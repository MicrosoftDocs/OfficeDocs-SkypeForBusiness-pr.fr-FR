---
title: Planifier le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment planifier la déviation du trafic multimédia avec le routage direct du système téléphonique, ce qui vous permet de raccourcir le chemin du trafic multimédia et d’améliorer les performances.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea92103789927d35ae8bdd317987f32863d4d74e
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981789"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planifier le contournement de média avec un routage direct

## <a name="about-media-bypass-with-direct-routing"></a>À propos de la déviation du trafic multimédia avec le routage direct

La déviation du trafic multimédia vous permet de raccourcir le chemin du trafic multimédia et de réduire le nombre de sauts en transit pour de meilleures performances. Avec la déviation du trafic multimédia, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système téléphonique Microsoft. Pour configurer la déviation du trafic multimédia, le SBC et le client doivent se trouver au même emplacement ou au même réseau.

Vous pouvez contrôler la déviation du trafic multimédia pour chaque SBC à l’aide de la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** défini sur true ou false. Si vous activez la déviation du trafic multimédia, cela ne signifie pas que tout le trafic multimédia restera dans le réseau d’entreprise. Cet article décrit le flux d’appel dans différents scénarios.

Les diagrammes ci-dessous illustrent la différence dans le flux d’appels avec et sans déviation de média.

Sans déviation du trafic multimédia, lorsqu’un client effectue ou reçoit un appel, la signalisation et le trafic multimédia circulent entre le SBC, le système téléphonique Microsoft et le client Teams, comme illustré dans le diagramme suivant :

> [!div class="mx-imgBorder"]
> ![Affiche la signalisation et le flux multimédia sans déviation du trafic multimédia.](media/direct-routing-media-bypass-1.png)


Mais supposons qu’un utilisateur se trouve dans le même bâtiment ou réseau que le SBC. Par exemple, supposons qu’un utilisateur qui se trouve dans un bâtiment à Francfort passe un appel à un utilisateur RTC : 

- **Sans contournement des médias**, les médias circulent via Amsterdam ou Dublin (où les centres de données Microsoft sont déployés) et retournent au SBC de Francfort. 

  Le centre de données en Europe est sélectionné, car le SBC se trouve en Europe et Microsoft utilise le centre de données le plus proche du SBC. Bien que cette approche n’affecte pas la qualité des appels en raison de l’optimisation du flux de trafic au sein des réseaux Microsoft dans la plupart des zones géographiques, le trafic a une boucle inutile.     

- **Avec la déviation du trafic** multimédia, le média est conservé directement entre l’utilisateur Teams et le SBC, comme illustré dans le diagramme suivant :

  > [!div class="mx-imgBorder"]
  > ![Affiche la signalisation et le flux multimédia avec déviation du trafic multimédia.](media/direct-routing-media-bypass-2.png)

La déviation du trafic multimédia utilise des protocoles appelés Ice (Interactive Connectivity Establishment) sur le client Teams et ICE lite sur le SBC. Ces protocoles permettent au routage direct d’utiliser le chemin d’accès multimédia le plus direct pour une qualité optimale. ICE et ICE Lite sont des normes WebRTC. Pour plus d’informations sur ces protocoles, consultez RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planification du flux d’appels et du pare-feu

La planification du flux d’appels et du pare-feu varie selon que l’utilisateur a un accès direct à l’adresse IP publique du SBC et si l’utilisateur se trouve à l’intérieur ou à l’extérieur du réseau.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appel si l’utilisateur a un accès direct à l’adresse IP publique du SBC

Si l’utilisateur a un accès direct à l’adresse IP publique du SBC, le flux d’appel est le suivant :

- Pour la déviation du trafic multimédia, le client Teams doit avoir accès à l’adresse IP publique du SBC, même à partir d’un réseau interne. Si le média direct n’est pas souhaité, le média peut circuler via relais de transport.

