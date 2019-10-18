---
title: Planifier le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Pour plus d’informations sur l’utilisation de la méthode de contournement multimédia avec le routage direct du système téléphonique, lisez cette rubrique.
ms.openlocfilehash: cdfeb5313416730c703a1d0f10e2c7ccdddee1cc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572156"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planifier le contournement de média avec un routage direct

## <a name="about-media-bypass-with-direct-routing"></a>À propos du contournement de média avec le routage direct

La dérivation de médias vous permet d’abréger le chemin du trafic multimédia et de réduire le nombre de tronçons en transit pour de meilleures performances. Par le biais du contournement du contenu multimédia, le contenu multimédia est maintenu entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système Microsoft Phone. Pour configurer la dérivation multimédia, l’SBC et le client doivent se trouver dans le même emplacement ou réseau.

Vous pouvez contrôler la dérivation multimédia pour chaque SBC en utilisant la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** défini sur true ou false. Cela ne signifie pas que le trafic multimédia restera dans le réseau d’entreprise. Cet article décrit le flux d’appels dans différents scénarios.    

Les diagrammes ci-dessous montrent la différence de flux d’appels avec et sans dérivation multimédia.

Sans dérivation multimédia, quand un client effectue ou reçoit un appel, la signalisation et le flux multimédia entre le SBC, le système Microsoft Phone et le client Teams, comme indiqué dans le schéma suivant :

![Affiche la signalisation et le flux multimédia sans contournement du support multimédia](media/direct-routing-media-bypass-1.png)


Par exemple, supposons qu’un utilisateur se trouve dans le même bâtiment ou réseau que l’SBC. Par exemple, supposons qu’un utilisateur participant à un bâtiment à Francfort effectue un appel vers un utilisateur RTC : 

- **Sans dérivation multimédia**, le contenu multimédia sera transmis par l’intermédiaire d’Amsterdam ou de Dublin (sur lequel sont déployés les centres de connaissances Microsoft) et de retour vers l’SBC à Francfort. 

  Le centre de donnees en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de donne le plus proche de l’SBC. Même si cette approche n’a aucun impact sur la qualité des appels en raison de l’optimisation du flux de trafic au sein de réseaux Microsoft dans la plupart des zones géographiques, le trafic comporte une boucle inutile.     

- Par le biais du **contournement du contenu multimédia**, le média est maintenu directement entre l’utilisateur teams et l’élément SBC, comme illustré dans le schéma suivant :

![Affiche le signalement et le flux multimédia avec une dérivation multimédia](media/direct-routing-media-bypass-2.png)

La fonction de contournement de média utilise des protocoles appelés interactifs (ICE) sur le client teams et ICE Lite sur l’SBC. Ces protocoles permettent le routage direct pour utiliser le chemin multimédia le plus direct pour une qualité optimale. ICE et ICE Lite sont des normes WebRTC. Pour plus d’informations sur ces protocoles, voir RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planification de flux d’appels et de pare-feu

Le flux d’appels et la planification de pare-feu varient selon que l’utilisateur a un accès direct à l’adresse IP publique de l’SBC et que l’utilisateur se trouve à l’intérieur ou à l’extérieur du réseau.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC

Si l’utilisateur a un accès direct à l’adresse IP publique de l’SBC, le flux des appels est le suivant :

- Pour le contournement du média multimédia, le client teams doit avoir accès à l’adresse IP publique de la SBC même à partir d’un réseau interne. Si les médias directs ne sont pas souhaités, le média peut circuler via des relais de transport.

- Il s’agit de la solution recommandée quand un utilisateur se trouve dans la même construction et/ou le même réseau que l’SBC : supprimer les composants Cloud Microsoft du chemin multimédia.

- Le signalement est toujours transmis via le Cloud Microsoft.

Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media) : 

- Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- Le signalement SIP accepte toujours les chemins 4 et 4 (selon la direction du trafic). Le contenu multimédia reste local et prend le chemin 5b.

