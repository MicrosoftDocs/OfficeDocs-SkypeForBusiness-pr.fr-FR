---
title: Planification du contournement de média avec le routage Direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lisez cette rubrique pour savoir comment planifier le contournement de média avec le routage d’un système téléphonique Direct.
ms.openlocfilehash: 39fc46fb95fef1d78f6f6cc946693f05c7c1f865
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631043"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planification du contournement de média avec le routage Direct

## <a name="about-media-bypass-with-direct-routing"></a>Sur le contournement de média avec le routage Direct

Le contournement de média vous permet de raccourcir le chemin d’accès du trafic multimédia et de réduire le nombre de tronçons en transit pour améliorer les performances. Avec le contournement de média est conservé entre le contrôleur de Session en périphérie (SBC) et le client au lieu de l’envoyer via le système téléphonique de Microsoft. Pour configurer media contournement de média, le contrôleur SBC et le client doivent être dans le même emplacement ou le réseau

Vous pouvez contrôler le contournement de média pour chaque SBC à l’aide de la commande **Set-CSOnlinePSTNGateway** avec le paramètre **- MediaBypass** la valeur true ou false. Si vous activez le contournement de média, cela ne signifie pas que tout le trafic multimédia est conservées au sein du réseau d’entreprise. Cet article décrit le flux des appels dans différents scénarios.    

Les diagrammes ci-dessous illustrent la différence de flux des appels avec et sans contournement de média.

Sans contournement de média, lorsqu’un client effectue ou reçoit un appel, la signalisation et média de flux entre le contrôleur SBC, le système téléphonique de Microsoft et le client d’équipes, comme illustré dans le diagramme suivant :

![Affiche la signalisation et les flux multimédias sans contournement de média](media/direct-routing-media-bypass-1.png)


Mais supposons qu’un utilisateur est dans la même construction ou réseau en tant que le contrôleur SBC. Supposons, par exemple, un utilisateur qui se trouve dans un bâtiment en fait Francfort un appel à un utilisateur PSTN : 

- **Sans media contournement de média**, media passera via Amsterdam ou Dublin (où les centres de données Microsoft sont déployés) et sur le contrôleur SBC à Francfort. 

  Le centre de données en Europe est sélectionnée, car le contrôleur SBC est en Europe, et Microsoft utilise le centre de données le plus proche pour le contrôleur SBC. Alors que cette approche n’affecte pas la qualité des appels en raison de l’optimisation du flux de trafic dans les réseaux Microsoft dans la plupart des régions, le trafic a une boucle inutile.     

- **Avec support de contournement**, il est conservé directement entre l’utilisateur équipes et le contrôleur SBC comme indiqué dans le diagramme suivant :

![Affiche la signalisation et les flux multimédias avec contournement de média](media/direct-routing-media-bypass-2.png)

Protocoles exploite appelées établissement ICE (Interactive Connectivity) sur le client d’équipes et ICE clair sur le contrôleur SBC du contournement de média. Ces protocoles permettent de routage Direct à utiliser le chemin d’accès des médias plus directe pour une qualité optimale. ICE et clair ICE sont des normes WebRTC. Pour plus d’informations sur ces protocoles, voir RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Flux des appels et la planification de pare-feu

Flux des appels et la planification de pare-feu dépend de si l’utilisateur possède un accès direct à l’adresse IP publique de le SBC, et si l’utilisateur est à l’intérieur ou à l’extérieur du réseau.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur dispose d’un accès direct à l’adresse IP publique de le SBC

Si l’utilisateur dispose d’un accès direct à l’adresse IP publique de le SBC, le flux d’appels est la suivante :

- Pour le contournement de média, le client équipes doit avoir accès à l’adresse IP publique de le SBC même à partir d’un réseau interne. Si media direct n’est pas souhaité, le média peut être transmis via le Transport de relais.

- Il s’agit de la solution recommandée lorsqu’un utilisateur est dans la même construction et/ou le réseau en tant que le contrôleur SBC : supprimer des composants de Cloud Microsoft à partir du chemin d’accès des médias.

- Flux de signalisation toujours via le nuage de Microsoft.

Le diagramme suivant illustre le flux des appels lorsque le contournement de média est activé, le client est interne et le client peut atteindre l’adresse IP publique de le SBC (media direct) : 

- Les flèches et les valeurs numériques des chemins d’accès respectent le document Microsoft équipes Online flux d’appels.

- La signalisation SIP prend toujours les chemins d’accès 4 et 4' (en fonction de la direction du trafic). Support reste local et prend 5 b de chemin d’accès.

