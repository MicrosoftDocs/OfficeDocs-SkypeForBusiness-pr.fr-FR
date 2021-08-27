---
title: Qualité des médias et performances de connectivité réseau
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Cette rubrique définit les conditions de performances du réseau pour les services Microsoft Teams et la façon dont vous pouvez choisir d’utiliser Internet ou ExpressRoute pour établir une connectivité entre votre réseau et Microsoft Teams en fonction de votre évaluation de la connectivité réseau. Si vous avez décidé de déployer Azure ExpressRoute pour une connectivité dédiée à Microsoft 365 ou Office 365, ce document fournit également des instructions sur la façon de planifier vos connexions ExpressRoute selon différents scénarios Microsoft Teams déploiement.
ms.openlocfilehash: 3699e225f69deda5fd69b2308dc50337a1d0b228
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618240"
---
# <a name="media-quality-and-network-connectivity-performance-in-microsoft-teams"></a>Qualité multimédia et performances de connectivité réseau dans Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique définit les conditions de performances du réseau pour les services Microsoft Teams et la façon dont vous pouvez choisir d’utiliser Internet ou ExpressRoute pour établir une connectivité entre votre réseau et Microsoft Teams en fonction de votre évaluation de la connectivité réseau. Si vous avez décidé de déployer Azure ExpressRoute pour une connectivité dédiée à Microsoft 365 ou Office 365, ce document fournit également des instructions sur la façon de planifier vos connexions ExpressRoute selon différents scénarios Microsoft Teams déploiement.
  
La qualité multimédia Real-Time (audio, vidéo et partage d’applications) sur IP est largement impactée par la qualité de la connectivité réseau de bout en bout. Pour optimiser Microsoft Teams qualité multimédia, vous devez vous assurer qu’il existe une connexion de haute qualité entre le réseau de votre entreprise et Microsoft Teams. La meilleure façon d’y parvenir est de configurer la connectivité de votre réseau interne et du cloud en fonction de la capacité de votre réseau à s’adapter au volume du trafic de pointe pour les Microsoft Teams sur toutes les connexions.
  
Azure ExpressRoute n’est pas obligatoire pour les services Microsoft 365 et Office 365, Microsoft Teams. Toutefois, Azure ExpressRoute est l’une des options de déploiement disponibles qui vous aideront à vous assurer que la connectivité à Microsoft 365 ou Office 365 répond aux exigences de performances réseau d’Microsoft Teams et garantit une qualité multimédia Microsoft Teams optimale.
  