![Flux d’appels avec contournement de média activé, le client est interne](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC

La description suivante décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC. 

Par exemple, supposons que l’utilisateur est externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique de l’SBC auprès de tout le monde sur Internet, mais uniquement dans Microsoft Cloud. Les composants internes du trafic peuvent être acheminés par le biais des relais de transport Teams. Il s’agit de la configuration recommandée pour les utilisateurs en dehors du réseau d’entreprise. Dans ce cas, tenez compte des points suivants :

- Des relais de transport d’équipes sont utilisés.

- Dans le cas d’une dérivation de média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture des ports 50 000 à 59 999 entre les relais de transport d’équipe et l’SBC (à l’avenir, nous envisageons de migrer vers la version qui ne nécessite que les ports 3478 et 3479).

- À des fins d’optimisation des éléments multimédias, Microsoft recommande l’ouverture de l’adresse IP publique de l’SBC uniquement aux relais de transport d’équipes. Pour les clients en dehors du réseau d’entreprise, Microsoft recommande l’utilisation de relais de transport au lieu de joindre directement l’adresse IP publique de la SBC.

Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de bordure de session (le contenu multimédia est relayée par teams Relay Relay).

- Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- Les médias sont relayés par le biais de chemins d’accès 3, 3, 4 et 4 '

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flux d’appels s’il se trouve hors du réseau et a accès à l’adresse IP publique de l’SBC

> [!NOTE]
> Il ne s’agit pas d’une configuration recommandée, car elle ne tire aucunement parti des relais de transport Teams. Au lieu de cela, vous devez prendre en considération le scénario précédent dans lequel l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC. 

Le diagramme suivant illustre le flux d’appels lorsque la dérivation de média est activée, que le client est externe et que le client peut accéder à l’adresse IP publique de l’SBC (direct Media).

- Les flèches et les valeurs numériques des chemins sont conformes à l’article [flux d’appels de Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- Le signalement SIP accepte toujours les chemins 3 et 3 (selon la direction du trafic). Flux multimédias utilisant Path 2.

![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de l’SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Utilisation de processeurs multimédias et de relais de transport

Il existe deux composants dans le Cloud Microsoft qui peuvent se trouver dans le chemin d’accès au média : processeurs multimédias et relais de transport. 

- Le processeur de média est un composant public qui gère le contenu multimédia en cas de non-contournement et gère le contenu multimédia pour les applications vocales.

   Les processeurs multimédias sont toujours dans le chemin d’accès pour les utilisateurs finaux sans ignorer les appels, mais jamais dans le chemin d’accès pour les appels ignorés. Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc d’appels, le standard automatique d’entreprise et les files d’attente d’appels.

- Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer du trafic en temps réel.

   Les relais de transport peuvent être ou ne pas se trouver dans le chemin d’accès pour les appels passés (provenant de ou destinés aux utilisateurs finaux), en fonction de l’endroit où se trouve l’utilisateur et du mode de configuration du réseau.

Le schéma suivant montre deux flux d’appels : l’un avec la dérivation multimédia est activée et le second avec contournement de média désactivé. Remarque le diagramme ne montre que le trafic provenant de--ou destinés aux utilisateurs finaux.  
- La manette de média est un microservice dans Azure qui affecte des processeurs de média et crée des offres SDP.

- Le proxy SIP est un composant qui convertit la signalisation HTTP REST utilisée dans teams pour SIP.    

![Flux d’appels avec contournement de média activé et désactivé](media/direct-routing-media-bypass-6.png)


Le tableau ci-dessous résume la différence entre les processeurs multimédias et les relais de transport.

|    | Processeurs multimédias | Relais de transport|
| :--------------|:---------------|:------------|
Chemin multimédia pour les appels sans contournement pour les utilisateurs finaux | Toujours | Interdire | 
Dans le chemin multimédia pour les appels ignorés pour les utilisateurs finaux | Interdire | Si le client ne peut pas accéder à l’SBC sur l’adresse IP publique | 
Dans le chemin multimédia pour les applications vocales | Toujours | Interdire | 
Peut faire un transcodage (B2BUA)\* | Oui | Non, ne relaye le son qu’entre les points de terminaison. | 
Nombre d’instances dans le monde et emplacement | 8 au total : 2 aux États-Unis et en ouest ; 2 dans Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon (ajouté dans Q1CY2019)  | Multiples

La plage d’adresses IP est 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254). 

\*Explication du transcodage : 

- Le processeur de média est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, soie du client teams vers MP et G. 711 entre MP et SBC).

- Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais changé entre le client et l’SBC, même si le trafic est transmis via des relais.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Utilisation de relais de transport d’équipes dans des scénarios d’escalade si le protocole Trunk est configuré pour une dérivation multimédia

Les relais de transport d’équipes sont toujours dans le chemin multimédia dans les scénarios suivants :

- Appel transféré de 1:1 vers un appel de groupe
- Appel vers un utilisateur d’équipes fédérées
- Appel transféré ou transféré vers un utilisateur Skype entreprise

Assurez-vous que votre SBC a accès aux relais de transport comme décrit ci-dessous.    


## <a name="sip-signaling-fqdns"></a>Signalisation SIP : noms de domaine complets

Pour la signalisation SIP, les exigences en matière de nom de domaine complet et de pare-feu sont les mêmes que pour les cas sans contournement. 

Le routage direct est fourni dans les environnements Office 365 suivants :
- Office 365
- GCC Office 365
- Office 365 (GCC High)
- Office 365 DoD en savoir plus sur les [environnements d’administration des États-Unis et d’office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Environnements Office 365 et Office 365 GCC

Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :

- **SIP.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) global, doit d’abord être essayé. Lorsque le SBC envoie une demande pour résoudre ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de noms principal Azure attribué à l’SBC. Cette affectation est basée sur les métriques de performance des centres de donnes et de proximité géographique de l’SBC. L’adresse IP renvoyée correspond au FQDN principal.

- **sip2.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) : il correspond à la deuxième région de priorité.