![Flux d’appels affiche avec contournement de média activé, client interne et peut atteindre l’adresse IP publique de la Session Border Controller (media direct)](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de le SBC

La section suivante décrit flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de le SBC. 

Par exemple, supposons que l’utilisateur est externe, et l’administrateur de clients décidé de ne pas ouvrir l’adresse IP publique de le SBC pour tout le monde dans Internet, mais uniquement pour le Cloud Microsoft. Les composants internes du trafic peuvent être transmis via le relais de Transport équipes. Il s’agit de la configuration recommandée pour les utilisateurs en dehors du réseau d’entreprise. Dans ce cas, tenez compte des points suivants :

- Relais de Transport d’équipes sont utilisées.

- Pour le contournement de média, Microsoft utilise une version de relais de Transport qui requiert l’ouverture des ports 50 000 à 59 999 entre les équipes de relais de Transport et le contrôleur SBC (dans l’avenir, que nous prévoyons pour déplacer vers la version qui nécessite des ports uniquement 3478 et 3479).

- À des fins d’optimisation multimédia, Microsoft recommande l’ouverture de l’adresse IP publique de le SBC uniquement aux équipes Transport relais. Pour les clients en dehors du réseau d’entreprise, Microsoft recommande l’utilisation de relais de Transport au lieu d’atteindre l’adresse IP publique de le SBC directement.

Le diagramme suivant illustre le flux des appels lorsque le contournement de média est activé, le client est externe et le client ne peut pas joindre l’adresse IP publique de Session Border Controller (media est relayé par équipes Transport relais).

- Les flèches et les valeurs numériques des chemins d’accès respectent le document Microsoft équipes Online flux d’appels.

- Multimédia est relayé par le biais de chemins d’accès 3, 3', 4 et 4'

![Indique les flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de le SBC)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flux d’appels si un utilisateur est en dehors du réseau et a accès à l’adresse IP publique de le SBC

> [!NOTE]
> Il n’est pas une configuration recommandée, car il ne tire pas parti des équipes Transport relais. Au lieu de cela, vous devez envisager le scénario précédent où l’utilisateur n’a pas accès à l’adresse IP publique de le SBC. 

Le diagramme suivant illustre le flux des appels lorsque le contournement de média est activé, le client est externe et le client peut atteindre l’adresse IP publique de le SBC (media direct).

- Les flèches et les valeurs numériques des chemins d’accès respectent le document Microsoft équipes Online flux d’appels.

- La signalisation SIP prend toujours les chemins d’accès 3 et 3 » (en fonction de la direction du trafic). Flux multimédias à l’aide du chemin d’accès de 2.

![Indique les flux d’appels si l’utilisateur n’a pas accès à l’adresse IP publique de le SBC)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Utilisation des processeurs multimédia et relais de Transport

Il existe deux composants dans le Cloud Microsoft pouvant se trouver dans le chemin d’accès du trafic multimédia : processeurs multimédia et le relais de Transport. 

- Le processeur de média est un composant de face publique qui gère les médias dans les cas sans contournement et gère les médias pour les applications vocales.

   Des processeurs multimédia sont toujours dans le chemin d’accès pour les appels non contourné utilisateur final, mais jamais dans le chemin d’accès pour les appels ignorés. Des processeurs multimédia sont toujours dans le chemin d’accès pour toutes les applications vocales comme parcage d’appel, d’organisation standard automatique et files d’attente des appels.

- Le relais de Transport est utilisé pour se connecter au Service de Transport le plus proche pour envoyer le trafic en temps réel.

   Relais de transport peuvent ou ne peuvent pas être dans le chemin d’accès pour les appels ignorées--provenant ou destinés aux utilisateurs finaux--selon où est l’utilisateur et comment le réseau est configuré.

Le diagramme suivant illustre les deux flux d’appels – avec le contournement de média activé et le second avec support de contournement désactivé. Remarque le diagramme illustre uniquement le trafic provenant de--ou destiné à--les utilisateurs finaux.  
- Le contrôleur de support est un microservice dans Azure qui affecte des processeurs multimédia et crée des offres de protocole SDP (Session Description).

- Le Proxy SIP est un composant qui traduit la signalisation de REST HTTP utilisés dans les équipes pour SIP.    

![Affiche deux flux d’appels – avec le contournement de média activé et désactivé le second avec le contournement de média)](media/direct-routing-media-bypass-6.png)


Le tableau ci-dessous résume les différences entre les processeurs multimédia et le relais de Transport.

|    | Processeurs multimédia | Relais de transport|
| :--------------|:---------------|:------------|
Dans le chemin d’accès des médias pour les appels non contourné pour les utilisateurs finaux | Toujours | Jamais | 
Dans le chemin d’accès des médias pour les appels ignorés pour les utilisateurs finaux | Jamais | Si le client ne peut pas joindre le contrôleur SBC sur l’adresse IP publique | 
Dans le chemin d’accès des médias pour les applications vocales | Toujours | Jamais | 
Peut faire transcodage (B2BUA)\* | Oui | Non, seulement relaie audio entre les points de terminaison | 
Nombre d’instancess dans le monde et l’emplacement | 8 au total : 2 nous est et l’ouest ; 2 dans Amsterdam et Dublin ; 2 de Hong Kong et Singapour ; 2 au Japon (ajouté dans Q1CY2019)  | Plusieurs