- Il s’agit de la solution recommandée lorsqu’un utilisateur se trouve dans le même bâtiment et/ou réseau que le SBC : supprimez les composants Microsoft Cloud du chemin d’accès multimédia.

- La signalisation passe toujours par le cloud Microsoft.

Le diagramme suivant montre le flux d’appel lorsque la déviation du trafic multimédia est activée, que le client est interne et que le client peut atteindre l’adresse IP publique du SBC (média direct) : 

- Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux d’appels Microsoft Teams](./microsoft-teams-online-call-flows.md).

- La signalisation SIP prend toujours les chemins 4 et 4' (selon la direction du trafic). Le média reste local et prend le chemin 5b.

> [!div class="mx-imgBorder"]
> ![Affiche le flux d’appel avec la déviation du trafic multimédia activée, le client est interne.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appel si l’utilisateur n’a pas accès à l’adresse IP publique du SBC

La section suivante décrit le flux d’appel si l’utilisateur n’a pas accès à l’adresse IP publique du SBC. 

Par exemple, supposons que l’utilisateur est externe et que l’administrateur du locataire a décidé de ne pas ouvrir l’adresse IP publique du SBC à tous les utilisateurs d’Internet, mais uniquement à Microsoft Cloud. Les composants internes du trafic peuvent circuler via les relais de transport Teams. Vous devez tenir compte des éléments suivants :

- Les relais de transport Teams sont utilisés.

- Pour la déviation du trafic multimédia, Microsoft utilise une version de Relais de transport qui nécessite l’ouverture des ports 50 000 à 59 999 entre les relais de transport Teams et le SBC (à l’avenir, nous prévoyons de passer à la version qui nécessite des ports 3478-3481).


Le diagramme suivant montre le flux d’appel lorsque la déviation du trafic multimédia est activée, que le client est externe et que le client ne peut pas atteindre l’adresse IP publique du contrôleur de bordure de session (le média est relayé par relais de transport Teams).

- Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux d’appels Microsoft Teams](./microsoft-teams-online-call-flows.md).

- Le média est relayé via les chemins 3, 3', 4 et 4'

