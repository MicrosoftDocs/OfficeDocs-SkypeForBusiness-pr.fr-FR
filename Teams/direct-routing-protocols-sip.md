---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocoles de routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00df395ab67ea3e268cb31f202dd59cba4d4148b
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396315"
---
# <a name="direct-routing---sip-protocol"></a>Routage direct - Protocole SIP

Cet article décrit comment le routage direct implémente le protocole SIP (Session Initiation Protocol). Pour acheminer correctement le trafic entre un contrôleur de bordure de session (SBC) et le proxy SIP, certains paramètres SIP doivent avoir des valeurs spécifiques. Cet article s’adresse aux administrateurs vocaux responsables de la configuration de la connexion entre le SBC local et le service proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Traitement de la requête entrante : recherche du locataire et de l’utilisateur

Avant qu’un appel entrant ou sortant puisse être traité, les messages OPTIONS sont échangés entre le proxy SIP et le SBC. Ces messages OPTIONS permettent au proxy SIP de fournir les fonctionnalités autorisées à SBC. Il est important que la négociation OPTIONS réussisse (réponse 200OK), ce qui permet une communication supplémentaire entre SBC et le proxy SIP pour l’établissement des appels. Les en-têtes SIP d’un message OPTIONS vers le proxy SIP sont fournis à titre d’exemple ci-dessous :

| Nom du paramètre | Exemple de la valeur | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Via l’en-tête | Via : SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| en-tête Max-Forwards | Max-Forwards:68 |
| À partir de l’en-tête | À partir de l’en-tête : <sip:sbc1.adatum.biz:5058> |
| Vers l’en-tête | À: <sip:sip.pstnhub.microsoft.com:5061> |
| En-tête CSeq | CSeq: 1 INVITE | 
| En-tête de contact | Contact: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Les en-têtes SIP ne contiennent pas d’userinfo dans l’URI SIP utilisé. Conformément à [la RFC 3261, section 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), la partie userinfo d’un URI est facultative et peut être absente lorsque l’hôte de destination n’a pas de notion d’utilisateurs ou lorsque l’hôte lui-même est la ressource identifiée. Si le signe @ est présent dans un URI SIP, le champ utilisateur NE DOIT PAS être vide.
> Notez que l’URI SIPS ne doit pas être utilisé avec le routage direct, car il n’est pas pris en charge.
> Vérifiez la configuration de votre contrôleur de frontière de session et assurez-vous que vous n’utilisez pas les en-têtes « Remplacer » dans les demandes SIP. Le routage direct rejette les demandes SIP dont les en-têtes Replaces sont définis.

Lors d’un appel entrant, le proxy SIP doit rechercher le locataire auquel l’appel est destiné et trouver l’utilisateur spécifique au sein de ce locataire. L’administrateur de locataire peut configurer des numéros non DID, par exemple +1001, dans plusieurs locataires. Par conséquent, il est important de trouver le locataire spécifique sur lequel effectuer la recherche de nombres, car les numéros non DID peuvent être les mêmes dans plusieurs organisations Microsoft 365 ou Office 365.  

Cette section décrit comment le proxy SIP recherche le locataire et l’utilisateur, et effectue l’authentification du SBC sur la connexion entrante.

Voici un exemple de message d’invitation SIP sur un appel entrant :

| Nom du paramètre | Exemple de la valeur | 
| :---------------------  |:---------------------- |
| Request-URI | INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Via l’en-tête | Via : SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| en-tête Max-Forwards | Max-Forwards:68 |
| À partir de l’en-tête | À partir de l’en-tête : <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Vers l’en-tête | À : sip:+183338006777@sbc1.adatum.biz | 
| En-tête CSeq | CSeq: 1 INVITE | 
| En-tête de contact | Contact : <sip : 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Lors de la réception de l’invitation, le proxy SIP effectue les étapes suivantes :