La plage IP est 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254). 

\*Explication transcodage : 

- Processeur média est B2BUA, ce qui signifie qu’il peut modifier un codecs (par exemple, soie client équipes MP et G.711 entre MP et SBC).

- Relais de transport ne sont pas B2BUA, ce qui signifie que le codec ne change jamais entre le client et le contrôleur SBC--même si le trafic passe par le biais de relais.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Utiliser des équipes de relais de Transport dans les scénarios de réaffectation si jonction est configurée pour le média de contournement

Relais de Transport d’équipes sont toujours dans le chemin d’accès des médias dans les scénarios suivants :

- Appel est transmis à partir de 1:1 à un appel de groupe
- Appel sur le point d’un utilisateur fédéré d’équipes
- Appel est transféré ou transféré vers un Skype pour utilisateur professionnel

Enusre votre contrôleur SBC a accès aux relais de Transport comme décrit ci-dessous.    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a>Signalisation SIP : Noms de domaine complets et les ports du pare-feu

Pour la signalisation SIP, les exigences de nom de domaine complet et pare-feu sont les mêmes que pour les cas de non contourné. 

Les points de connexion pour le routage Direct sont les noms de domaine trois complets suivants :

- **sip.pstnhub.microsoft.com** – Global FQDN – doit être tenté en premier. Lorsque le contrôleur SBC envoie une demande pour résoudre ce nom, les serveurs DNS de Microsoft Azure renvoient une adresse IP pointant vers le centre de données Azure principal affecté à la SBC. L’affectation est basée sur des mesures de performances des centres de données et le contrôleur SBC proximité géographique. L’adresse IP retournée correspond au nom de domaine complet principal.

- **sip2.pstnhub.microsoft.com** – FQDN secondaire – géographiquement mappe à la seconde région priorité.

- **sip3.pstnhub.microsoft.com** – nom de domaine complet de troisième niveau – géographiquement correspond à la région de priorité de la troisième.

Vous devez placer ces trois noms de domaine complets pour :

- Offrent une expérience optimale (moins chargée et le plus proche du centre de données SBC affectée en interrogeant le premier nom de domaine complet).

- Assurer un basculement lorsqu’une connexion à partir d’un contrôleur SBC est établie avec un centre de données qui rencontre un problème temporaire. Pour plus d’informations, voir le mécanisme de basculement ci-dessous.


Les noms de domaine complets **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**et **sip3.pstnhub.microsoft.com** soient résolues sur une des adresses IP suivantes :
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Vous devez ouvrir des ports pour toutes les adresses IP dans votre pare-feu pour permettre le trafic entrant et sortant vers et depuis les adresses de signalisation. Si votre pare-feu prend en charge les noms DNS, nom de domaine complet **sip-all.pstnhub.microsoft.com** résout toutes les adresses IP ci-dessus. Vous devez utiliser les ports suivants :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| Proxy SIP | SBC | 1024 - 65535 | Défini sur le contrôleur SBC |
| SIP/TLS | SBC | Proxy SIP | Défini sur le contrôleur SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Le trafic multimédia : adresse IP et Port de plages

Le trafic multimédia est disposé entre le client SBC et les équipes si une connexion directe est disponible ou par le biais des équipes Transport relais si le client ne peut pas joindre le contrôleur SBC à l’aide de l’adresse IP publique.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Configuration requise pour le trafic multimédia direct (entre le client d’équipes et le contrôleur SBC) 

Le client doit avoir accès aux ports spécifiés (voir tableau) sur l’adresse IP publique de le SBC. 

Remarque : Si le client est dans un réseau interne, les données multimédias transitent à l’adresse IP publique de le SBC. Vous pouvez configurer hairpinning sur votre périphérique NAT pour le trafic quitte jamais le matériel de réseau d’entreprise.

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 50 000 – 50 019  | Défini sur le contrôleur SBC |
| UDP/SRTP | SBC | Client | Défini sur le contrôleur SBC | 50 000 – 50 019  |


Remarque : Si vous disposez d’un périphérique réseau qui traduit les ports source du client, assurez-vous que les ports traduits sont ouverts entre le matériel réseau et le contrôleur SBC. 

### <a name="requirements-for-using-transport-relays"></a>Conditions d’utilisation de relais de Transport

Relais de transport sont dans la même plage que des processeurs multimédia (pour les cas sans contournement) : 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254).