- nom de domaine complet (FQDN) **sip3.pstnhub.Microsoft.com** : il correspond géographiquement à la troisième région de priorité.

Pour pouvoir effectuer les opérations suivantes, vous devez placer ces trois noms de domaine complets :

- Offrir une plus meilleure version (moins chargée et la plus proche du centre de divertissement SBC attribué en interrogeant le premier nom de domaine complet).

- Fournir un basculement lorsqu’une connexion à partir d’un SBC est établie à un centre de donne qui rencontre un problème temporaire. Pour plus d’informations, consultez la section mécanisme de basculement ci-dessous.


Les noms de domaine complets **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**et **sip3.pstnhub.Microsoft.com** seront résolus vers l’une des adresses IP suivantes :
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu. Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet **SIP-All.pstnhub.Microsoft.com** est résolu sur toutes les adresses IP suivantes. 

### <a name="office-365-gcc-dod-environment"></a>Environnement DoD DoD dans Office 365

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**SIP.pstnhub.DoD.Teams.Microsoft.us** : FQDN global. Comme l’environnement Office 365 DoD existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.

Les noms de domaine complets (FQDN) – sip.pstnhub.dod.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :

- 52.127.64.33
- 52.127.68.34

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu sur toutes les adresses IP suivantes. 

### <a name="office-365-gcc-high-environment"></a>Environnement de grande qualité dans Office 365

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**SIP.pstnhub.gov.Teams.Microsoft.us** : FQDN global. Dans la mesure où l’environnement de grande qualité n’existe qu’aux centres de données américains, il n’y a pas de noms de domaine complets secondaires et tertiaires.

Les noms de domaine complets (FQDN) – sip.pstnhub.gov.teams.microsoft.us seront résolus vers l’une des adresses IP suivantes :

- 52.127.88.59
- 52.127.92.64

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu sur toutes les adresses IP suivantes. 

## <a name="sip-signaling-ports"></a>Signalisation SIP : ports

La configuration requise pour les ports est identique pour tous les environnements Office 365 dans lesquels le routage direct est disponible :
- Office 365
- GCC Office 365
- Office 365 (GCC High)
- Office 365 DoD

Vous devez utiliser les ports suivants :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| Proxy SIP | SBC | 1024-65535 | Définie sur l’SBC |
| SIP/TLS | SBC | Proxy SIP | Définie sur l’SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Trafic multimédia : plages d’adresses IP et de ports

Le trafic multimédia entre le client SBC et teams est disponible si la connectivité directe est disponible ou par le biais de relais de transport d’équipes si le client ne peut pas accéder à l’SBC en utilisant l’adresse IP publique.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Configuration requise pour le trafic multimédia direct (entre le client teams et l’SBC) 

Le client doit avoir accès aux ports spécifiés (voir table) sur l’adresse IP publique de l’SBC. 

Remarque : si le client se trouve dans un réseau interne, le média est transmis à l’adresse IP publique de l’SBC. Vous pouvez configurer Hairpinning sur votre appareil NAT de sorte que le trafic ne reste jamais sur l’équipement réseau d’entreprise.

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 50 000 – 50 019  | Définie sur l’SBC |
| UDP/SRTP | SBC | Client | Définie sur l’SBC | 50 000 – 50 019  |


Remarque : Si vous disposez d’un appareil réseau qui traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et l’SBC. 

### <a name="requirements-for-using-transport-relays"></a>Configuration requise pour l’utilisation des relais de transport

Les relais de transport sont dans la même plage que les processeurs de médias (pour les cas de non-contournement) : 

### <a name="office-365-and-office-365-gcc-environments"></a>Environnements Office 365 et Office 365 GCC

-52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Environnement DoD DoD dans Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Environnement de grande qualité dans Office 365

- 52.127.88.0/21


Le tableau suivant indique la plage de ports des relais de transport Teams (applicables à tous les environnements) :


| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Relais de transport | SBC | 50 000-59 999    | Définie sur l’SBC |
| UDP/SRTP | SBC | Relais de transport | Définie sur l’SBC | 50 000 – 59 999, 3478, 3479     |


Remarque : Microsoft recommande au moins deux ports par appel simultané sur l’SBC. Microsoft étant doté de deux versions de relais de transport, les informations suivantes sont nécessaires :

- v4, qui peut uniquement utiliser la plage de ports 50 000 à 59 999

- V6, qui est compatible avec les ports 3478, 3479

Pour le moment, le contournement de média ne prend en charge que la version v4 de relais de transport. La prise en charge de la version V6 sera bientôt prise en charge. 

Vous avez besoin d’ouvrir les ports 3478 et 3479 pour la transition. Lorsque Microsoft présente la prise en charge des relais de transport V6 avec le contournement de média, vous n’aurez pas besoin de reconfigurer votre équipement réseau ou SBCs. 

### <a name="requirements-for-using-media-processors"></a>Configuration requise pour l’utilisation de processeurs multimédias

Les processeurs multimédias sont toujours dans le chemin multimédia pour les applications vocales et pour les clients Web (par exemple, les clients teams dans Microsoft Edge ou Google Chrome). Les exigences sont les mêmes que pour la configuration sans contournement.


La plage d’adresses IP du trafic multimédia est 

### <a name="office-365-and-office-365-gcc-environments"></a>Environnements Office 365 et Office 365 GCC

-52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Environnement DoD DoD dans Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Environnement de grande qualité dans Office 365

- 52.127.88.0/21

Le tableau suivant indique la portée de port des processeurs multimédias (applicables à tous les environnements) :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Processeur de média | SBC | 49 152 – 53 247    | Définie sur l’SBC |
| UDP/SRTP | SBC | Processeur de média | Définie sur l’SBC | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Remarques Si vous avez des téléphones Skype entreprise sur votre réseau  

Si vous avez des points de terminaison Skype entreprise dans votre réseau qui utilisent le routage direct (par exemple, un utilisateur de teams peut avoir un téléphone 3PIP basé sur le client Skype entreprise), la dérivation multimédia sur le Trunk qui dessert ces utilisateurs doit être désactivée.

Vous pouvez créer un Trunk distinct pour ces utilisateurs et leur attribuer une stratégie de routage vocale en ligne.

Étapes de configuration de haut niveau :

- Fractionnez les utilisateurs par type, selon que l’utilisateur a ou non un téléphone 3PIP.

- Créez deux Trunks distinctes avec différents noms de domaine complets : l’un est activé pour la dérivation multimédia ; l’autre non. 

  Les deux Trunks pointent vers le même SBC. Les ports pour le signalement SIP TLS doivent être différents. Les ports pour le média doivent être identiques.

- Attribuez le Trunk approprié en fonction du type d’utilisateur dans la politique de routage de la voix en ligne.

L’exemple ci-dessous illustre cette logique.

| Ensemble d’utilisateurs | Nombre d’utilisateurs | Nom de domaine complet du Trunk affecté dans OVRP | Contournement de média activé |
| :------------ |:----------------- |:--------------|:--------------|
Utilisateurs avec des clients équipes et des téléphones 3PIP | CX3-20 | sbc1.contoso.com:5061 | false | 
Utilisateurs avec uniquement les points de terminaison équipes (y compris les nouveaux téléphones certifiés pour Teams) | 980 | sbc2.contoso.com:5060 | true

Les deux Trunks peuvent pointer sur la même SBC avec la même adresse IP publique. Les ports de signalisation TLS de l’SBC doivent être différents, comme indiqué dans le schéma suivant. Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks. Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.


![Affiche les deux liaisons peuvent pointer sur le même SBC avec la même adresse IP publique](media/direct-routing-media-bypass-7.png)

Pour plus d’informations sur la configuration de deux lignes sur le même SBC, voir la documentation fournie par votre fournisseur de SBC :

 - [Documentation de déploiement AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation relative au déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Points de terminaison client pris en charge avec l’exclusion de média

La dérivation de média est prise en charge avec tous les points de terminaison Teams.

Remarque pour les clients Web (teams Web App dans Microsoft Edge, Google Chrome ou Mozilla Firefox), l’appel est soumis à un contournement, même s’il a commencé en tant qu’appel de contournement. Ce problème se produit automatiquement et ne nécessite aucune action de l’administrateur. 
 
## <a name="see-also"></a>Voir aussi

[Configurer le contournement de média avec un routage direct](direct-routing-configure-media-bypass.md)



