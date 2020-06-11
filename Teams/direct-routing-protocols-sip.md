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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocoles de routage directe
appliesto:
- Microsoft Teams
ms.openlocfilehash: 264e7e3de8031e8ac150c186078ff3d7ccff2f16
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691220"
---
# <a name="direct-routing---sip-protocol"></a>Routage direct-protocole SIP

Cet article décrit comment le routage direct implémente le protocole SIP (Session Initiation Protocol). Pour acheminer correctement le trafic entre un contrôleur de bordure de session et le proxy SIP, certains paramètres SIP doivent avoir des valeurs spécifiques. Cet article est destiné aux administrateurs de voix qui sont responsables de la configuration de la connexion entre le SBC local et le service proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Traitement de la demande entrante : recherche du client et de l’utilisateur

Lors d’un appel entrant, le proxy SIP doit rechercher le client auquel est destiné l’appel et Rechercher l’utilisateur spécifique au sein de ce client. L’administrateur client peut configurer des numéros qui ne sont pas des nombres, par exemple + 1001, dans plusieurs clients. Par conséquent, il est important de rechercher le client spécifique sur lequel effectuer la recherche de numéro, car les numéros qui ne sont pas les mêmes peuvent être identiques dans plusieurs organisations Microsoft 365 ou Office 365.  

Cette section décrit la façon dont le proxy SIP trouve le locataire et l’utilisateur et effectue l’authentification de l’SBC sur la connexion entrante.

Voici un exemple du message d’invitation SIP lors d’un appel entrant :

| Nom du paramètre | Exemple de valeur | 
| :---------------------  |:---------------------- |
| Requête-URI | INVITER sip :+18338006777@sip.pstnhub.microsoft.com SIP/2,0 |
| En-tête via | Via : SIP/2.0/TLS sbc1. adatum. biz : 5058 ; alias = z9hG4bKac2121518978 | 
| En-tête de transfert maximal | Maximum : 68 |
| En-tête de | À partir de l’en-tête de : <SIP : 7168712781@sbc1. adatum. biz ; transport = UDP ; balise = 1c747237679 |
| En-tête | Pour : sip :+183338006777@sbc1.adatum.biz | 
| En-tête CSeq | CSeq : 1 invitation | 
| En-tête contact | Contact : <SIP : 68712781@sbc1. adatum. biz ; transport = TLS> | 

Lors de la réception de l’invitation, le proxy SIP effectue les étapes suivantes :

1. Vérifier le certificat. Lors de la connexion initiale, le service de routage direct utilise le nom de domaine complet figurant dans l’en-tête du contact et le fait correspondre au nom usuel ou au nom d’objet alternatif du certificat présenté. Le nom SBC doit correspondre à l’une des options suivantes :

   - Option 1. Le nom de domaine complet complet figurant dans l’en-tête de contact doit correspondre au nom du certificat que vous avez présenté.  

   - Option 2. La partie Domain du nom de domaine complet figurant dans l’en-tête de contact (par exemple, adatum.biz du nom de domaine complet sbc1.adatum.biz) doit correspondre à la valeur du caractère générique figurant dans nom ou objet commun (par exemple, *. adatum.biz).

2. Essayez de rechercher un client à l’aide du nom complet complet figurant dans l’en-tête contact.  

   Vérifiez si le nom de domaine complet de l’en-tête de contact (sbc1.adatum.biz) est enregistré en tant que nom DNS dans toute organisation Microsoft 365 ou Office 365. Le cas échéant, la liste de choix de l’utilisateur est exécutée dans le client qui dispose du nom de domaine complet SBC inscrit comme nom de domaine. S’il est introuvable, l’étape 3 s’applique.   

3. L’étape 3 s’applique uniquement en cas d’échec de l’étape 2. 

   Supprimez la partie hôte du nom de domaine complet (FQDN) figurant dans l’en-tête de contact (nom de domaine complet (FQDN) : sbc12.adatum.biz, après avoir supprimé la partie hôte : adatum.biz), puis vérifiez que ce nom est enregistré en tant que nom DNS dans une organisation Microsoft 365 ou Office 365. Le cas échéant, la recherche utilisateur est effectuée dans ce client. Si ce n’est pas le cas, l’appel échoue.

4. En utilisant le numéro de téléphone présenté dans la requête-URI, effectuez la recherche de numéro inverse dans le client trouvé à l’étape 2 ou 3. Associez le numéro de téléphone présenté à un URI SIP utilisateur dans le client indiqué à l’étape précédente.