La plage de ports des équipes Transport relais est indiquée dans le tableau suivant :


| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Relais de transport | SBC | 50 000-59 999    | Défini sur le contrôleur SBC |
| UDP/SRTP | SBC | Relais de transport | Défini sur le contrôleur SBC | 50 000 – 59 9999, 3478, 3479     |


Remarque : Microsoft recommande au moins deux ports par appel simultané sur le contrôleur SBC. Étant donné que Microsoft a deux versions de relais de Transport, les éléments suivants sont requis :

- v4, qui peut fonctionner uniquement avec la plage de ports 50 000 à 59 999

- v6, qui fonctionne avec les ports 3478, 3479

À ce stade, le contournement de média prend en charge uniquement le version v4 de relais de Transport. Prise en charge de v6 présente à l’avenir. 

Vous devez ouvrir des ports 3478 et 3479 pour la transition. Microsoft prend en charge des relais de Transport v6 avec contournement de média, vous devrez pas reconfigurer votre équipement réseau ou les SBCs. 

### <a name="requirements-for-using-media-processors"></a>Configuration requise pour l’utilisation des processeurs multimédia

Des processeurs multimédia sont toujours dans le chemin d’accès des médias pour les applications vocales. Les exigences sont les mêmes que pour configuration sans contournement.


La plage d’IP pour le trafic multimédia est 52.112.0.0 /14 (adresses IP de 52.112.0.1 à 52.115.255.254).

La plage de ports des processeurs multimédia est indiquée dans le tableau suivant :

| Trafic | De | À | Port source | Port de destination|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Processeur média | SBC | 49 152 – 53 247    | Défini sur le contrôleur SBC |
| UDP/SRTP | SBC | Processeur média | Défini sur le contrôleur SBC | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Considérations relatives à la si vous avez Skype pour téléphones d’entreprise dans votre réseau  

Si vous avez tout Skype pour les points de terminaison Business dans votre réseau qui utilisent le routage Direct, par exemple, un utilisateur peut avoir un téléphone 3PIP qui repose sur Skype pour client Business--les équipes le contournement de média sur la jonction qui sert de ces utilisateurs doit être désactivé.

Vous pouvez créer une jonction distincte pour ces utilisateurs et lui affecter une stratégie de routage des communications vocales en ligne.

Étapes de configuration de niveau supérieur :

- Fractionner les utilisateurs par type – selon que l’utilisateur a un téléphone 3PIP ou non.

- Créer deux tronçons distincts avec différents noms de domaine complets : activée pour le contournement de média ; l’autres non. 

  Les jonctions pointent vers le même SBC. Les ports pour la signalisation SIP TLS doivent être différents. Les ports pour le média doivent être la même.

- Affecter la jonction appropriée en fonction du type de l’utilisateur dans la stratégie de routage des communications vocales en ligne.

L’exemple ci-dessous illustre cette logique.

| Ensemble d’utilisateurs | Nombre d’utilisateurs | Nom de domaine complet attribué dans OVRP de jonction | Le contournement de média activé |
| :------------ |:----------------- |:--------------|:--------------|
Utilisateurs avec des clients d’équipes et téléphones 3PIP | 20 | sbc1.contoso.com:5061 | false | 
Utilisateurs avec uniquement les points de terminaison équipes (y compris les nouveaux téléphones certifiés pour les équipes) | 980 | sbc2.contoso.com:5060 | true

Les jonctions peuvent pointer vers le même SBC avec la même adresse IP publique. La signalisation des ports sur le contrôleur SBC de TLS doivent être différents, comme illustré dans le diagramme suivant. Notez que vous devez vous assurer que votre certificat prend en charge les jonctions. SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou dispose d’un certificat générique.


![Affiche que les deux jonctions peuvent pointer vers le même SBC avec la même adresse IP publique)](media/direct-routing-media-bypass-7.png)

Pour plus d’informations sur la configuration des deux jonctions sur le même SBC, voir la documentation fournie par votre fournisseur SBC :

- AudioCodes
- Ruban
- NOTE-Systems (Anynode)   

## <a name="client-endpoints-supported-with-media-bypass"></a>Contournement des points de terminaison clients pris en charge avec support

Le contournement de média est pris en charge avec tous les systèmes d’extrémité équipes, à l’exception des clients Web équipes indéterminée. 

Si vos utilisateurs préfèrent équipes Web app dans Microsoft Edge, Google Chrome ou Mozilla Firefox, le contournement de média pour ces utilisateurs doit être désactivé. Nous allons présenter l’appeler à l’aide d’une jonction de contournement de média activé multimédia à l’avenir.   
 
## <a name="see-also"></a>Voir aussi

[Configurer le contournement de média avec le routage Direct](direct-routing-configure-media-bypass.md)