1. Vérifiez le certificat. Lors de la connexion initiale, le service de routage direct prend le nom de nom de domaine complet présenté dans l’en-tête Contact et le correspond au nom commun ou à l’autre nom de l’objet du certificat présenté. Le nom SBC doit correspondre à l’une des options suivantes :

   - Option 1. Le nom complet du nom de domaine complet présenté dans l’en-tête Contact doit correspondre au nom commun/autre nom de l’objet du certificat présenté.  

   - Option 2. La partie domaine du nom de nom de domaine complet présentée dans l’en-tête Contact (par exemple, adatum.biz du nom de nom de domaine complet sbc1.adatum.biz) doit correspondre à la valeur générique dans common name/Subject Alternative Name (par exemple *.adatum.biz).

2. Essayez de trouver un locataire à l’aide du nom complet du nom de domaine complet présenté dans l’en-tête Contact.  

   Vérifiez si le nom de nom de domaine complet de l’en-tête de contact (sbc1.adatum.biz) est inscrit en tant que nom DNS dans une organisation Microsoft 365 ou Office 365. Si elle est trouvée, la recherche de l’utilisateur est effectuée dans le locataire sur lequel le nom de domaine complet SBC est inscrit en tant que nom de domaine. S’il est introuvable, l’étape 3 s’applique.   

3. L’étape 3 s’applique uniquement si l’étape 2 a échoué. 

   Supprimez la partie hôte du nom de domaine complet, présentée dans l’en-tête de contact (FQDN : sbc12.adatum.biz, après avoir supprimé la partie hôte : adatum.biz) et vérifiez si ce nom est inscrit en tant que nom DNS dans une organisation Microsoft 365 ou Office 365. Si elle est trouvée, la recherche utilisateur est effectuée dans ce locataire. S’il est introuvable, l’appel échoue.

4. À l’aide du numéro de téléphone présenté dans l’URI de requête, effectuez la recherche de numéro inversé dans le locataire trouvé à l’étape 2 ou 3. Faites correspondre le numéro de téléphone présenté à un URI SIP utilisateur dans le locataire trouvé à l’étape précédente.

5. Appliquer les paramètres de jonction. Recherchez les paramètres définis par l’administrateur client pour ce SBC.

   Microsoft ne prend pas en charge l’utilisation d’un proxy SIP tiers ou d’un serveur d’agent utilisateur entre le proxy SIP Microsoft et le SBC associé, ce qui peut modifier l’URI de demande créé par le SBC associé.

   Les exigences pour les deux recherches (étapes 2 et 3) requises pour le scénario où un SBC est interconnecté à de nombreux locataires (scénario de transporteur) sont abordées plus loin dans cet article.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Exigences détaillées pour l’en-tête contact et l’URI de demande

#### <a name="contact-header"></a>En-tête de contact

Pour tous les messages SIP entrants (OPTIONS, INVITE) vers le proxy SIP Microsoft, l’en-tête de contact doit avoir le nom de domaine complet SBC associé dans le nom d’hôte de l’URI comme suit :

Syntaxe : Contact : <sip:phone ou sip address@FQDN du SBC;transport=tls> 

Conformément à [RFC 3261, section 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), un champ d’en-tête Contact peut être présent dans un message OPTIONS. Dans le routage direct, l’en-tête de contact est requis. Pour les messages INVITE au format ci-dessus, pour les messages OPTIONS, l’élément userinfo peut être supprimé de l’URI SIP et seul le nom de domaine complet envoyé au format suivant :

Syntaxe : Contact : <sip:FQDN du SBC;transport=tls>

Ce nom (FQDN) doit également se trouver dans les champs Nom commun ou Autre nom de l’objet du certificat présenté. Microsoft prend en charge l’utilisation de valeurs génériques du ou des noms dans les champs Nom commun ou Autre nom de l’objet du certificat.   