5. Appliquez les paramètres de Trunk. Recherchez les paramètres définis par l’administrateur client pour cet SBC.

   Microsoft ne prend pas en charge la présence d’un proxy SIP ou d’un serveur d’agent utilisateur tiers entre le proxy SIP Microsoft et l’SBC couplé, qui peut modifier l’URI de la demande créée par le SBC couplé.

   La configuration requise pour les deux recherches (étapes 2 et 3) requises pour le scénario dans lequel un SBC est interconnectée à de nombreux clients (scénario d’opérateur) est décrite plus loin dans cet article.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Exigences détaillées pour l’en-tête et la demande de contact

#### <a name="contact-header"></a>En-tête contact

Pour tous les appels entrants du proxy SIP Microsoft, l’en-tête de contact doit avoir le nom de domaine complet du SBC couplé dans le nom d’hôte de l’URI comme suit :

Syntaxe : contact : <SIP : téléphone ou address@FQDN SIP de l’SBC ; transport = TLS> 

Ce nom doit également figurer dans le ou les champs du nom usuel ou du nom de remplacement de l’objet du certificat présenté. Microsoft prend en charge l’utilisation de valeurs génériques du ou des noms figurant dans les champs nom usuel ou autre nom de l’objet du certificat.   

La prise en charge des caractères génériques est décrite dans [RFC 2818, section 3,1](https://tools.ietf.org/html/rfc2818#section-3.1). Destinées

*"Les noms doivent contenir le caractère générique \* qui est considéré comme correspondant à tout composant de nom de domaine ou fragment de composant. Par exemple, \* . a.com correspond à foo.a.com mais pas bar.foo.a.com. f \* . com correspond à foo.com, mais pas bar.com. "*

Si plusieurs valeurs dans l’en-tête de contact présentées dans un message SIP sont envoyées par l’SBC, seule la partie FQDN de la première valeur de l’en-tête de contact est utilisée.

#### <a name="request-uri"></a>Requête-URI 

Pour tous les appels entrants, la requête-URI est utilisée pour faire correspondre le numéro de téléphone à un utilisateur.   

Le numéro de téléphone doit actuellement contenir le signe plus (+), comme le montre l’exemple suivant. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Considérations relatives aux en-têtes de contact et d’enregistrement

Le proxy SIP doit calculer le nom de domaine complet (FQDN) du tronçon suivant pour les nouvelles transactions de client dans la boîte de dialogue (par exemple, bye ou réinvite) et lorsque vous répondez aux options SIP. Les options contact ou enregistrement-itinéraire sont utilisées. 

D’après le RFC 3261, l’en-tête de contact est requis pour toutes les demandes qui peuvent engendrer une nouvelle boîte de dialogue. L’enregistrement-itinéraire est requis uniquement si un proxy veut rester sur le chemin d’accès des demandes futures dans une boîte de dialogue. 

Microsoft recommande l’utilisation de l’en-tête contact uniquement pour les raisons suivantes :

- Par RFC 3261, la fonction record-route est utilisée si un proxy veut rester sur le chemin d’une requête future dans une boîte de dialogue, ce qui n’est pas essentiel pour le trafic entre le proxy SIP Microsoft et le SBC couplé. Il n’est pas nécessaire de disposer d’un serveur proxy intermédiaire entre le serveur proxy SBC et Microsoft SIP.

- Le serveur proxy SIP Microsoft utilise uniquement l’en-tête contact (pas d’enregistrement) pour déterminer le saut suivant lors de l’envoi des options de test ping sortant. La configuration d’un seul paramètre (contact) au lieu de deux (contact et enregistrement-itinéraire) simplifie l’administration.

Pour calculer le tronçon suivant, le proxy SIP utilise les éléments suivants :

- Priorité 1. Enregistrement de niveau supérieur-itinéraire. Si le nom d’enregistrement de niveau supérieur contient le nom de domaine complet (FQDN) ou l’adresse IP, le nom de domaine complet (FQDN) ou l’adresse IP sont utilisés pour établir la connexion sortante dans la boîte de dialogue.

- Priorité 2. En-tête contact. Si Record-route n’existe pas, le proxy SIP vérifie la valeur de l’en-tête de contact pour établir la connexion sortante. (Il s’agit de la configuration recommandée.)

Si le contact et l’itinéraire d’enregistrement sont tous deux utilisés, l’administrateur de l’SBC doit conserver leurs valeurs identiques, ce qui entraîne la surcharge administrative. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Utilisation du nom de domaine complet (FQDN) dans les contacts ou les itinéraires

L’utilisation d’une adresse IP n’est pas prise en charge dans la rubrique enregistrement-itinéraire ou contact. La seule option prise en charge est un nom de domaine complet (FQDN) qui doit correspondre au nom usuel ou au nom alternatif du certificat SBC (les valeurs génériques du certificat sont prises en charge).

- S’il s’agit d’une adresse IP, le contrôle du certificat échoue et l’appel échoue.

- Si le nom de domaine complet ne correspond pas à la valeur du nom du Common ou de l’objet dans le certificat présenté, l’appel échoue. 

## <a name="inbound-call-sip-dialog-description"></a>Appel entrant : description de la boîte de dialogue SIP

Le tableau suivant récapitule les différences de flux d’appels et les similarités entre les modes sans contournement et contournement :

| Nom du paramètre | Mode sans contournement | Mode ignorer
| :---------------------  |:---------------------- |:----------------|
| Éléments médias dans 183 et 200 messages provenant de | Processeurs multimédias | Clients | 
| Nombre de messages 183 que SBC peut recevoir | Une par session | Multiples | 
| L’appel peut être avec une réponse provisoire (183) | Oui | Oui |
| L’appel peut être sans réponse provisoire (183) | Oui | Oui |

###  <a name="non-media-bypass-flow"></a>Flux de contournement non multimédia

Un utilisateur d’équipes peut avoir plusieurs points de terminaison en même temps. Par exemple, teams pour les clients Windows, teams pour iPhone et Teams (client d’équipe Android). Chaque point de terminaison peut signaler un Rest HTTP comme suit :

-   Progression de l’appel – converti par le proxy SIP par le message SIP 180. Lors de la réception d’un message 180, l’SBC doit générer une sonnerie locale.

-   Réponse multimédia : conversion par le proxy SIP en message 183 avec les médias dans le protocole SDP. Lors de la réception d’un message 183, l’SBC s’attend à ce qu’il se connecte aux candidats de médias reçus dans le message SDP. Notez que, dans certains cas, la réponse sur le média ne peut pas être générée et que le point de terminaison peut répondre par un message « appel accepté ».

-   Appel accepté – converti par le proxy SIP en message SIP 200 avec SDP. Lors de la réception d’un message 200, l’SBC est censé envoyer et recevoir des contenus multimédias vers et depuis les candidats SDP fournis.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Plusieurs points de terminaison appelant une réponse provisoire

1.  Lors de la réception de la première invitation de SBC, le proxy SIP envoie le message « SIP SIP/2.0 100 essayant » et avertit tous les points de terminaison de l’utilisateur final à propos de l’appel entrant. 

2.  Dès qu’une notification est lancée, chaque point de terminaison commence à sonner et à envoyer des messages « de progression des appels » au proxy SIP. Dans la mesure où un utilisateur d’équipes peut avoir plusieurs points de terminaison, le proxy SIP peut recevoir plusieurs messages de progression d’appel.

3.  Pour chaque message de progression des appels reçu de la part des clients, le proxy SIP convertit le message de progression de l’appel en message SIP « SIP SIP/2.0 180 essayant ». L’intervalle d’envoi de ces messages est défini par l’intervalle des messages de réception du contrôleur d’appel. Le schéma suivant comporte des messages 2 180 générés par le proxy SIP. Ces messages proviennent des deux points de terminaison teams de l’utilisateur. Les clients possèdent chacun un ID de balise unique.  Chaque message provenant d’un point de terminaison différent sera une session séparée (le paramètre « balise » dans le champ « à » sera différent). En revanche, un point de terminaison peut ne pas générer le message 180 et envoyer le message 183 immédiatement, comme illustré dans le schéma suivant.

4.  Dès lors que le point de terminaison génère un message de réponse multimédia avec les adresses IP des candidats multimédia du point de terminaison, le proxy SIP convertit le message reçu en message « progression de la session SIP 183 » avec le SDP du client remplacé par le SDP du processeur multimédia. Dans le diagramme suivant, le point de terminaison de bifurcation 2 a répondu à l’appel. En l’absence de contournement du Trunk, le message SIP 183 est généré une seule fois (soit en anneau ou point de terminaison client). Le 183 peut se trouver dans une fourchette existante ou en démarrer un nouveau.

5.  Un message d’acceptation d’appel est envoyé avec les candidats finaux du point de terminaison ayant accepté l’appel. Le message d’acceptation des appels est converti en message SIP 200. 

![Diagramme montrant plusieurs points de terminaison appelant une réponse provisoire](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Plusieurs points de terminaison qui sonnent sans réponse provisoire

1.  Lors de la réception de la première invitation de SBC, le proxy SIP envoie le message « SIP SIP/2.0 100 essayant » et avertit tous les points de terminaison de l’utilisateur final à propos de l’appel entrant. 

2.  Dès qu’une notification est lancée, chaque point de terminaison commence à sonner et envoie le message « progression des appels » au proxy SIP. Dans la mesure où un utilisateur d’équipes peut avoir plusieurs points de terminaison, le proxy SIP peut recevoir plusieurs messages de progression d’appel.

3.  Pour chaque message de progression des appels reçu de la part des clients, le proxy SIP convertit le message de progression de l’appel en message SIP « SIP SIP/2.0 180 essayant ».  L’intervalle d’envoi des messages est défini par l’intervalle de réception des messages du contrôleur d’appel. Dans l’image ci-dessous, des messages 2 180 sont générés par le proxy SIP, ce qui signifie que l’utilisateur s’est connecté à trois clients équipes et chaque client envoie la progression de l’appel. Chaque message sera une session séparée (le paramètre « balise » dans le champ « à » est différent)

4.  Un message d’acceptation d’appel est envoyé avec les candidats finaux du point de terminaison ayant accepté l’appel. Le message d’acceptation des appels est converti en message SIP 200. 

![Diagramme montrant plusieurs points de terminaison qui sonnent sans réponse provisoire](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flux de contournement du média

Les mêmes messages (100 essayant, 180, 183) sont utilisés dans le scénario de contournement de média. 

Le schéma ci-dessous montre un exemple de contournement du flux d’appels. Notez que les candidats de médias peuvent provenir de différents points de terminaison. 

![Diagramme montrant plusieurs points de terminaison appelant une réponse provisoire](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Option remplacer

L’SBC doit prendre en charge l’invitation avec des remplacements.

## <a name="size-of-sdp-considerations"></a>Taille des considérations SDP

L’interface de routage direct peut envoyer un message SIP de plus de 1 500 octets.  La taille de SDP est essentiellement à l’origine de ce problème. Toutefois, s’il y a un Trunk UDP derrière l’SBC, il est possible que le message soit rejeté s’il est transmis du proxy SIP Microsoft vers le Trunk non modifié. Microsoft recommande de répartir certaines valeurs dans SDP sur l’SBC lors de l’envoi du message aux Trunks UDP. Par exemple, les codecs de glace ou les codecs inutilisés peuvent être supprimés.

## <a name="call-transfer"></a>Transfert d’appel

Le routage directe prend en charge deux méthodes pour le transfert d’appel :

- Option 1. Les processus de proxy SIP font référence au client localement et agissant en tant qu’arbitre, comme décrit dans la section 7,1 de RFC 3892.

  Avec cette option, le proxy SIP arrête le transfert et ajoute une nouvelle invitation. 


- Option 2. Le proxy SIP envoie le rapport au SBC et agissant en tant que transféreur comme décrit à la section 6 de RFC 5589.

  Avec cette option, le proxy SIP envoie une référence à l’SBC et attend que l’SBC gère entièrement le transfert.

Le proxy SIP sélectionne la méthode en fonction des fonctionnalités rapportées par l’SBC. Si l’SBC indique qu’il prend en charge la méthode « refer », le proxy SIP utilisera option 2 pour les transferts d’appels.

Voici un exemple d’un SBC envoyant le message que la méthode refer est prise en charge :

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Si les SBC n’indiquent pas qu’il s’agit d’une méthode prise en charge, le routage direct utilise l’option 1 (proxy SIP agissant en tant qu’arbitre). L’SBC doit également signaler qu’il prend en charge la méthode Notify :

Exemple de SBC indiquant que la méthode refer n’est pas prise en charge :

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processus de proxy SIP faire référence au client en local et agissant en tant qu’arbitre

Si le SBC a indiqué que la méthode refer n’est pas prise en charge, le proxy SIP fait office d’arbitrage. 

La demande de renvoi fournie par le client sera arrêtée sur le proxy SIP. (La demande refer du client est représentée par « transfert d’appel vers Dave » dans le schéma suivant.  Pour plus d’informations, reportez-vous à la section 7,1 de [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

![Diagramme montrant plusieurs points de terminaison appelant une réponse provisoire](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Le proxy SIP envoie le rapport au SBC et fait office de transféreur

Il s’agit de la méthode recommandée pour les transferts d’appel et est obligatoire pour les appareils qui recherchent une certification de contournement de média. Le transfert d’appel sans SBC capable de gérer refer n’est pas pris en charge en mode de contournement multimédia. 

La norme est expliquée dans la section 6 de RFC 5589. Les RFC associées sont les suivantes :

- [Contrôle du protocole SIP (Session Initiation Protocol)-transfert](https://tools.ietf.org/html/rfc5589)

- [En-tête SIP (Session Initiation Protocol) "remplace"](https://tools.ietf.org/html/rfc3891)

- [Protocole SIP (Session Initiation Protocol) "mécanisme appelé"](https://tools.ietf.org/html/rfc3892)

Cette option suppose que le proxy SIP fait office de transfert et envoie un message de référence à l’SBC. Le SBC fait office de cessionnaire et gère le fait de s’assurer qu’il s’agit de générer une nouvelle proposition de transfert. Il existe deux cas possibles :

- L’appel est transféré vers un participant RTC externe. 
- L’appel est transféré d’un utilisateur de teams à un autre dans le même client via l’SBC. 

Si l’appel est transféré d’un utilisateur d’équipes à un autre par le biais de l’SBC, l’SBC est censé émettre une nouvelle invitation (en démarrant une nouvelle boîte de dialogue) pour la cible de transfert (l’utilisateur de Teams) en utilisant les informations reçues dans le message refer. 

Pour remplir les champs de destination et de transfert pour la transaction de la requête en interne, le proxy SIP doit transmettre ces informations à l’intérieur des en-têtes « REFER » et « EXPERTISÉ ». 

Le proxy SIP est appelé URI SIP, composé d’un nom de domaine complet (FQDN) du proxy SIP dans le nom d’hôte et l’une des méthodes suivantes :

- Un numéro de téléphone E. 164 dans la partie nom d’utilisateur de l’URI dans le cas où la cible de transfert est un numéro de téléphone ou

- paramètres x-m et x-t codant respectivement l’ID de client et l’MRI de la cible de transfert complète 

L’en-tête EXPERTISÉ est un URI SIP avec le service MRI encodé, ainsi que l’ID de locataire et les autres paramètres de contexte de transfert, comme indiqué dans le tableau suivant :

| Paramètre | Valeur | Description% |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MAGNETIQUE | Programme MRI complet de la cible de transfert/transfert tel qu’il est rempli par CC |
| x-t | ID de locataire | ID de locataire x-t ID de locataire facultatif tel qu’il est rempli par CC |
| x-TI | ID de corrélation du transfert | ID de corrélation de l’appel au cédant |
| x-TT | URI de l’appel cible de transfert | URI de remplacement d’appel encodé |

Dans le cas présent, la taille de l’en-tête refer peut contenir jusqu’à 400 symboles. L’SBC doit prendre en charge la gestion des messages qui se réfèrent à des symboles 400.

![Diagramme montrant plusieurs points de terminaison appelant une réponse provisoire](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Horloge de session

Le proxy SIP prend en charge (toujours) le minuteur de session sur les appels sans contournement mais ne l’offre pas sur les appels de contournement. L’utilisation du minuteur de session par SBC n’est pas obligatoire.

##  <a name="use-of-request-uri-parameter-userphone"></a>Utilisation du paramètre de requête-URI utilisateur = téléphone

Le serveur proxy SIP analyse l’URI de la demande et, si le paramètre utilisateur = téléphone est présent, le service gère le numéro de requête en tant que numéro de téléphone, en faisant correspondre le numéro à un utilisateur. Si le paramètre n’est pas présent, le proxy SIP applique des heuristiques pour déterminer le type d’utilisateur de requête-URI (numéro de téléphone ou adresse SIP).

Microsof recommande toujours d’appliquer le paramètre utilisateur = téléphone pour simplifier le processus de configuration d’appel.

## <a name="history-info-header"></a>Historique-en-tête d’information

L’en-tête History-Info est utilisé pour recibler les demandes SIP et « proposer (s) un mécanisme standard de capture des informations de l’historique des demandes pour permettre à un large éventail de services pour les réseaux et les utilisateurs finaux. » Pour plus d’informations, voir [RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt). Pour le système Microsoft Phone, cet en-tête est utilisé dans les scénarios SimulRing et de transfert d’appel.  

Dans le cadre de l’envoi, l’historique-informations est activé comme suit :

- Le proxy SIP insère un paramètre contenant le numéro de téléphone associé dans les entrées de l’historique des informations individuelles qui comprennent l’en-tête de l’historique des informations envoyées au contrôleur PSTN.  À l’aide de seules entrées dotées du paramètre numéro de téléphone, le contrôleur PSTN recrée un nouvel en-tête d’historique des informations et le transmet au fournisseur SIP Trunk via un proxy SIP.

- Historique : les en-têtes d’information seront ajoutés pour les cas de sonnerie simultanée et de transfert d’appel.

- Historique-les en-têtes d’information ne seront pas ajoutés aux cas de transfert d’appel.

- Une entrée d’historique individuelle dans l’en-tête historique reconstitué-info sera associée au paramètre de numéro de téléphone fourni avec le FQDN du routage direct (sip.pstnhub.microsoft.com) défini comme partie hôte de l’URI. un paramètre de’user = Phone’sera ajouté dans le cadre de l’URI SIP.  Tout autre paramètre associé à l’en-tête d’état d’origine, à l’exception des paramètres de contexte de téléphone, sera transmis dans l’en-tête de l’historique des informations.  Notez que les entrées privées (comme déterminé par les mécanismes définis dans la section 3,3 de RFC 4244) seront transmises en l’opération, car le fournisseur SIP Trunk est un homologue approuvé.

- Historique entrant-les informations sont ignorées.

Vous trouverez ci-après le format de l’en-tête d’information historique envoyé par le proxy SIP :

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Si l’appel a été redirigé plusieurs fois, les informations relatives à chaque redirection sont incluses avec la raison appropriée dans l’ordre chronologique.


Exemple d’en-tête :

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

L’historique des infos est protégé par un mécanisme TLS obligatoire. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Connexion SBC aux mécanismes de routage et de basculement directs

Voir la section mécanisme de basculement pour la signalisation SIP en [plan pour le routage direct](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Réessayer-après

Si un centre de routage direct est occupé, le service peut envoyer un message de nouvelle tentative après un intervalle d’une seconde à l’SBC. Lorsque l’SBC reçoit un message 503 avec un en-tête Retry-apres en réponse à une invitation, l’SBC doit mettre fin à cette connexion et essayer le prochain Centre de services Microsoft disponible. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>GLACE restart : un appel de dérivation multimédia a été transféré à un point de terminaison qui ne prend pas en charge la dérivation multimédia

L’SBC doit prendre en charge les redémarrages de glace comme décrit dans [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Le redémarrage dans le routage direct est implémenté conformément aux paragraphes suivants du RFC :

*Pour redémarrer la glace, un agent doit modifier à la fois le pwd-pwd et le ufrag de glace pour le flux multimédia dans une proposition.  Notez qu’il n’est pas possible d’utiliser un attribut de niveau session dans une offre, mais de fournir la même glace-pwd ou Ice-ufrag en tant qu’attribut de niveau multimédia dans une offre ultérieure.  Il ne s’agit pas d’un changement de mot de passe, d’une modification de sa représentation et n’entraîne pas de redémarrage de glace.*

*Un agent définit le reste des champs dans le SDP pour ce flux multimédia, comme dans le cas d’une proposition initiale du flux multimédia (voir la section 4,3).  Par conséquent, il est possible que l’ensemble des candidats ne comprenne qu’un certain nombre de candidats, aucun ou partie des candidats antérieurs à ce flux, et qu’il puisse y inclure un tout nouvel ensemble de candidatures collectées comme décrit dans la section 4.1.1.*

Si l’appel a été créé pour la première fois avec un contournement de média et si l’appel est transféré vers un client Skype entreprise, le routage direct doit insérer un processeur de média, car le routage direct ne peut pas être utilisé avec un client Skype entreprise avec un contournement de média. Le routage direct démarre le processus de redémarrage de la glace en modifiant les glaces-pwd et Ice-ufrag et en proposant de nouveaux éléments multimédias à une nouvelle invitation. 