> [!div class="mx-imgBorder"]
> ![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flux d’appel si un utilisateur est en dehors du réseau et a accès à l’adresse IP publique du SBC

> [!NOTE]
> Il ne s’agit pas d’une configuration recommandée, car elle ne tire pas parti des relais de transport Teams. Au lieu de cela, vous devez envisager le scénario précédent où l’utilisateur n’a pas accès à l’adresse IP publique du SBC. 

Le diagramme suivant montre le flux d’appel lorsque la déviation du trafic multimédia est activée, que le client est externe et que le client peut atteindre l’adresse IP publique du SBC (média direct).

- Les flèches et les valeurs numériques des chemins d’accès sont conformes à l’article [Flux d’appels Microsoft Teams](./microsoft-teams-online-call-flows.md) .

- La signalisation SIP prend toujours les chemins 3 et 3' (selon la direction du trafic). Flux multimédias à l’aide du chemin 2.

> [!div class="mx-imgBorder"]
> ![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>Utilisation de processeurs multimédias et de relais de transport

Il existe deux composants dans le cloud Microsoft qui peuvent se trouver dans le chemin du trafic multimédia : les processeurs multimédias et les relais de transport. 

- Le processeur multimédia est un composant public qui gère les médias dans les cas sans contournement et gère les médias pour les applications vocales.

   Les processeurs multimédias sont toujours dans le chemin d’accès pour les appels non contournés de l’utilisateur final, mais jamais dans le chemin d’accès pour les appels contournés. Les processeurs multimédias sont toujours dans le chemin pour toutes les applications vocales telles que le parcage d’appels, le standard automatique organisationnel et les files d’attente d’appels.

- Le relais de transport est utilisé pour se connecter au service de transport le plus proche afin d’envoyer du trafic en temps réel.

   Les relais de transport peuvent ou non se trouver dans le chemin d’accès pour les appels contournés , provenant ou destinés aux utilisateurs finaux, selon l’emplacement de l’utilisateur et la façon dont le réseau est configuré.

Le diagramme suivant montre deux flux d’appels : l’un avec la déviation du trafic multimédia activée et l’autre avec la déviation du trafic multimédia désactivée.

> [!NOTE]
> Le diagramme illustre uniquement le trafic provenant ou destiné aux utilisateurs finaux.  

- Media Controller est un microservice dans Azure qui affecte des processeurs multimédias et crée des offres SDP (Session Description Protocol).

- Le proxy SIP est un composant qui traduit la signalisation REST HTTP utilisée dans Teams en SIP.    

> [!div class="mx-imgBorder"]
> ![Affiche les flux d’appels avec la déviation du trafic multimédia activée et désactivée.](media/direct-routing-media-bypass-6.png)


Le tableau ci-dessous résume la différence entre les processeurs multimédias et les relais de transport.

|  &nbsp; | Processeurs multimédias | Relais de transport|
| :--------------|:---------------|:------------|
|Dans le chemin d’accès multimédia pour les appels non contournés pour les utilisateurs finaux | Toujours | Si le client ne peut pas atteindre directement le processeur multimédia |
|Dans le chemin d’accès multimédia pour les appels contournés pour les utilisateurs finaux | Jamais | Si le client ne peut pas atteindre le SBC sur l’adresse IP publique |
|Dans le chemin d’accès multimédia pour les applications vocales | Toujours | Jamais |
|Peut effectuer un transcodage (B2BUA)\* | Oui | Non, relaye uniquement l’audio entre les points de terminaison |

Les plages d’adresses IP sont les suivantes :
- 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)
- 52.122.0.0/15 (adresses IP de 52.122.0.1 à 52.123.255.254)

\* Explication du transcodage : 

- Le processeur multimédia est B2BUA, ce qui signifie qu’il peut modifier un codec (par exemple, SILK du client Teams au mp mp et G.711 entre MP et SBC).

- Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais modifié entre le client et le SBC, même si le trafic circule via des relais.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Utilisation des processeurs multimédias Teams si la jonction est configurée pour la déviation du trafic multimédia

Les processeurs multimédias Teams sont toujours insérés dans le chemin d’accès multimédia dans les scénarios suivants :

- L’appel est réaffecté de 1:1 à un appel de groupe
- L’appel est destiné à un utilisateur Teams fédéré
- L’appel est transféré ou transféré à un utilisateur Skype Entreprise

Vérifiez que votre SBC a accès aux plages processeurs multimédias et relais de transport, comme décrit ci-dessous.    


## <a name="sip-signaling-fqdns"></a>Signalisation SIP : noms de domaine complets

Pour la signalisation SIP, les exigences de nom de domaine complet et de pare-feu sont les mêmes que pour les cas non contournés. 

Le routage direct est proposé dans les environnements Microsoft 365 ou Office 365 suivants :
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD En savoir plus sur [les environnements Office 365 et us Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Environnements Microsoft 365, Office 365 et Office 365 GCC

Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :

- **sip.pstnhub.microsoft.com** (nom de domaine complet global) doit d’abord être essayé. Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure retournent une adresse IP pointant vers le centre de données Azure principal affecté au SBC. L’affectation est basée sur les métriques de performances des centres de données et la proximité géographique du SBC. L’adresse IP retournée correspond au nom de domaine complet principal.

- **sip2.pstnhub.microsoft.com** ( nom de domaine complet secondaire) est mappé géographiquement à la deuxième région de priorité.

- **sip3.pstnhub.microsoft.com** ( nom de domaine complet tertiaire) correspond géographiquement à la troisième région prioritaire.

Vous devez placer ces trois noms de domaine complets pour :

- Fournir une expérience optimale (moins chargé et le plus proche du centre de données SBC affecté en interrogeant le premier nom de domaine complet).

- Fournir un basculement lorsqu’une connexion à partir d’un SBC est établie vers un centre de données qui rencontre un problème temporaire. Pour plus d’informations, consultez Mécanisme de basculement ci-dessous.


Les noms de domaine complets **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** et **sip3.pstnhub.microsoft.com** sont résolus en adresses IP à partir des sous-réseaux suivants :
- 52.112.0.0/14
- 52.122.0.0/15

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

### <a name="office-365-gcc-dod-environment"></a>Office 365 environnement Gcc DoD

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.dod.teams.microsoft.us** : nom de domaine complet global. Étant donné que l’environnement Office 365 DoD n’existe que dans les centres de données américains, il n’y a pas de FQDN secondaires et tertiaires.

Le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us sera résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.64.0/21

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu en tous ces sous-réseaux IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.gov.teams.microsoft.us** : nom de domaine complet global. Comme l’environnement GCC High existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.

Le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us sera résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.88.0/21

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu en tous ces sous-réseaux IP. 

## <a name="sip-signaling-ports"></a>Signalisation SIP : Ports

Les exigences de port sont les mêmes pour tous les environnements Office 365 où le routage direct est proposé :
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Vous devez utiliser les ports suivants :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Défini sur le SBC |
| SIP/TLS | SBC | SIP Proxy | Défini sur le SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Trafic multimédia : plages d’adresses IP et de ports

Le trafic multimédia circule entre le SBC et le client Teams si une connectivité directe est disponible ou via les relais de transport Teams si le client ne peut pas atteindre le SBC à l’aide de l’adresse IP publique.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Configuration requise pour le trafic multimédia direct (entre le client Teams et le SBC) 

Le client doit avoir accès aux ports spécifiés (voir le tableau) sur l’adresse IP publique du SBC. 

> [!NOTE]
> Si le client se trouve dans un réseau interne, le média circule vers l’adresse IP publique du SBC. Vous pouvez configurer l’épinglage sur votre appareil NAT afin que le trafic ne quitte jamais l’équipement réseau de l’entreprise.

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Client | SBC | 50000-50019| Défini sur le SBC |
| UDP/SRTP | SBC | Client | Défini sur le SBC | 50000-50019  |


> [!NOTE]
> Si vous disposez d’un périphérique réseau qui traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et le SBC. 

### <a name="requirements-for-using-transport-relays"></a>Configuration requise pour l’utilisation de relais de transport

Les relais de transport se trouvent dans la même plage que les processeurs multimédias (pour les cas sans contournement) : 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Environnements Microsoft 365, Office 365 et Office 365 GCC

- 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 environnement Gcc DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

- 52.127.88.0/21


La plage de ports des relais de transport Teams (applicable à tous les environnements) est indiquée dans le tableau suivant :


| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Relais de transport | SBC | 50 000 -59 999    | Défini sur le SBC |
| UDP/SRTP | SBC | Relais de transport | Défini sur le SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft recommande au moins deux ports par appel simultané sur le SBC. Étant donné que Microsoft dispose de deux versions de Relais de transport, les éléments suivants sont requis :
> 
> - v4, qui ne peut fonctionner qu’avec la plage de ports 50 000 à 59 999
> 
> - v6, qui fonctionne avec les ports 3478-3481

À l’heure actuelle, la déviation du trafic multimédia prend uniquement en charge la version v4 des relais de transport. Nous allons introduire la prise en charge de la version 6 à l’avenir. 

Vous devez ouvrir les ports 3478-3481 pour la transition. Lorsque Microsoft introduit la prise en charge des relais de transport v6 avec dérivation de média, vous n’avez pas besoin de reconfigurer votre équipement réseau ou vos SBC. 

### <a name="requirements-for-using-media-processors"></a>Configuration requise pour l’utilisation de processeurs multimédias

Les processeurs multimédias sont toujours dans le chemin d’accès multimédia pour les applications vocales et pour les clients Web (par exemple, les clients Teams dans Edge ou Google Chrome). Les exigences sont les mêmes que pour la configuration sans contournement.


La plage d’adresses IP pour le trafic multimédia est 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 et Office 365 environnements GCC

- 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 environnement Gcc DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

- 52.127.88.0/21

La plage de ports des processeurs multimédias (applicable à tous les environnements) est indiquée dans le tableau suivant :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Processeur multimédia | SBC | 3478-3481 et 49 152 – 53 247    | Défini sur le SBC |
| UDP/SRTP | SBC | Processeur multimédia | Défini sur le SBC | 3478-3481 et 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurer des jonctions distinctes pour le contournement du trafic multimédia et le contournement non multimédia  

Si vous effectuez une migration vers la déviation du trafic multimédia à partir d’un contournement non multimédia et que vous souhaitez confirmer la fonctionnalité avant de migrer toute l’utilisation vers le contournement multimédia, vous pouvez créer une jonction distincte et une stratégie de routage de la voix en ligne distincte pour acheminer vers la jonction de contournement multimédia et l’attribuer à des utilisateurs spécifiques. 

Étapes de configuration générales :

- Identifier les utilisateurs à tester la déviation du trafic multimédia.

- Créez deux jonctions distinctes avec des noms de domaine complets différents : l’une activée pour la déviation du trafic multimédia ; l’autre non. 

  Les deux jonctions pointent vers le même SBC. Les ports pour la signalisation SIP TLS doivent être différents. Les ports du média doivent être identiques.

- Créez une stratégie de routage vocal en ligne et affectez la jonction de contournement multimédia aux itinéraires correspondants associés à l’utilisation RTC pour cette stratégie.

- Affectez la nouvelle stratégie de routage vocal en ligne aux utilisateurs que vous avez identifiés pour tester la déviation du trafic multimédia.

L’exemple ci-dessous illustre cette logique.

| Ensemble d’utilisateurs | Nombre d’utilisateurs | Nom de domaine complet de jonction affecté dans OVRP | Contournement du trafic multimédia activé |
| :------------ |:----------------- |:--------------|:--------------|
| Utilisateurs avec jonction de contournement non multimédia | 980 | sbc1.contoso.com:5061 | false |
| Utilisateurs disposant d’une jonction de contournement de média | 20 | sbc2.contoso.com:5060 | true | 

Les deux jonctions peuvent pointer vers le même SBC avec la même adresse IP publique. Les ports de signalisation TLS sur le SBC doivent être différents, comme illustré dans le diagramme suivant. Notez que vous devez vous assurer que votre certificat prend en charge les deux jonctions. Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.

> [!div class="mx-imgBorder"]
> ![Montre que les deux jonctions peuvent pointer vers le même SBC avec la même adresse IP publique.](media/direct-routing-media-bypass-7.png)

Pour plus d’informations sur la configuration de deux jonctions sur le même SBC, consultez la documentation fournie par votre fournisseur SBC :

 - [Documentation sur le déploiement d’AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation de déploiement TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Points de terminaison clients pris en charge avec la déviation du trafic multimédia

La déviation du trafic multimédia est prise en charge avec tous les clients De bureau Teams autonomes, les clients Android et iOS et les appareils téléphoniques Teams. 

Pour tous les autres points de terminaison qui ne prennent pas en charge la déviation du trafic multimédia, nous allons convertir l’appel en non-contournement, même s’il a démarré en tant qu’appel de contournement. Cela se produit automatiquement et ne nécessite aucune action de la part de l’administrateur. Cela inclut les téléphones Skype Entreprise 3PIP et les clients web Teams qui prennent en charge les appels de routage direct (clients WebRTC s’exécutant sur Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Voir aussi

[Configurer le contournement de média avec un routage direct](direct-routing-configure-media-bypass.md)