> [!TIP]
> Bien que cette rubrique fournit des conseils globaux sur les performances réseau, des instructions complètes pour l’évaluation du réseau ne sont pas du tout dans le cadre de ce document. Pour trouver la liste des partenaires Microsoft Teams qui peuvent vous aider à mesurer les performances réseau dans le cadre d’une évaluation approfondie et complète du réseau, visitez [Skype Entreprise solutions](http://partnersolutions.skypeforbusiness.com/)partenaires. 
  
## <a name="network-connectivity-requirements-to-microsoft-teams"></a>Conditions requises de connectivité réseau pour Microsoft Teams

### <a name="factors-that-impact-microsoft-teams-media-quality"></a>Facteurs qui ont un impact Microsoft Teams qualité multimédia

De nombreux facteurs contribuent à la qualité Microsoft Teams Real-Time multimédia (audio, vidéo et partage d’applications) incluant les périphériques utilisés, l’environnement et la connectivité réseau. 
  
#### <a name="devices"></a>Appareils

Dans une session Real-Time média, les périphériques de capture et de rendu utilisés par tous les participants, tels que des casques et des webcams, ont un fort impact sur la qualité audio et vidéo globale. Les périphériques de qualité inférieure ou dont les pilotes sont incorrects produiront globalement des sons et des images de moins bonne qualité. Les périphériques certifiés ou de bonne qualité contribuent à l’annulation de l’écho, au filtrage du bruit et à la résolution vidéo et réduisent la latence.
  
Bien que des périphériques multimédias audio et vidéo certifiés ne sont pas obligatoires, il est vivement recommandé d’avoir des périphériques certifiés pour Microsoft Teams d’optimiser l’expérience multimédia. Pour obtenir la liste de tous Microsoft Teams certifiés, consultez Téléphones et [périphériques pour Skype Entreprise.](../../SfbPartnerCertification/certification/devices-ip-phones.md) Vous pouvez utiliser le tableau de bord [Microsoft Teams](/microsoftteams/turning-on-and-using-call-quality-dashboard)qualité des appels, qui se trouve dans le Centre d’administration **Skype Entreprise,** pour vérifier que les périphériques utilisés fonctionnent correctement et surveiller la qualité des médias audio et vidéo.
  
> [!TIP]
> **Un périphérique certifié est requis pour optimiser la qualité** Skype Entreprise qualité multimédia optimale.
  
Il est important de savoir que tous les périphériques multimédias, clients Microsoft Teams et serveurs Skype Entreprise par lesquels Real-Time les flux multimédias présentent une certaine quantité de latence. La latence du traitement des périphériques et logiciels, de même que la latence du réseau, ont un fort impact sur la latence globale de bout en bout et contribuent à cette dernière.
  
#### <a name="environment"></a>Environnement

L’environnement dans lequel les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs appelant à partir d’un environnement bruyant auront de l’écho, un son tapé et un son difficilement clair. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour obtenir une image plus claire de l’expérience audio et vidéo d’un utilisateur, utilisez l’application Outils Skype Entreprise Options périphérique audio ou périphérique vidéo pour apporter des modifications au périphérique utilisé et personnaliser ses  >    >   paramètres. 

#### <a name="network"></a>Réseau

La qualité des médias Real-Time sur le réseau IP est largement impactée par la qualité de la connectivité du réseau, mais surtout par la quantité de :
  
- **Latence** C’est le temps d’obtenir un paquet IP du point A au point B sur le réseau. Ce retard de propagation sur le réseau est lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge des divers routeurs entre les deux. La latence se mesure en durée à sens inverse ou Durée de l’aller-retour (Round-trip Time, RTT).
    
- **Perte de paquets** Souvent définie comme le pourcentage de paquets perdus dans une période donnée. La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus, pratiquement sans impact, aux pertes en rafale dos-à-dos à l’origine de coupures audio complètes.
    
- **Gigue entre les arrivées de paquets ou simplement gigue** Il s’agit de la variation moyenne de délai entre les paquets successifs. La plupart des logiciels de VoIP modernes, Microsoft Teams pouvez s’adapter à certains niveaux de gigue grâce à la mise en mémoire tampon. C’est seulement lorsque la gigue est supérieure au tampon qu’un participant constatera une gigue.
    
> [!NOTE]
>  La mise en mémoire tampon pour la gigue augmente la latence de bout en bout.
  
Avec un grand nombre de sessions multimédia Microsoft Teams Real-Time simultanées et un autre trafic réseau généré par d’autres services Microsoft 365 ou Office 365 et d’autres applications métier, il est essentiel de s’assurer que la bande passante est suffisante sur l’ensemble du chemin réseau qui connecte votre réseau au service Microsoft Teams pour éviter l’encombrement du réseau et garantir une excellente qualité multimédia Real-Time multimédia (audio, vidéo et partage d’applications). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Mise en œuvre de la qualité de service (QoS) sur des réseaux encombrés

De plus, l’encombrement du trafic sur un réseau a une incidence considérable sur la qualité multimédia. Pour autoriser les paquets audio et vidéo à se déplacer plus rapidement sur le réseau et à être prioritaires sur tout autre trafic sur un réseau encombré, la qualité de service (QoS) peut aider à fournir une expérience utilisateur optimale pour les communications audio et vidéo.
  
QoS vous permet d’attribuer des priorités plus élevées aux paquets réseau qui transportent des données audio ou vidéo. En attribuant une priorité plus élevée à ces paquets, les communications audio et vidéo sont susceptibles de se déplacer plus rapidement et avec moins d’interruption que les sessions réseau impliquant des éléments tels que des transferts de fichiers, la navigation web ou des sauvegardes de bases de données. En effet, les paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données par défaut se voit attribuer la priorité « meilleur effort » et l’impact de l’encombrement du réseau est alors moins important. Si vous n’attribuez pas une priorité plus élevée aux paquets multimédia (audio, vidéo et partage d’applications) et que vous ne les affectez pas au niveau « meilleur effort », ils seront également traitées avec tout autre trafic réseau. En fonction de l’encombrement du réseau, cela risque potentiellement d’entraîner une baisse de la qualité audio et vidéo pour vos utilisateurs.
  
Il est vivement recommandé d’implémenter QoS sur votre réseau pour vous assurer que l’encombrement du réseau au sein de votre réseau n’aura aucun impact. Toutefois, pour que cela soit le plus impact possible, tous les points de terminaison réseau doivent prendre en charge QoS, ce qui signifie que tous les points de terminaison doivent respecter le marquage et la hiér donc QoS. Microsoft Teams services respectent le marquage et la hiérérisation QoS au sein du réseau Microsoft. Toutefois, le trafic acheminé via une connexion publique telle qu’Internet entre votre réseau d’entreprise et le réseau Microsoft ne conserve pas les marquages et les priorités QoS. Les connexions privées entre votre réseau et Microsoft 365 ou Office 365 à l’aide [d’Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) offrent une solution de déploiement qui conserve les marquages et les priorités QoS, ce qui augmente à son tour la qualité audio et vidéo globale pour vos utilisateurs finaux.
  
## <a name="network-performance-requirements-to-connect-to-microsoft-teams"></a>Conditions requises de performances réseau pour la connexion à Microsoft Teams
<a name="bkNetworkPerf"> </a>

Skype Entreprise Real-Time les médias parcourt un grand nombre de périphériques, d’applications client, de logiciels serveurs et de réseaux. La latence de bout en bout des Real-Time multimédias représente la quantité totale de latence introduite sur l’ensemble des composants et des segments réseau. La qualité de la connexion réseau de bout en bout est déterminée par le segment de réseau dont la qualité est la moins élevée. Ce segment agit comme un goulot d’étranglement pour ce trafic réseau.
  
Le diagramme suivant illustre le flux audio à sens sensé d’une conférence d’Microsoft Teams participant à un autre.
  
![Flow d’appel ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Dans ce scénario de conférence, le chemin multimédia est constitué des segments réseau suivants :
  
1. **Connexion de l’utilisateur 1 au réseau de périphérie Microsoft** Cela inclut généralement une connexion réseau telle que WiFi ou Ethernet, la connexion WAN entre l’utilisateur 1 et le point de sortie d’Internet (votre périphérique de réseau de périphérie), et la connexion Internet entre votre réseau de périphérie et celui de Microsoft.
    
2. **Connexion au sein du réseau Microsoft** Il s’agit de la Microsoft Edge au Microsoft Teams centre de données, dans lequel les serveurs de téléconférence A/V sont utilisés.
    
3. **Connexion au sein du réseau Microsoft** Cela se trouve entre le Microsoft Teams de données et le réseau de périphérie Microsoft.
    
4. **Connexion entre le réseau de périphérie Microsoft et l’utilisateur 2** Cela inclut la connexion Entre votre réseau de périphérie et celui de Microsoft, la connexion WAN entre l’utilisateur 2 et le point de sortie d’Internet (votre réseau de réseau) et une connexion réseau telle qu’une connexion WiFi ou Ethernet.
    
Le diagramme suivant illustre la répartition des composants et des segments réseau d’un Microsoft Teams un appel PSTN :
  
![Appels d’opérateur PSTN ExpressRoute Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Dans un scénario d’appel PSTN, le chemin multimédia passe par les segments réseau suivants :
  
1. **Connexion d’Skype Entreprise appelant client au bord du réseau Microsoft** Cela comprend généralement une connexion réseau telle que WiFi ou Ethernet, la connexion WAN entre l’appelant client Skype Entreprise et le point de sortie d’Internet (votre périphérique de réseau de périphérie), et la connexion Internet entre votre réseau de périphérie et celui de Microsoft.
    
2. **Connexion au sein du réseau Microsoft** Cette relation s’est Microsoft Edge au Microsoft Teams centre de données, dans lequel un serveur de médiation est utilisé.
    
3. **Connexion au sein du réseau Microsoft** Cela se trouve entre le Microsoft Teams de données et le réseau de périphérie Microsoft.
    
4. Connexion entre le réseau Microsoft et les partenaires fournisseurs de **services PSTN** Il s’agit de la connexion qui existe pour placer un appel PSTN à partir du client Skype Entreprise extérieur au réseau Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Conditions requises de performances réseau entre Skype Entreprise client et le réseau de périphérie Microsoft
<a name="bkSfBClienttoEdge"></a>

Pour optimiser Skype Entreprise qualité multimédia, les objectifs ou seuils de mesure de performances suivants sont requis pour une connexion entre le réseau de votre entreprise et le réseau de périphérie Microsoft. Ce segment du réseau comprend votre réseau interne, ce qui inclut toutes les connexions WiFi et Ethernet, tout le trafic de site à site de la société via une connexion WAN, par exemple MPLS (Multiprotocol Label Switching), ainsi que les connexions partenaires Internet ou ExpressRoute vers le réseau de périphérie Microsoft.
  
> [!CAUTION]
> **La connectivité entre un client Skype Entreprise sur votre réseau d’entreprise et les services Microsoft 365 ou Office 365 doit répondre aux conditions et aux seuils de performances réseau suivantes.**

|**Mesure** <br/> |**Target (Cible)** <br/> |
|:-----|:-----|
|Latence (à sens aller)  <br/> |< 50 ms  <br/> |
|Latence (RTT ou Durée de l’aller-retour)  <br/> |< 100 ms  <br/> |
|Perte de paquets en rafale  <br/> |<10 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |<1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |<30 ms sur un intervalle de 15 s  <br/> |
|Réordentation des paquets  <br/> |<paquets hors commande à 0,05 %  <br/> |
   
 **Autres conditions requises pour les objectifs de performances :**
  
- Le réseau Microsoft dispose de plus de 160 réseaux de périphérie dans le monde. Nous travaillons avec les principaux fournisseurs de services Internet (FSI) au monde par le biais de ces sites de périphérie. L’objectif de mesure de latence présumait que le ou les sites de votre entreprise et les bords Microsoft se sont situés sur le même continent.
    
- Les sites de votre entreprise et la connexion au réseau de périphérie Microsoft incluent un accès réseau de premier saut, qui peut être WiFi ou une autre technologie sans fil. 
    
- L’objectif de performance réseau présumait une planification appropriée de la bande passante et/ou de la qualité de service. En d’autres termes, cela s’applique directement au trafic Skype Entreprise Real-Time multimédia lorsque la connexion réseau est sous une charge de pointe.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Conditions requises de performances réseau entre votre réseau de périphérie et le réseau de périphérie Microsoft
<a name="bkYourNetworkEdge"> </a>

Voici les objectifs ou seuils de performance réseau requis pour la connexion entre votre réseau de périphérie et le réseau de périphérie Microsoft. Ce segment du réseau exclut le réseau interne ou le WAN du client et est conçu comme conseil pour tester votre trafic réseau envoyé sur Internet ou via un réseau partenaire ExpressRoute et peut également être utilisé pour négocier un contrat de niveau de service (SLA) avec votre fournisseur ExpressRoute.
  
> [!CAUTION]
> **La connectivité entre le réseau de votre réseau de votre entreprise et le réseau de périphérie Microsoft doit répondre aux exigences et aux seuils de performances réseau suivantes.**

|**Mesure** <br/> |**Target (Cible)** <br/> |
|:-----|:-----|
|Latence (à sens aller)  <br/> |< 30 ms  <br/> |
|Latence (RTT)  <br/> |< 60 ms  <br/> |
|Perte de paquets en rafale  <br/> |<1 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |<0,1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |<15 ms sur un intervalle de 15 s  <br/> |
|Réordentation des paquets  <br/> |<paquets pré-commandés de 0,01 %  <br/> |
   
 **Autres conditions requises pour les objectifs de performances :**
  
- L’objectif de performance nécessite que la connexion entre l’un des réseaux de votre entreprise et son réseau de périphérie Microsoft le plus proche soit sur le même continent.
    
- L’objectif de performance réseau présumait une planification appropriée de la bande passante et/ou de la qualité de service. Cela s’applique également Skype Entreprise Real-Time trafic multimédia lorsque la connexion réseau est sous une charge de pointe. Pour une bande passante appropriée et une planification de la QoS, reportez-vous à ExpressRoute et [QoS dans Microsoft Teams.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Mesure des performances du réseau
<a name="bkNetworkPerf"> </a>

Pour mesurer les performances réelles du réseau, notamment la latence et la perte de paquets, entre un site réseau de l’entreprise et un réseau de périphérie, vous pouvez utiliser des outils tels que ping, pour tester un ensemble de services de relais multimédia Skype Entreprise s’exécutant à partir des sites de centre de données et Microsoft Edge. 

>[!NOTE]
> La mesure des performances réseau via la commande ping (ICMP) n’est pas efficace. Pour cette raison, l’adresse IP anycast ci-dessous cessera de répondre aux demandes ICMP à partir du mois de janvier 2020. Pour mesurer efficacement les performance du réseau, Microsoft recommande l’outil [d’assesment réseau.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Pour tester les connexions Internet au réseau Microsoft, il est recommandé de tester par rapport aux VIP suivants des relais Skype Entreprise multimédias. La *VIP Anycast*  se résout à l’adresse IP d’un relais multimédia sur un site de réseau de périphérie Microsoft le plus proche de l’emplacement du test.
  

|**Adresse IP** <br/> |**Type** <br/> |**Emplacement** <br/>|
|:-----|:-----|:-----|
|13.107.8.2  <br/> |VIP  <br/> |Adresse IP Anycast dans le monde entier  <br/> |
   
 **Voici quelques recommandations de haut niveau à suivre pour évaluer les performances du réseau :**
  
- Vous devez évaluer votre réseau interne et les connexions à Microsoft 365 ou Office 365.
    
- Vous devez évaluer et collecter des données pour l’ensemble de vos réseaux sur une période prolongée. Nous vous recommandons d’effectuer vos tests de performances réseau sur une période minimale d’une semaine, afin de voir les modes d’utilisation pour tous les jours et heures d’ouverture. Cela vous indique les heures de pointe.
    
- Vous devez prendre plusieurs échantillons des mesures de performances réseau. Nous vous recommandons de prendre une mesure toutes les 10 minutes à partir d’un site de l’entreprise sur l’ensemble de la période de collecte de données. Pour comparer les Microsoft Teams performances réseau requises, prenez la valeur de mesure du 90e centile dans cet échantillon de jeu de données. 
    
- Vous devez évaluer en permanence les performances du réseau. L’utilisation du réseau varie dans le temps en fonction des changements de modes d’utilisation, de nouvelles applications d’entreprise qui utilisent une bande passante importante et des modifications apportées aux emplacements organisationnels ou physiques de votre entreprise. Il est important de surveiller en permanence les performances de votre réseau par rapport à ces conditions et objectifs/seuils de performances réseau, et de faire les ajustements nécessaires pour garantir la qualité multimédia la plus optimale Real-Time réseau. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Mesure des performances du réseau à l’aide de VMs Azure
<a name="bkNetworkPerf"> </a>

Au lieu de tester les résultats par rapport aux sites de réseau de périphérie Microsoft, il existe des solutions d’évaluation du réseau de Skype Entreprise clients et partenaires qui utilisent la configuration de test pour les services dans le cloud Microsoft Azure. Dans ces solutions, les outils d’évaluation du réseau testent la latence, la perte de paquets et la gigue par rapport à des points de terminaison personnalisés qui sont configurer en tant que service dans le cloud Azure. Par conséquent, le trafic réseau test est parcourt un autre segment réseau, qui est la connexion au sein du réseau Microsoft entre les réseaux de réseau et les centres de données Azure qui hébergent le service d’évaluation du réseau.
  
Pour les solutions d’évaluation du réseau basées sur des services de test hébergés par Azure. Nous vous recommandons d’effectuer l’évaluation du réseau au sein du pays et/ou de la région. Par exemple, pour les sites des clients de l’est des États-Unis, l’évaluation doit être effectuée par rapport à une instance du service de test hébergée dans la région du centre de données Azure de l’est des États-Unis. 
  
Voici les objectifs de latence (RTT) pour la configuration de l’évaluation du réseau basée sur le service Azure. Les objectifs de latence à sens simple seront la moitié des objectifs de latence RTT correspondants. Les objectifs de perte de paquets et de gigue restent les mêmes que ceux définis Skype de test basé sur un relais multimédia.
  


|**Région du client** <br/> |**Région Azure** <br/> |**Votre réseau de périphérie - Azure Round-trip Time (RTT)** <br/> |**Votre site - Azure Round-trip Time (RTT)** <br/> |
|:-----|:-----|:-----|:-----|
|Centre des États-Unis  <br/> |Centre des États-Unis  <br/> |99  <br/> |139  <br/> |
|Est des États-Unis  <br/> |Est des États-Unis  <br/> |86  <br/> |126  <br/> |
|Centre Nord des États-Unis  <br/> |Centre Nord des États-Unis  <br/> |97  <br/> |137  <br/> |
|Centre Sud des États-Unis  <br/> |Centre Sud des États-Unis  <br/> |94  <br/> |134  <br/> |
|Ouest des États-Unis  <br/> |Ouest des États-Unis  <br/> |94  <br/> |134  <br/> |
|Hawaï États-Unis  <br/> |Ouest des États-Unis  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Canada Est  <br/> |Canada Est  <br/> |131  <br/> |171  <br/> |
|Europe du Nord  <br/> |Europe du Nord  <br/> |99  <br/> |139  <br/> |
|Europe de l’Ouest  <br/> |Europe de l’Ouest  <br/> |95  <br/> |135  <br/> |
|Asie de l’Est  <br/> |Asie de l’Est  <br/> |118  <br/> |158  <br/> |
|Asie du Sud-Est  <br/> |Asie du Sud-Est  <br/> |97  <br/> |137  <br/> |
|Japon Est  <br/> |Japon Est  <br/> |111  <br/> |151  <br/> |
|Japon Ouest  <br/> |Japon Ouest  <br/> |118  <br/> |158  <br/> |
|Brésil Sud  <br/> |Brésil Sud  <br/> |70  <br/> |110  <br/> |
|Australie Est  <br/> |Australie Est  <br/> |124  <br/> |164  <br/> |
|Australie (Sud-est)  <br/> |Australie (Sud-est)  <br/> |124  <br/> |164  <br/> |
|Inde centrale  <br/> |Inde centrale  <br/> |103  <br/> |143  <br/> |
|Inde du Sud  <br/> |Inde du Sud  <br/> |103  <br/> |143  <br/> |
|Inde de l’Ouest  <br/> |Inde de l’Ouest  <br/> |103  <br/> |143  <br/> |
|Est de la Chine  <br/> |Est de la Chine  <br/> |120  <br/> |160  <br/> |
|Nord de la Chine  <br/> |Nord de la Chine  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualité multimédia et ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute pour Microsoft 365 ou Office 365 est une connexion réseau dédiée pour la connexion à Microsoft 365 ou Office 365. Il offre aux clients la possibilité de contrôler le chemin d’accès de leur trafic réseau. Ils n’ont plus à se préoccuper de l’imprévisible routage qui se produit sur Internet, où les données sont portées par des opérateurs, fournisseurs et fournisseurs inconnus. Le trafic réseau envoyé via ExpressRoute est envoyé directement via le réseau du partenaire ExpressRoute au réseau de Microsoft. Ainsi, les clients peuvent considérer Microsoft 365 ou Office 365 comme s’ils se trouvent dans leur propre centre de données hors site avec une connexion dédiée.
  
Azure ExpressRoute est disponible pour toutes les offres Microsoft 365 et Office 365 de licences azure. Toutefois, le module Premium Azure ExpressRoute est requis pour que les Microsoft 365 et les Office 365 activent un routage mondial. Les clients avec au moins 500 postes qui mettent en œuvre ExpressRoute peuvent obtenir le module additionnel *ExpressRoute requis* Premium sans frais supplémentaires.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute est-il requis pour une bonne qualité multimédia ?

Azure ExpressRoute n’est pas une condition requise pour obtenir la meilleure qualité Microsoft Teams qualité multimédia. Toutefois, c’est l’une des options de déploiement qui vous permettent de vous assurer que votre connectivité cloud répond aux Skype Entreprise de performances réseau et aux seuils.
  
Microsoft 365 et Office 365 sont des services sécurisés et hautes performances qui utilisent Internet. Nous continuons d’investir dans de nouvelles fonctionnalités de sécurité et des réseaux de périmètre régionaux pour améliorer en permanence la sécurité et les performances. Azure ExpressRoute n’est pas obligatoire pour les services Microsoft 365'entreprise ou Office 365 services, Microsoft Teams. Azure ExpressRoute est l’une des options de déploiement disponibles qui vous aideront à garantir que la connectivité à Microsoft 365 ou Office 365 répond aux exigences de performances réseau d’Skype Entreprise et garantit une qualité multimédia optimale au Microsoft Teams.
  
Pour Microsoft Teams qualité multimédia, il est important que la connexion entre les sites de votre entreprise et les réseaux de périphérie Microsoft réponde aux objectifs de performance en matière de performances réseau, d’un client Skype Entreprise au réseau de périphérie [Microsoft,](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) et que la connexion entre vos réseaux de réseau et les réseaux de périphérie Microsoft atteint les objectifs de performance requis en matière de performances réseau, de votre réseau de réseau à celui de [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
Il est également important que la connectivité réseau physique de votre entreprise, notamment votre réseau interne et la connectivité cloud, soit suffisante pour prendre en charge les volumes des pics de trafic multimédia. Azure ExpressRoute est l’une des nombreuses solutions qui aideront les clients à garantir que leur connectivité cloud Microsoft Teams à toutes ces conditions de performances.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute est-il requis pour les SLA de qualité vocale ?

Non, ExpressRoute n’est pas requis pour Microsoft Teams SLA de qualité vocale. Le [SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) sur la qualité vocale Microsoft Teams s’applique à tout appel éligible passé par un utilisateur de service vocal Microsoft Teams dans le cadre de la licence et de l’abonnement corrects qui lui permettent d’effectuer n’importe quel type d’appel VoIP ou PSTN. Un SLA de qualité vocale doit inclure que toutes les conditions suivantes sont traitées :
  
- Appels à partir de téléphones IP certifiés Microsoft.
    
- Connexions Ethernet filtrées.
    
- Problèmes de qualité vocale liés à des problèmes de réseau Microsoft.
    
> [!NOTE]
> Le SLA de qualité vocale exclut les appels dont la mauvaise qualité est due à des problèmes dans des réseaux autres que Microsoft, y compris le partenaire ExpressRoute et d’autres réseaux. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou Azure ExpressRoute ?

Avant de prendre des décisions sur les options de connectivité réseau à l’Microsoft Teams, les clients doivent évaluer leur réseau et la connectivité Internet actuelle sur la base des conditions de performances réseau décrites dans les conditions de performances réseau pour se connecter à [Microsoft Teams.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Si les performances du réseau via la connexion Internet actuelle sont définies sur une capacité suffisante pendant les heures de pointe et qu’elles répondent aux exigences de performances du réseau entre les sites et les réseaux de réseaux de périphérie Microsoft, et entre vos réseaux de réseau et les réseaux de réseau, vous pouvez continuer à utiliser votre connectivité Internet existante pour vous connecter à Microsoft Teams.
  
Sur les sites de l’entreprise où les conditions de performances du réseau ne sont pas respectées, nous vous recommandons vivement de travailler avec vos fournisseurs de services réseau existants pour améliorer vos performances réseau globales. Toutefois, si elles ne sont toujours pas satisfaites, Azure ExpressRoute peut contribuer à garantir que votre connectivité cloud Microsoft Teams vous aide à répondre aux exigences de performances du réseau.
  
Azure ExpressRoute offre les avantages supplémentaires suivants :
  
- Un contrat de niveau de service (SLA) sur la disponibilité de la connexion entre votre réseau et le réseau Microsoft. ExpressRoute offre un SLA de disponibilité garantie à 99,9 %.
    
- Bande passante prévue et garantie requise pour les services Microsoft 365 et Office 365 réseau. Pour y parvenir, vous pouvez envoyer uniquement du trafic Microsoft 365, Office 365 ou Skype Entreprise via ExpressRoute, puis faire passer tout le reste du trafic Internet par d’autres points de sortie/sortie Internet de votre réseau.
    
- ExpressRoute est conçu pour conserver les marquages de la QoS DSCP entre votre réseau et le réseau Microsoft.
    
Pour plus d’informations sur la QoS Et la planification de la capacité d’ExpressRoute, voir ExpressRoute et [QoS dans Microsoft Teams.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-set-up-azure-expressroute-for-microsoft-teams-only"></a>Puis-je configurer Azure ExpressRoute pour Microsoft Teams uniquement ?

Oui, vous pouvez configurer Azure ExpressRoute pour assurer une excellente connectivité entre le réseau de votre entreprise et les Microsoft Teams. Vos utilisateurs pourront ainsi obtenir la qualité Real-Time multimédia la plus optimale, mais vous pourrez continuer à vous connecter à d’autres services Microsoft 365 ou Office 365 sur Internet.
  
Le protocole de passerelle frontière (BGP) est un protocole de routage sur Internet utilisé pour router le trafic réseau sur Internet. Il est conçu pour échanger des informations de routage entre les systèmes autonomes (AS) trouvés sur Internet. Les valeurs de communautés BGP sont des balises d’attribut qui peuvent être appliquées aux itinéraires entrants ou sortants. Les communautés BGP sont souvent utilisées pour signaler au système DS de réception une liaison sortante à utiliser pour atteindre une destination donnée en fonction de la géographie, du type de service ou d’autres critères.
  
Avec la prise en charge des communautés BGP, Microsoft marquera les préfixes et les itinéraires avec les valeurs de communauté BGP appropriées en fonction du service à qui ils appartiennent. Microsoft marquera les préfixes annoncés via l’peering public et l’peering Microsoft avec les valeurs de communauté BGP appropriées indiquant la région dans qui les préfixes sont hébergés. Vous pouvez compter sur les valeurs de la communauté pour prendre les décisions de routage appropriées afin d’offrir un routage optimal. Vous pouvez utiliser la Microsoft Teams communauté BGP pour configurer une connexion ExpressRoute uniquement pour les Microsoft Teams. Pour en savoir plus, voir les exigences [de routage d’ExpressRoute.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-microsoft-teams"></a>Scénarios de connectivité ExpressRoute pour les Microsoft Teams
<a name="bkNetworkPerf"> </a>

Si vous avez décidé qu’ExpressRoute s’appuie sur les recommandations ci-dessus s’intait pour vous, voici quelques recommandations sur l’endroit et le nombre de connexions ExpressRoute dont vous devez obtenir.
  
### <a name="online-only-deployment---single-site"></a>Déploiement de Online uniquement - Un seul site

Si tous vos utilisateurs utilisent le service Microsoft Teams, et si vos bureaux sont centrés autour d’un emplacement physique unique et que vous décidez de déployer Azure ExpressRoute, vous devez configurer une seule connexion ExpressRoute entre votre site d’entreprise et l’emplacement d’peering [ExpressRoute](/azure/expressroute/expressroute-locations)le plus proche.
  
Le graphique suivant montre un exemple de ce type de déploiement. Pour cet exemple, Contoso est une université située à Orlando, FL. Contoso compte 10 000 enseignants et étudiants. Les tests Internet réalisés entre leur emplacement et Microsoft Edge ont montré une perte de paquets supérieure à 5 % pendant les heures de cours (heures de pointe). Ils ont décidé d’obtenir une connexion dédiée à Microsoft 365 ou Office 365 avec ExpressRoute avec une bande passante sur-provisionnée afin d’éviter l’encombrement du réseau pour Microsoft 365 ou Office 365 en particulier pour le trafic Microsoft Teams Real-Time. Ils se connectent au cloud de Microsoft via ExpressRoute sur le site MeetMe d’Atlanta, GA.
  
![Site unique ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Déploiement de Online uniquement - Plusieurs sites sur le même continent

Si votre entreprise utilise les services Microsoft Teams de plusieurs sites de la même région ou du même continent et que vous avez choisi d’implémenter Azure ExpressRoute, nous vous recommandons de connecter votre site principal via ExpressRoute, puis d’ajouter éventuellement une peering ExpressRoute supplémentaire pour les autres emplacements qui ne répondent pas aux objectifs de performance réseau recommandés.
  
Dans l’exemple suivant, Contoso est une agence de voyage américaine, qui possède son siège social à New York et des bureaux dans l’ensemble des États-Unis. Leurs bureaux sont interconnectés via un réseau WAN MPLS pour se connecter à Microsoft 365 ou Office 365. Ils ont initialement mis en place une connexion ExpressRoute entre leur routeur Internet situé à Hoboken, New Jersey et le site MeetMe de New York. 
  
Avec cette configuration, le trafic réseau entre la plupart de ses sites et le réseau Microsoft (site de périphérie de New York) peut répondre aux critères de performance réseau de connexion au client Skype Entreprise décrits dans la configuration requise pour les performances réseau entre un client Skype Entreprise et le réseau de périphérie [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Toutefois, le temps de latence entre les bureaux de Contoso situés sur la côte Ouest et ceux de New York est de plus de 50 ms. De plus, honolulu est le deuxième plus grand bureau de Contoso. Le temps de latence entre Honolulu et New York est supérieur à 80 ms. Pour garantir une bonne qualité multimédia pour les utilisateurs de ces bureaux, Contoso a décidé d’ajouter une connexion ExpressRoute sur la côte Ouest entre son site de San José et le site ExpressRoute MeetMe de la Silicon Valley.
  
![Routeur Express Multi-site sur le même continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Déploiement de Online uniquement - Plusieurs sites sur différents continents

Si tous vos utilisateurs utilisent le service Microsoft Teams et si vos sites se trouveront dans plusieurs emplacements physiques sur plusieurs continents, si vous décidez de déployer Azure ExpressRoute, vous devez configurer au moins une connexion ExpressRoute pour chaque continent entre le site principal de chaque continent et l’emplacement d’peering [ExpressRoute](/azure/expressroute/expressroute-locations)le plus proche. Selon le rapport qualité-prix, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de sites pour lequel les objectifs de performances réseau ne sont pas atteints.
  
Dans l’exemple suivant, Contoso est un grand cabinet d’avocats qui a des bureaux dans des grandes villes d’Amérique du Nord et d’Europe. Suite à l’évaluation de leur connexion Internet et des performances de leur réseau interne, Contoso a décidé de déployer deux connexions ExpressRoute en Amérique du Nord et un circuit ExpressRoute pour tous ses bureaux européens.
  
![ExpressRoute avec plusieurs sites sur plusieurs continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Déploiement hybride

Si vous avez un déploiement local de Lync ou Microsoft Teams et que vous choisissez d’implémenter une intégration Microsoft Teams hybride, nous vous recommandons de déployer Azure ExpressRoute au moins une connexion ExpressRoute pour chaque site Edge Lync ou Microsoft Teams local et au moins une connexion ExpressRoute pour chaque continent où vous avez des bureaux. Selon le rapport qualité-prix, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires sur chaque continent pour les bureaux qui ne souhaitent pas atteindre les objectifs de performance réseau.
  
Si vous avez un déploiement local Microsoft Teams, vous devez suivre le Guide de planification et de déploiement du serveur [Edge.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) Plus précisément, les serveurs Edge doivent être accessibles depuis l’extérieur de votre réseau. Pour ce faire, affectez une adresse IP publique routable au serveur Edge ou utilisez la traduction d’adresses réseau (NAT).
  
Dans l’exemple suivant, Contoso dispose d’un déploiement local Microsoft Teams Voix Entreprise existant. Ils souhaitent migrer des utilisateurs locaux vers des services Microsoft 365 ou Office 365 en ligne. Ils ont également décidé d’utiliser un déploiement hybride afin de continuer à utiliser leur infrastructure PSTN existante pour tous les utilisateurs locaux et en ligne. Le centre de données local de Contoso et Skype Entreprise Serveurs Edge se sont situés à Chicago. Pour son déploiement, Contoso a décidé de configurer une seule connexion ExpressRoute entre son centre de données de Chicago et le site ExpressRoute de Chicago. Ils ont également ajouté une connexion ExpressRoute sur la côte Ouest pour mieux servir leur bureau d’Honolulu.
  
![ExpressRoute hybride.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Déploiement en ligne avec la version Cloud Connector

Skype Entreprise Cloud Connector Edition est une offre hybride comprenant un ensemble de machines virtuelles (VM) qui implémentent la connectivité RSTN sur site. En déployant une topologie de Skype Entreprise Server minimale dans un environnement virtualisé, vous pourrez envoyer et recevoir des appels avec des téléphones fixes et mobiles par le biais de l’infrastructure PSTN Voice locale existante.
  
Si vous décidez de déployer Azure ExpressRoute et la version Cloud Connector, nous vous conseillons de configurer au moins une connexion ExpressRoute pour chaque continent, entre le site principal de chaque continent et l’emplacement d’peering [ExpressRoute](/azure/expressroute/expressroute-locations)le plus proche. Selon le rapport qualité-prix, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires sur chaque continent pour les sites pour lequel les objectifs de performance réseau ne sont pas atteints.
  
Si vous avez un déploiement local Microsoft Teams, vous devez suivre le Guide de [planification pour](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)Skype Entreprise Cloud Connector Edition. Plus précisément, les services Access Edge et A/V Edge doivent avoir des adresses IP publiques et des centres de données accessibles Microsoft 365 ou Office 365 de données.
  
Dans l’exemple suivant, Contoso est un cabinet d’experts-comptables européen qui est présent dans quelques villes et pays/villes d’Europe. Lorsqu’ils se sont connectés à Microsoft Teams pour répondre à tous leurs besoins de collaboration, ils ont décidé de mettre en place un connecteur Cloud pour chaque pays/région où ils se sont placés pour continuer à utiliser leur infrastructure RSTN et leurs contrats d’opérateur existants. Suite aux tests effectués sur l’ensemble de leurs sites et sur le réseau de périphérie Microsoft, ils ont déterminé qu’une seule connexion ExpressRoute à Londres faciliterait l’atteindre les objectifs de performances réseau de connexion au client Microsoft Teams décrits dans les conditions de performances réseau entre un client Skype Entreprise et le réseau de périphérie [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![ExpressRoute Cloud Connector un.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Voici une autre option de déploiement pour Contoso. Dans ce cas, ils ont décidé de configurer une connexion ExpressRoute sur chaque site où la connexion Cloud Connector est déployée. 
  
![Deux ExpressRoute Cloud Connector.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Rubriques connexes

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)

  
