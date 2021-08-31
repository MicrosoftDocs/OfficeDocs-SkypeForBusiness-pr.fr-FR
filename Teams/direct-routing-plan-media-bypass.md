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
description: Découvrez comment planifier la dérivation média avec Système téléphonique routage direct, ce qui vous permet de raccourcir le chemin d’accès au trafic multimédia et d’améliorer les performances.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8231a57d844539272c65709270b0a0477c50e214
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730483"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planifier le contournement de média avec un routage direct

## <a name="about-media-bypass-with-direct-routing"></a>À propos de la dérivation média avec le routage direct

La dérivation média vous permet de raccourcir le chemin d’accès au trafic de médias et de réduire le nombre de sauts en transit pour de meilleures performances. Avec la dérivation média, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via Téléphone Microsoft système informatique. Pour configurer la dérivation média, le SBC et le client doivent se trouver dans le même emplacement ou réseau.

Vous pouvez contrôler la dérivation média pour chaque SBC à l’aide de la commande **Set-CSOnlinePSTNGateway** avec le paramètre **-MediaBypass** définie sur true ou false. Si vous activez la dérivation média, cela ne signifie pas que tout le trafic de médias restera au sein du réseau d’entreprise. Cet article décrit le flux d’appels dans différents scénarios.

Les diagrammes ci-dessous illustrent la différence de flux d’appels avec et sans contournement des médias.

Sans contournement média, lorsqu’un client effectue ou reçoit un appel, le trafic de signalisation et le flux de médias entre le SBC, le système Téléphone Microsoft et le client Teams, comme illustré dans le diagramme suivant :

> [!div class="mx-imgBorder"]
> ![Affiche les signaux et le flux de médias sans contournement multimédia.](media/direct-routing-media-bypass-1.png)


Supposons toutefois qu’un utilisateur se trouve dans le même bâtiment ou le même réseau que le SBC. Par exemple, supposons qu’un utilisateur se trouve dans un bâtiment dans Le Monde appelle un utilisateur PSTN : 

- **Sans contournement** des médias, les médias circulent via Amsterdam ou Dublin (où les centres de données Microsoft sont déployés), puis reviennent au SBC dans Le Monde. 

  Le centre de données en Europe est sélectionné, car le SBC est en Europe et Microsoft utilise le centre de données le plus proche du SBC. Bien que cette approche n’affecte pas la qualité des appels en raison de l’optimisation du flux de trafic au sein des réseaux Microsoft dans la plupart des régions, le trafic présente une boucle inutile.     

- **Avec la dérivation** média, le média est conservé directement entre l Teams un utilisateur et le SBC, comme illustré dans le diagramme suivant :

  > [!div class="mx-imgBorder"]
  > ![Affiche la signalisation et le flux multimédia avec contournement des médias.](media/direct-routing-media-bypass-2.png)

La dérivation média s’appuie sur des protocoles appelés ice (Interactive Connectivity Connectivity Connectivity Connectivité) sur le client Teams et ICE sur le SBC. Ces protocoles permettent au routage direct d’utiliser le chemin de médias le plus direct pour une qualité optimale. ICE et ICE Lite sont des normes WebRTC. Pour plus d’informations sur ces protocoles, voir RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planification du flux d’appels et du pare-feu

La planification du flux d’appels et du pare-feu varie selon que l’utilisateur a un accès direct à l’adresse IP publique du SBC et si l’utilisateur est à l’intérieur ou à l’extérieur du réseau.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur dispose d’un accès direct à l’adresse IP publique du SBC

Si l’utilisateur dispose d’un accès direct à l’adresse IP publique du SBC, le flux d’appels est le suivant :

- Pour la dérivation média, Teams client doit avoir accès à l’adresse IP publique du SBC, même à partir d’un réseau interne. Si le média direct n’est pas souhaité, il peut être transmis via un relais de transport.

- Il s’agit de la solution recommandée lorsqu’un utilisateur se trouve dans le même bâtiment et/ou réseau que le SBC (supprimer les composants Microsoft Cloud du chemin de médias).

- Les signaux circulent toujours via le cloud Microsoft.