La prise en charge des caractères génériques est décrite dans [la section 3.1 du RFC 2818](https://tools.ietf.org/html/rfc2818#section-3.1). Spécifiquement:

*« Les noms peuvent contenir le caractère \* générique qui est considéré comme correspondant à n’importe quel composant ou fragment de composant de nom de domaine unique. Par exemple, \*.a.com correspond à foo.a.com mais pas bar.foo.a.com. f.com\* correspond à foo.com mais pas bar.com. »*

Si plusieurs valeurs de l’en-tête Contact présentées dans un message SIP sont envoyées par le SBC, seule la partie FQDN de la première valeur de l’en-tête Contact est utilisée.

En règle générale pour le routage direct, il est important que le nom de domaine complet soit utilisé pour remplir l’URI SIP au lieu de l’adresse IP. Un message INVITATION ou OPTIONS entrant vers le proxy SIP avec l’en-tête Contact où le nom d’hôte est représenté par IP et non par un nom de domaine complet, la connexion est refusée avec la valeur 403 Interdit.

#### <a name="request-uri"></a>Request-URI 

Pour tous les appels entrants, l’URI de demande est utilisé pour faire correspondre le numéro de téléphone à un utilisateur.   

Actuellement, le numéro de téléphone doit contenir un signe plus (+) comme indiqué dans l’exemple suivant. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>À partir de l’en-tête

Pour tous les appels entrants, l’en-tête From est utilisé pour faire correspondre le numéro de téléphone de l’appelant à la liste des numéros de téléphone bloqués de l’appelant.

Le numéro de téléphone doit contenir un + comme indiqué dans l’exemple suivant.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Considérations relatives aux en-têtes de contact et de Record-Route

Le proxy SIP doit calculer le nom de domaine complet du tronçon suivant pour les nouvelles transactions clientes dans la boîte de dialogue (par exemple, bye ou ré-invitation) et lors de la réponse aux options SIP. Contact ou Record-Route sont utilisés. 

Selon [RFC 3261, section 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), l’en-tête de contact est requis dans toute demande pouvant entraîner une nouvelle boîte de dialogue. La Record-Route n’est requise que si un proxy souhaite rester sur le chemin des demandes futures dans une boîte de dialogue. Si un SBC proxy est utilisé avec [l’optimisation des médias locaux pour le routage direct](./direct-routing-media-optimization.md), un itinéraire d’enregistrement doit être configuré, car le SBC proxy doit rester dans l’itinéraire. 

Microsoft recommande d’utiliser uniquement l’en-tête Contact si un SBC proxy n’est pas utilisé :

- Par [RFC 3261, section 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route est utilisé si un proxy souhaite rester sur le chemin des demandes futures dans une boîte de dialogue, ce qui n’est pas essentiel si aucun proxy SBC n’est configuré car tout le trafic va entre le proxy SIP Microsoft et le SBC associé. 

- Le proxy Microsoft SIP utilise uniquement l’en-tête Contact (et non record-route) pour déterminer le tronçon suivant lors de l’envoi des options ping sortantes. La configuration d’un seul paramètre (Contact) au lieu de deux (Contact et Record-Route) simplifie l’administration si un SBC proxy n’est pas utilisé. 

Pour calculer le tronçon suivant, le proxy SIP utilise :

- Priorité 1. Route d’enregistrement de niveau supérieur. Si le Record-Route de niveau supérieur contient le nom de nom de domaine complet, le nom de domaine complet est utilisé pour établir la connexion sortante dans la boîte de dialogue.

- Priorité 2. En-tête de contact. Si Record-Route n’existe pas, le proxy SIP recherche la valeur de l’en-tête Contact pour établir la connexion sortante. (Il s’agit de la configuration recommandée.)

Si contact et Record-Route sont utilisés, l’administrateur SBC doit conserver leurs valeurs identiques, ce qui entraîne une surcharge administrative. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Utilisation du nom de domaine complet dans Contact ou Record-Route

L’utilisation d’une adresse IP n’est pas prise en charge dans Record-Route ou Contact. La seule option prise en charge est un nom de domaine complet, qui doit correspondre au nom commun ou à l’autre nom de l’objet du certificat SBC (les valeurs génériques du certificat sont prises en charge).

- Si une adresse IP est présentée dans Record-route ou Contact, la vérification du certificat échoue et l’appel échoue.

- Si le nom de domaine complet ne correspond pas à la valeur de l’autre nom commun ou de l’autre nom de l’objet dans le certificat présenté, l’appel échoue. 

## <a name="inbound-call-sip-dialog-description"></a>Appel entrant : description de la boîte de dialogue SIP

Le tableau suivant ci-dessous récapitule les différences de flux d’appel et les similitudes entre les modes de non-contournement et de contournement :

| Nom du paramètre | Mode sans contournement | Mode de contournement
| :---------------------  |:---------------------- |:----------------|
| Médias candidats dans 183 et 200 messages provenant de | Processeurs multimédias | Clients | 
| Nombre de 183 messages que SBC peut recevoir | Un par session | Plusieurs | 
| L’appel peut être avec la réponse provisoire (183) | Oui | Oui |
| L’appel peut être sans réponse provisoire (183) | Oui | Oui |

###  <a name="non-media-bypass-flow"></a>Flux de contournement non multimédia

Un utilisateur Teams peut avoir plusieurs points de terminaison en même temps. Par exemple, le client Teams pour Windows, teams pour iPhone et Teams Phone (client Android Teams). Chaque point de terminaison peut signaler un repos HTTP comme suit :

-   Progression des appels : convertie par le proxy SIP en message SIP 180. Lors de la réception du message 180, le SBC doit générer une sonnerie locale.

-   Réponse multimédia : convertie par le proxy SIP en message 183 avec les médias candidats dans le protocole SDP (Session Description Protocol). Lors de la réception du message 183, le SBC s’attend à se connecter aux candidats multimédias reçus dans le message SDP. 

    > [!NOTE]
    > Dans certains cas, la réponse media peut ne pas être générée, et le point de terminaison peut répondre avec le message « Appel accepté ».

-   Appel accepté : converti par le proxy SIP en message SIP 200 avec SDP. Lors de la réception du message 200, le SBC est censé envoyer et recevoir des médias vers et à partir des candidats SDP fournis.

    > [!NOTE]
    > Le routage direct ne prend pas en charge l’invite d’offre différée (invite sans SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Plusieurs points de terminaison sonnerie avec réponse provisoire

1.  Lors de la réception de la première invitation à partir du SBC, le proxy SIP envoie le message « SIP SIP/2.0 100 Trying » et avertit tous les points de terminaison de l’utilisateur final de l’appel entrant. 

2.  Lors de la notification, chaque point de terminaison commence à sonner et à envoyer des messages « Progression des appels » au proxy SIP. Étant donné qu’un utilisateur Teams peut avoir plusieurs points de terminaison, le proxy SIP peut recevoir plusieurs messages de progression des appels.

3.  Pour chaque message de progression des appels reçu des clients, le proxy SIP convertit le message de progression de l’appel en message SIP « SIP SIP/2.0 180 Ringing ». L’intervalle d’envoi de ces messages est défini par l’intervalle des messages de réception du contrôleur d’appel. Dans le diagramme suivant, deux messages 180 sont générés par le proxy SIP. Ces messages proviennent des deux points de terminaison Teams de l’utilisateur. Les clients ont chacun un ID de balise unique.  Chaque message provenant d’un point de terminaison différent sera une session distincte (le paramètre « tag » dans le champ « À » sera différent). Toutefois, un point de terminaison peut ne pas générer le message 180 et envoyer immédiatement le message 183, comme illustré dans le diagramme suivant.

4.  Une fois qu’un point de terminaison génère un message Media Answer avec les adresses IP des candidats multimédias du point de terminaison, le proxy SIP convertit le message reçu en message « PROGRESSION de session SIP 183 » avec le protocole SDP du client remplacé par le protocole SDP du processeur multimédia. Dans le diagramme suivant, le point de terminaison de Fork 2 a répondu à l’appel. Si la jonction n’est pas contournée, le message SIP 183 n’est généré qu’une seule fois (ring bot ou point de terminaison client). Le 183 peut arriver sur une fourchette existante ou en démarrer une nouvelle.

5.  Un message d’acceptation d’appel est envoyé avec les derniers candidats du point de terminaison qui a accepté l’appel. Le message d’acceptation d’appel est converti en message SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramme montrant plusieurs points de terminaison qui sonnent avec une réponse provisoire.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Plusieurs points de terminaison sonnerie sans réponse provisoire

1.  Lors de la réception de la première invitation à partir du SBC, le proxy SIP envoie le message « SIP SIP/2.0 100 Trying » et avertit tous les points de terminaison de l’utilisateur final de l’appel entrant. 

2.  Lors de la notification, chaque point de terminaison commence à sonner et à envoyer le message « Progression de l’appel » au proxy SIP. Étant donné qu’un utilisateur Teams peut avoir plusieurs points de terminaison, le proxy SIP peut recevoir plusieurs messages de progression des appels.

3.  Pour chaque message de progression des appels reçu des clients, le proxy SIP convertit le message progression de l’appel en message SIP « SIP SIP/2.0 180 Trying ».  L’intervalle d’envoi des messages est défini par l’intervalle de réception des messages à partir du contrôleur d’appel. Sur l’image ci-dessous, deux messages 180 sont générés par le proxy SIP, ce qui signifie que l’utilisateur s’est connecté à trois clients Teams et que chaque client envoie la progression de l’appel. Chaque message sera une session distincte (le paramètre « tag » dans le champ « À » est différent)

4.  Un message d’acceptation d’appel est envoyé avec les derniers candidats du point de terminaison qui a accepté l’appel. Le message d’acceptation d’appel est converti en message SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramme montrant plusieurs points de terminaison qui sonnent sans réponse provisoire.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flux de contournement du média

Les mêmes messages (100 Tentative, 180, 183) sont utilisés dans le scénario de contournement du média. 

Le schéma ci-dessous montre un exemple de flux d’appel de contournement. 

> [!NOTE]
> Les candidats multimédias peuvent provenir de différents points de terminaison. 

> [!div class="mx-imgBorder"]
> ![Diagramme montrant plusieurs points de terminaison qui sonnent avec une réponse provisoire.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Remplace l’option

Le SBC doit prendre en charge Invite with Replaces.

## <a name="size-of-sdp-considerations"></a>Taille des considérations relatives au protocole SDP

L’interface de routage direct peut envoyer un message SIP dépassant 1 500 octets.  La taille de SDP est principalement à l’origine de cette situation. Toutefois, s’il existe une jonction UDP derrière le SBC, elle peut rejeter le message s’il est transféré du proxy SIP Microsoft vers la jonction non modifiée. Microsoft recommande de supprimer certaines valeurs dans SDP sur le SBC lors de l’envoi du message aux jonctions UDP. Par exemple, les candidats ICE ou les codecs inutilisés peuvent être supprimés.

## <a name="call-transfer"></a>Transfert d’appel

Le routage direct prend en charge deux méthodes pour le transfert d’appels :

- Option 1. Les processus de proxy SIP font référence au client localement et jouent le rôle d’arbitre, comme décrit dans la section 7.1 du RFC 3892.

  Avec cette option, le proxy SIP met fin au transfert et ajoute une nouvelle invite. 


- Option 2. Le proxy SIP envoie le référentiel au SBC et agit comme un transféreur comme décrit dans la section 6 du RFC 5589.

  Avec cette option, le proxy SIP envoie une référence au SBC et s’attend à ce que le SBC gère entièrement le transfert.

Le proxy SIP sélectionne la méthode en fonction des fonctionnalités signalées par le SBC. Si le SBC indique qu’il prend en charge la méthode « Refer », le proxy SIP utilise l’option 2 pour les transferts d’appels.

Voici un exemple de SBC qui envoie le message indiquant que la méthode Refer est prise en charge :

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Si le SBC n’indique pas qu’il s’agit d’une méthode prise en charge, le routage direct utilise l’option 1 (le proxy SIP agit en tant qu’arbitre). Le SBC doit également signaler qu’il prend en charge la méthode Notify :

Exemple de SBC indiquant que la méthode Refer n’est pas prise en charge :

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processus proxy SIP Faire référence au client localement et agir en tant qu’arbitre

Si le SBC a indiqué que la méthode Refer n’est pas prise en charge, le proxy SIP agit en tant qu’arbitre. 

La demande De référence qui provient du client sera arrêtée sur le proxy SIP. (La demande De référence du client s’affiche sous la forme « Transfert d’appel à Dave » dans le diagramme suivant.  Pour plus d’informations, consultez la section 7.1 du [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagramme montrant plusieurs points de terminaison qui sonnent avec une réponse provisoire.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Le proxy SIP envoie le référentiel au SBC et agit en tant que transféreur

Il s’agit de la méthode préférée pour les transferts d’appels, et elle est obligatoire pour les appareils qui recherchent la certification de contournement multimédia. Le transfert d’appel sans que le SBC puisse gérer Refer n’est pas pris en charge en mode de contournement du média. 

La norme est expliquée dans la section 6 du RFC 5589. Les RFC connexes sont les suivants :

- [Contrôle d’appel SIP (Session Initiation Protocol) - Transfert](https://tools.ietf.org/html/rfc5589)

- [En-tête SIP (Session Initiation Protocol) « Remplace »](https://tools.ietf.org/html/rfc3891)

- [Mécanisme SIP (Session Initiation Protocol) « Référencé par »](https://tools.ietf.org/html/rfc3892)

Cette option suppose que le proxy SIP agit comme un transféreur et envoie un message De référence au SBC. Le SBC agit en tant que Transferee et gère le référent pour générer une nouvelle offre pour le transfert. Il existe deux cas possibles :

- L’appel est transféré à un participant RTC externe. 
- L’appel est transféré d’un utilisateur Teams à un autre utilisateur Teams dans le même locataire via le SBC. 

Si l’appel est transféré d’un utilisateur Teams à un autre via le SBC, le SBC est censé émettre une nouvelle invitation (démarrer une nouvelle boîte de dialogue) pour la cible de transfert (l’utilisateur Teams) à l’aide des informations reçues dans le message De référence. 

Pour remplir les champs To/Transferor pour la transaction de la demande en interne, le proxy SIP doit transmettre ces informations à l’intérieur des en-têtes REFER-TO/REFERRED-BY. 

Le proxy SIP forme le RÉFÉR-TO en tant qu’URI SIP composé d’un nom de domaine complet de proxy SIP dans le nom d’hôte et l’un des éléments suivants :

- Un numéro de téléphone E.164 dans la partie nom d’utilisateur de l’URI si la cible de transfert est un numéro de téléphone, ou

- Paramètres x-m et x-t encodant respectivement l’IRM cible de transfert complet et l’ID de locataire 

L’en-tête REFERRED-BY est un URI SIP dont l’IRM du transférateur est encodée, ainsi que l’ID de locataire du transféreur et d’autres paramètres de contexte de transfert, comme indiqué dans le tableau suivant :

| Paramètre | Valeur | Description% |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Irm | IRM complète de la cible de transfert/transfert comme rempli par CC |
| x-t | ID du locataire | ID de locataire facultatif x-t tel que rempli par CC |
| x-ti | ID de corrélation du transféreur | ID de corrélation de l’appel au transférateur |
| x-tt | Transférer l’URI d’appel cible | URI de remplacement d’appel encodé |

Dans ce cas, la taille de l’en-tête de référence peut atteindre 400 symboles. Le SBC doit prendre en charge la gestion des messages De référence avec une taille maximale de 400 symboles.

> [!div class="mx-imgBorder"]
> ![Diagramme montrant plusieurs points de terminaison qui sonnent avec une réponse provisoire.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Minuteur de session

Le proxy SIP prend en charge (offre toujours) le minuteur de session sur les appels sans contournement, mais ne l’offre pas sur les appels de contournement. L’utilisation du minuteur de session par le SBC n’est pas obligatoire.

##  <a name="use-of-request-uri-parameter-userphone"></a>Utilisation du paramètre Request-URI user=phone

Le proxy SIP analyse l’URI de requête et, si le paramètre user=phone est présent, le service gère l’URI de demande en tant que numéro de téléphone, correspondant au numéro à un utilisateur. Si le paramètre n’est pas présent, le proxy SIP applique une heuristique pour déterminer le type d’utilisateur Request-URI (numéro de téléphone ou adresse SIP).

Microsoft recommande de toujours appliquer le paramètre user=phone pour simplifier le processus d’installation des appels.

## <a name="history-info-header"></a>en-tête History-Info

L’en-tête History-Info est utilisé pour reciblage des demandes SIP et « fournit (s) un mécanisme standard pour capturer les informations d’historique des demandes afin d’activer un large éventail de services pour les réseaux et les utilisateurs finaux ». Pour plus d’informations, consultez [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt). Pour Microsoft Phone System, cet en-tête est utilisé dans les scénarios de simulring et de transfert d’appel.  

En cas d’envoi, le History-Info est activé comme suit :

- Le proxy SIP insère un paramètre contenant le numéro de téléphone associé dans des entrées History-Info individuelles qui comprennent l’en-tête History-Info envoyé au contrôleur RTC.  En utilisant uniquement les entrées qui ont le paramètre de numéro de téléphone, le contrôleur RTC regénère un nouvel en-tête History-Info et le transmet au fournisseur de jonction SIP via le proxy SIP.

- History-Info'en-tête est ajouté pour les cas de transfert d’appel et d’anneau simultanés.

- History-Info'en-tête n’est pas ajouté pour les cas de transfert d’appel.

- Une entrée d’historique individuelle dans l’en-tête History-Info reconstruit aura le paramètre de numéro de téléphone fourni combiné avec le nom de domaine complet de routage direct (sip.pstnhub.microsoft.com) défini comme partie hôte de l’URI ; un paramètre « user=phone » est ajouté dans le cadre de l’URI SIP.  Tous les autres paramètres associés à l’en-tête History-Info d’origine, à l’exception des paramètres de contexte de téléphone, sont transmis dans l’en-tête History-Info recréé.  

  > [!NOTE]
  > Les entrées privées (déterminées par les mécanismes définis dans la section 3.3 du RFC 4244) sont transférées telles quelle, car le fournisseur de jonctions SIP est un homologue approuvé.

- Les History-Info entrantes sont ignorées.

Voici le format de l’en-tête History-info envoyé par le proxy SIP :

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Si l’appel a été redirigé plusieurs fois, les informations sur chaque redirection sont incluses avec la raison appropriée dans l’ordre chronologique.


Exemple d’en-tête :

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Le History-Info est protégé par un mécanisme TLS obligatoire. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Connexion SBC au routage direct et au mécanisme de basculement

Consultez la section Mécanisme de basculement pour la signalisation SIP dans [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Si un centre de données de routage direct est occupé, le service peut envoyer un message Retry-After avec un intervalle d’une seconde au SBC. Lorsque le SBC reçoit un message 503 avec un en-tête Retry-After en réponse à une invite, le SBC doit arrêter cette connexion et essayer le prochain centre de données Microsoft disponible.

## <a name="handling-retries-603-response"></a>Gestion des nouvelles tentatives (réponse 603)
Si un utilisateur final observe plusieurs appels manqués pour un appel après avoir décliné l’appel entrant, cela signifie que le mécanisme de nouvelle tentative du fournisseur de jonctions SBC ou PSTN est mal configuré. Le SBC doit être reconfiguré pour arrêter les efforts de nouvelle tentative sur la réponse 603.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Redémarrage ice : appel de contournement multimédia transféré vers un point de terminaison qui ne prend pas en charge le contournement du média

Le SBC doit prise en charge les redémarrages ICE, comme décrit dans [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Le redémarrage dans le routage direct est implémenté conformément aux paragraphes suivants du RFC :

*Pour redémarrer ICE, un agent DOIT modifier à la fois le ice-pwd et le ice-ufrag pour le flux multimédia dans une offre.  Notez qu’il est permis d’utiliser un attribut de niveau session dans une offre, mais de fournir le même ice-pwd ou ice-ufrag qu’un attribut de niveau média dans une offre ultérieure.  Il ne s’agit pas d’une modification du mot de passe, mais simplement d’une modification de sa représentation et ne provoque pas de redémarrage de l’ice.*

*Un agent définit le reste des champs dans le SDP pour ce flux multimédia comme il le ferait dans une offre initiale de ce flux multimédia (voir la section 4.3).  Par conséquent, l’ensemble des candidats peut inclure certains, aucun ou l’ensemble des candidats précédents pour ce flux et PEUT inclure un ensemble totalement nouveau de candidats rassemblés comme décrit à l’article 4.1.1.*

Si l’appel a été initialement établi avec la déviation du trafic multimédia et que l’appel est transféré vers un client Skype Entreprise, le routage direct doit insérer un processeur multimédia, car le routage direct ne peut pas être utilisé avec un client Skype Entreprise avec contournement du média. Le routage direct démarre le processus de redémarrage de l’ICE en modifiant les ice-pwd et ice-ufrag et en offrant de nouveaux médias candidats dans une réinitialisation.