Le diagramme suivant montre le flux d’appels lorsque la dérivation média est activée, que le client est interne et que le client peut accéder à l’adresse IP publique du support SBC : 

- Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux Microsoft Teams’appel.](./microsoft-teams-online-call-flows.md)

- Le trafic de signalisation SIP prend toujours les chemins 4 et 4' (selon le sens de trafic). Les médias restent locaux et prennent le chemin 5b.

> [!div class="mx-imgBorder"]
> ![Présente le flux d’appels avec contournement multimédia activé, le client est interne.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC

Le tableau suivant décrit le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC. 

Par exemple, supposons que l’utilisateur soit externe et que l’administrateur client a décidé de ne pas ouvrir l’adresse IP publique du SBC à tous les utilisateurs d’Internet, mais uniquement au cloud Microsoft. Les composants internes du trafic peuvent être acheminés par le biais Teams relais de transport. Vous devez tenir compte des éléments suivants :

- Teams Les relais de transport sont utilisés.

- Pour la dérivation média, Microsoft utilise une version de relais de transport qui nécessite l’ouverture de ports 50 000 à 59 999 entre les relais de transport Teams et le SBC (à l’avenir, nous prévoyons de passer à la version nécessitant 3478-3481 ports).


Le diagramme suivant illustre le flux d’appels lorsque la dérivation média est activée, que le client est externe et que le client ne peut pas accéder à l’adresse IP publique du contrôleur de session en bordure (le média est relayé par Teams Relais de transport).

- Les flèches et les valeurs numériques des chemins d’accès sont conformes aux [flux Microsoft Teams’appel.](./microsoft-teams-online-call-flows.md)

- Le média est relayé par les chemins d’accès 3, 3', 4 et 4'

> [!div class="mx-imgBorder"]
> ![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flux d’appels si un utilisateur se trouve en dehors du réseau et a accès à l’adresse IP publique du SBC

> [!NOTE]
> Cette configuration n’est pas recommandée, car elle ne prend pas en Teams relais de transport. Au lieu de cela, vous devez tenir compte du scénario précédent où l’utilisateur n’a pas accès à l’adresse IP publique du SBC. 

Le diagramme suivant montre le flux d’appels lorsque la dérivation média est activée, que le client est externe et que le client peut atteindre l’adresse IP publique du support SBC.

- Les flèches et les valeurs numériques des chemins d’accès sont conformes à l’article [Microsoft Teams flux d’appels.](./microsoft-teams-online-call-flows.md)

- Le trafic de signalisation SIP prend toujours les chemins 3 et 3' (selon le sens du trafic). Flux multimédias en utilisant le chemin d’accès 2.

> [!div class="mx-imgBorder"]
> ![Affiche le flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique du SBC.](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Utilisation de processeurs multimédias et de relais de transport

Microsoft Cloud peut utiliser deux composants dans le chemin d’accès du trafic de médias : Processeurs de média et Relais de transport. 

- Le processeur de média est un composant public qui gère les éléments multimédias dans les cas qui ne contournent pas et gère les médias pour les applications vocales.

   Les processeurs multimédias sont toujours dans le chemin pour les appels sans contournement de l’utilisateur final, mais jamais dans le chemin pour les appels contournements. Les processeurs multimédias sont toujours dans le chemin d’accès de toutes les applications vocales, telles que le parc des appels, les Standard automatique de l’organisation et les files d’attente d’appels.

- Le relais de transport est utilisé pour se connecter au service de transport le plus proche pour envoyer le trafic en temps réel.

   Les relais de transport peuvent ou non se trouver dans le chemin d’accès des appels contournements (provenant ou destinés à des utilisateurs finaux), selon l’endroit où se trouve l’utilisateur et la manière dont le réseau est configuré.

Le diagramme suivant montre deux flux d’appels : un avec la dérivation média activée et la seconde avec la dérivation média désactivée.

> [!NOTE]
> Le diagramme illustre uniquement le trafic provenant d’utilisateurs - ou destinés à des utilisateurs finaux.  

- Le contrôleur de média est un microservice dans Azure qui attribue des processeurs multimédias et crée des offres SDP (Session Description Protocol).

- Le proxy SIP est un composant qui traduit le signalisation HTTP REST utilisé dans Teams en SIP.    

> [!div class="mx-imgBorder"]
> ![Affiche les flux d’appels avec la dérivation média activée et désactivée.](media/direct-routing-media-bypass-6.png)


Le tableau ci-dessous résume la différence entre les processeurs de média et les relais de transport.

|    | Processeurs multimédias | Relais de transport|
| :--------------|:---------------|:------------|
Chemin de médias pour les appels non contournements pour les utilisateurs finaux | Toujours | Si le client ne parviennent pas à joindre le processeur de média directement | 
Dans le chemin de médias pour les appels contournements pour les utilisateurs finaux | Jamais | Si le client ne peut pas accéder au SBC sur l’adresse IP publique | 
Dans le chemin multimédia des applications vocales | Toujours | Jamais | 
Can do transcoding (B2BUA)\* | Oui | Non, seul l’audio est relayé entre les points de terminaison | 
Nombre d’instances dans le monde et emplacement | 10 total : 2 dans la région Est et Ouest des États-Unis ; 2 à Amsterdam et Dublin ; 2 à Hong Kong et Singapour ; 2 au Japon ; 2 en Australie de l’Est et du Sud-est | Multiple

Les plages d’adresses IP sont les plus diverses :
- 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254)
- 52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254)

\* Explication de la transcodage : 

- Le processeur multimédia est B2BUA, ce qui signifie qu’il peut changer un codec (par exemple, SILK d’un client Teams en MP et G.711 entre MP et SBC).

- Les relais de transport ne sont pas B2BUA, ce qui signifie que le codec n’est jamais modifié entre le client et le SBC, même si le trafic est acheminé par relais.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Utilisation de processeurs Teams média si la ligne est configurée pour la dérivation média

Teams Les processeurs multimédias sont toujours insérés dans le chemin de médias dans les scénarios suivants :

- L’appel est recalé de 1:1 à un appel de groupe
- L’appel va être fédéré Teams utilisateur
- L’appel est transféré ou transféré à un Skype Entreprise utilisateur

Assurez-vous que votre SBC a accès aux plages Processeurs de média et Relais de transport, comme décrit ci-dessous.    


## <a name="sip-signaling-fqdns"></a>Signalisation SIP : FQDN

Pour le signalisation SIP, les exigences de nom de passe (FQDN) et de pare-feu sont identiques à ceux des cas non contourné. 

Un routage direct est proposé dans les environnements Microsoft 365 ou Office 365 suivants :
- Microsoft 365 ou Office 365
- Office 365 Cloud de la communauté du secteur public
- Office 365 Cloud de la communauté du secteur public Haute
- Office 365 DoD En savoir plus [sur les environnements Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) administration publique des États-Unis, tels que Cloud de la communauté du secteur public, Cloud de la communauté du secteur public Élevé et DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail

Les points de connexion pour le routage direct sont les trois FQDN suivants :

- **sip.pstnhub.microsoft.com** , vous devez d’abord essayer le FQDN global. Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de données Azure principal affecté au SBC. L’affectation est basée sur les mesures de performance des centres de données et la proximité géographique par rapport au SBC. L’adresse IP renvoyée correspond au FQDN principal.

- **sip2.pstnhub.microsoft.com** (FQDN secondaire) géographiquement à la région de deuxième priorité.

- **sip3.pstnhub.microsoft.com** – FQDN de l’situation géographique de la troisième région.

Vous devez placer ces trois FQDN pour :

- Offrez une expérience optimale (moins chargé et le plus proche du centre de données SBC attribué en interrogeant le premier FQDN).

- Offrez un échec lorsqu’une connexion à partir d’un SBC est établie vers un centre de données qui rencontre un problème temporaire. Pour plus d’informations, voir le mécanisme deover ci-dessous.


Les noms de **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** et sip3.pstnhub.microsoft.com sont  résolus pour les adresses IP des sous-réseaux suivants :
- 52.112.0.0/14
- 52.120.0.0/14

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP de votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation. Si votre pare-feu prend en charge les noms DNS, le sip-all.pstnhub.microsoft.com **de** noms de domaine (FQDN) est résolu pour tous ces sous-réseaux IP. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 Cloud de la communauté du secteur public Environnement DoD

Le point de connexion pour le routage direct est le FQDN suivant :

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Étant donné que l’Office 365 DoD existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.

Le sip.pstnhub.dod.teams.microsoft.us de sip.pstnhub.dod.teams.microsoft.us de votre FQDN sera résolu en une adresse IP provenant du sous-réseau suivant :

- 52.127.64.0/21

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP de votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.  Si votre pare-feu prend en charge les noms DNS, le sip.pstnhub.dod.teams.microsoft.us de noms de domaine (FQDN) est résolu pour tous ces sous-réseaux IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 Cloud de la communauté du secteur public environnement élevé

Le point de connexion pour le routage direct est le FQDN suivant :

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Étant donné que l Cloud de la communauté du secteur public de haute ligne existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.

Le problème de sip.pstnhub.gov.teams.microsoft.us de sip.pstnhub.gov.teams.microsoft.us sera résolu en tant qu’adresse IP provenant du sous-réseau suivant :

- 52.127.88.0/21

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP de votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.  Si votre pare-feu prend en charge les noms DNS, le sip.pstnhub.gov.teams.microsoft.us de noms de domaine (FQDN) est résolu pour tous ces sous-réseaux IP. 

## <a name="sip-signaling-ports"></a>Signalisation SIP : ports

Les exigences de port sont identiques pour tous Office 365 d’environnements de routage direct :
- Microsoft 365 ou Office 365
- Office 365 Cloud de la communauté du secteur public
- Office 365 Cloud de la communauté du secteur public Haute
- Office 365 DoD

Vous devez utiliser les ports suivants :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Défini sur le SBC |
| SIP/TLS | SBC | SIP Proxy | Défini sur le SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Trafic de médias : ip et plages de ports

Le trafic de médias est acheminé entre le client SBC et le client Teams si une connectivité directe est disponible ou via des relais de transport Teams si le client ne peut pas accéder au SBC à l’aide de l’adresse IP publique.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Exigences pour le trafic de médias directs (entre le client Teams et le SBC) 

Le client doit avoir accès aux ports spécifiés (voir tableau) sur l’adresse IP publique du SBC. 

> [!NOTE]
> Si le client se trouve dans un réseau interne, le média passe à l’adresse IP publique du SBC. Vous pouvez configurer l’épinglage de cheveux sur votre appareil NAT afin que le trafic ne quitte jamais l’équipement réseau d’entreprise.

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 3478-3481 et 49152 – 53247| Défini sur le SBC |
| UDP/SRTP | SBC | Client | Défini sur le SBC | 3478-3481 et 49152 – 53247  |


> [!NOTE]
> Si votre périphérique réseau traduit les ports sources du client, assurez-vous que les ports traduits sont ouverts entre l’équipement réseau et le SBC. 

### <a name="requirements-for-using-transport-relays"></a>Conditions requises pour l’utilisation de relais de transport

Les relais de transport sont dans la même plage que les processeurs multimédias (pour les cas sans contournement) : 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail

- 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 Cloud de la communauté du secteur public Environnement DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 Cloud de la communauté du secteur public environnement élevé

- 52.127.88.0/21


La plage de ports des Teams relais de transport (applicable à tous les environnements) est indiquée dans le tableau suivant :


| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Relais de transport | SBC | 50 000 -59 999    | Défini sur le SBC |
| UDP/SRTP | SBC | Relais de transport | Défini sur le SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft recommande au moins deux ports par appel simultané sur le SBC. Étant donné que Microsoft dispose de deux versions de relais de transport, les suivantes sont requises :
> 
> - v4, qui ne peut fonctionner qu’avec la plage de ports 50 000 à 59 999
> 
> - v6, qui fonctionne avec les ports 3478-3481

Pour l’instant, la dérivation média ne prend en charge que la version v4 des relais de transport. Nous introduirons la prise en charge de la v6 à l’avenir. 

Vous devez ouvrir les ports 3478-3481 pour la transition. Lorsque Microsoft introduit la prise en charge des relais de transport v6 avec la dérivation média, vous n’avez pas besoin de reconfigurer votre équipement réseau ou SBCS. 

### <a name="requirements-for-using-media-processors"></a>Exigences pour l’utilisation de processeurs multimédias

Les processeurs de média sont toujours dans le chemin de médias des applications vocales et des clients web (par exemple, Teams clients dans Edge ou Google Chrome). La configuration requise est la même que pour une configuration sans contournement.


La plage IP du trafic de médias est 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 et Office 365 Cloud de la communauté du secteur public de travail

- 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 Cloud de la communauté du secteur public Environnement DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 Cloud de la communauté du secteur public environnement élevé

- 52.127.88.0/21

La plage de ports des processeurs multimédias (applicable à tous les environnements) est indiquée dans le tableau suivant :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Processeur multimédia | SBC | 3478-3481 et 49 152 – 53 247    | Défini sur le SBC |
| UDP/SRTP | SBC | Processeur multimédia | Défini sur le SBC | 3478-3481 et 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurer des ligne distinctes pour la dérivation média et la dérivation non multimédia  

Si vous migrez vers la dérivation média à partir d’une dérivation non multimédia et souhaitez confirmer la fonctionnalité avant de migrer toute utilisation vers la dérivation média, vous pouvez créer une ligne distincte et une stratégie de routage vocale en ligne distinctes pour router vers la ligne de dérivation média et affecter à des utilisateurs spécifiques. 

Étapes de configuration générales :

- Identifiez les utilisateurs qui testent la dérivation média.

- Créez deux ligne distinctes avec différents FQDN : l’une activée pour la dérivation média ; l’autre non. 

  Les deux ligne pointent vers le même SBC. Les ports de signalisation SIP du TLS doivent être différents. Les ports pour les médias doivent être identiques.

- Créez une stratégie de routage voix en ligne et affectez la ligne de dérivation média aux itinéraires correspondants à l’utilisation PSTN pour cette stratégie.

- Affectez la nouvelle stratégie de routage voix en ligne aux utilisateurs que vous avez identifiés pour tester la dérivation média.

L’exemple ci-dessous illustre cette logique.

| Ensemble d’utilisateurs | Nombre d’utilisateurs | Trunk FQDN assigned in OVRP | Contournement multimédia activé |
| :------------ |:----------------- |:--------------|:--------------|
Utilisateurs avec ligne de contournement non multimédia | 980 | sbc1.contoso.com:5061 | false |
Utilisateurs avec ligne de dérivation média | 20 | sbc2.contoso.com:5060 | true | 

Les deux ligne peuvent pointer vers le même SBC avec la même adresse IP publique. Les ports de signalisation TLS sur le SBC doivent être différents, comme illustré dans le diagramme suivant. Notez que vous devez vous assurer que votre certificat prend en charge les deux ligne. En san san, vous devez avoir deux noms **(sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.

> [!div class="mx-imgBorder"]
> ![Affiche les deux ligne peut pointer vers le même SBC avec la même adresse IP publique.](media/direct-routing-media-bypass-7.png)

Pour plus d’informations sur la configuration de deux ligne sur le même SBC, consultez la documentation fournie par votre fournisseur SBC :

 - [Documentation sur le déploiement de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation de déploiement de Communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement des systèmes TE (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Points de terminaison clients pris en charge avec la dérivation média

La dérivation média est prise en charge avec tous les clients Teams bureau, les clients Android et iOS et les Teams Téléphone périphériques. 

Pour tous les autres points de terminaison qui ne supportent pas la dérivation média, nous convertirons l’appel en appel sans contournement, même s’il a été démarré en tant qu’appel de contournement. Cette situation se produit automatiquement et ne nécessite aucune action de l’administrateur. Cela inclut Skype Entreprise téléphones 3PIP et les clients web Teams qui supportent l’appel de routage direct (clients WebRTC s’exécutant sur Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Voir aussi

[Configurer le contournement de média avec un routage direct](direct-routing-configure-media-bypass.md)
