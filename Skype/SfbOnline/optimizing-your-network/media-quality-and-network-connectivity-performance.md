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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Cette rubrique définit l’ensemble des exigences de performances réseau pour les services Skype entreprise Online et la façon dont vous pouvez choisir d’utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et Skype entreprise Online en fonction de votre évaluation de la connectivité du réseau. Si vous avez décidé de déployer Azure ExpressRoute pour une connectivité dédiée à Office 365, ce document fournit également des instructions sur la planification de vos connexions ExpressRoute dans différents scénarios de déploiement de Skype entreprise online.
ms.openlocfilehash: ed7ad6ebd456122e41ccd74269180ff9c79fa3fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776439"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online

Cette rubrique définit l’ensemble des exigences de performances réseau pour les services Skype entreprise Online et la façon dont vous pouvez choisir d’utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et Skype entreprise Online en fonction de votre évaluation de la connectivité du réseau. Si vous avez décidé de déployer Azure ExpressRoute pour une connectivité dédiée à Office 365, ce document fournit également des instructions sur la planification de vos connexions ExpressRoute dans différents scénarios de déploiement de Skype entreprise online.
  
La qualité des contenus multimédias en temps réel (audio, vidéo et de partage d’application) sur IP est fortement affectée par la qualité de la connectivité réseau de bout en bout. Pour bénéficier d'une qualité optimale pour Skype Entreprise Online, assurez-vous de la bonne qualité de la connexion entre votre réseau d'entreprise et Skype Entreprise Online. La meilleure façon d'y parvenir est de configurer la connectivité du réseau interne et du cloud en fonction de la capacité de votre réseau à s'adapter au volume du trafic maximal de Skype Entreprise Online sur l'ensemble des connexions.
  
Azure ExpressRoute n’est pas requis pour les services Office 365, dont Skype entreprise online. Toutefois, Azure ExpressRoute est l’une des options de déploiement disponibles qui vous aideront à vous assurer que la connectivité à Office 365 répond aux exigences de performance réseau de Skype entreprise et à garantir une qualité multimédia optimale de Skype entreprise online.
  
> [!TIP]
> Même si cette rubrique vous présente les conseils relatifs aux performances globales du réseau, des instructions complètes pour l’analyse du réseau ne sont pas du cadre de ce document. Pour obtenir la liste des partenaires de Skype entreprise Online qui peuvent vous aider à utiliser les mesures de performance du réseau dans le cadre d’une évaluation complète du réseau, consultez la rubrique [solutions de partenariat Skype entreprise](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Exigences de connectivité réseau pour Skype entreprise Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Facteurs ayant un impact sur la qualité multimédia de Skype entreprise Online

Il existe de nombreux facteurs différents pour la qualité de média en temps réel de Skype entreprise Online (audio, vidéo et partage d’application) qui inclut les périphériques utilisés, l’environnement et la connectivité réseau. 
  
#### <a name="devices"></a>Appareils

Dans une session multimédia en temps réel, la capture multimédia et le rendu des appareils utilisés par tous les participants, tels que les casques et les webcams ont un impact important sur la qualité globale de l’audio et de la vidéo. Les périphériques de qualité inférieure ou dont les pilotes sont incorrects produiront globalement des sons et des images de moins bonne qualité. Les périphériques certifiés ou de bonne qualité, en revanche, améliorent l'annulation d'écho, le filtrage du bruit et la résolution vidéo, et réduisent les temps de latence.
  
Même si les périphériques audio et vidéo certifiés ne sont pas requis, il est fortement recommandé d’avoir une certification Skype entreprise pour une qualité multimédia optimale. Pour obtenir la liste des appareils certifiés Skype entreprise, reportez-vous à la rubrique [téléphones et périphériques pour Skype entreprise](https://technet.microsoft.com/office/dn947482). Vous pouvez utiliser le [tableau de bord de qualité des appels de Skype entreprise Online](/microsoftteams/turning-on-and-using-call-quality-dashboard)dans le **Centre d’administration de Skype entreprise**pour vérifier le fonctionnement correct des appareils utilisés et surveiller la qualité des médias audio et vidéo.
  
> [!TIP]
> **Un périphérique certifié est requis pour garantir une qualité multimédia optimale sur Skype entreprise**.
  
Il est important de garder à l’esprit que les appareils multimédias, les clients Skype entreprise et les serveurs Skype entreprise via lesquels des flux multimédia en temps réel présentent un certain temps de latence. Le temps de latence du processus et du périphérique, en plus de la latence du réseau, a un impact important sur la latence globale globale et sur l’utilisation de l’utilisateur final.
  
#### <a name="environment"></a>Environnement

L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour obtenir une image plus claire de l’utilisation de**l’audio et**de la vidéo d’un utilisateur, utilisez le > **périphérique audio** ou le **périphérique vidéo** des **Outils** > de l’application Skype entreprise pour modifier les paramètres de l’appareil.

#### <a name="network"></a>Réseau

La qualité multimédia en temps réel sur le réseau IP est fortement affectée par la qualité de la connectivité du réseau, mais surtout par la quantité de :
  
- **Latence** Il s’agit du temps nécessaire à l’obtention d’un paquet IP du point A au point B sur le réseau. Ce délai de propagation du réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge supplémentaire prélevée par les différents routeurs entre eux. La latence est mesurée comme une seule ou même durée de boucle (RTT).
    
- **Perte de paquets** Il s’agit généralement d’un pourcentage de paquets perdus dans une période donnée. La perte de paquets affecte directement la qualité audio (par rapport aux petits paquets perdus individuels qui n’ont presque aucun impact, en raison d’une perte de Burst en retour en continu qui engendre une coupure audio complète).
    
- **Scintillement du son entre les paquets ou** inversement Il s’agit de la modification moyenne du délai entre les paquets successifs. La plupart des logiciels VoIP modernes, dont Skype entreprise, peuvent s’adapter à certains niveaux de scintillement par le biais de la mise en mémoire tampon. C’est uniquement lorsque l’instabilité est supérieure à la mise en mémoire tampon qu’un participant notera les effets de gigue.
    
> [!NOTE]
>  La mise en mémoire tampon pour le scintillement permettra d’augmenter la latence de bout en bout.
  
Avec beaucoup de sessions multimédias en temps réel de Skype entreprise Online, ainsi que d’autres trafic réseau générés par d’autres services 365 d’Office et d’autres applications métier, assurez-vous qu’il y a suffisamment de bande passante sur l’ensemble du chemin réseau qui connecte votre réseau au service de Skype entreprise Online est essentiel pour éviter l’encombrement du réseau et garantir un son qualité du partage, de la vidéo et de l’application. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Mise en œuvre de la qualité de service (QoS) sur des réseaux encombrés

De plus, la congestion du trafic sur un réseau aura un impact considérable sur la qualité multimédia. Pour autoriser les paquets audio et vidéo à voyager du réseau plus rapidement et aux priorités sur le trafic réseau d’un réseau encombré, il est possible d’utiliser la qualité de service (QoS) pour fournir une utilisation optimale des communications audio et vidéo.
  
La fonction QoS fournit un moyen d’affecter des priorités plus élevées aux paquets réseau qui transportent des données audio ou vidéo. En attribuant une priorité plus élevée à ces paquets, les communications audio et vidéo sont susceptibles d’être acheminées sur le réseau plus rapidement et avec moins d’interruption, qu’il s’agissait de sessions réseau impliquant des transferts de fichiers, de navigation sur le Web ou des sauvegardes de bases de données. En effet, les paquets réseau utilisés pour les transferts de fichiers ou de base de données par défaut sont attribués en priorité et la congestion du réseau n’aura pas le même impact. Si vous n’affectez pas une priorité plus élevée aux paquets de médias (audio, vidéo et de partage d’application), et que vous les laissez également affectés en tant que « meilleur effort », ils sont également traités avec le trafic réseau. En fonction de la quantité de congestion du réseau, le niveau de qualité audio et vidéo peut être inférieur à celui de vos utilisateurs.
  
Il est vivement recommandé de mettre en œuvre la qualité de service (QoS) sur votre réseau pour vous assurer que la congestion du réseau au sein de votre réseau n’aura aucun impact. Toutefois, pour que cela ait un impact maximal, tous les points de terminaison réseau doivent prendre en charge la qualité de service (QoS), ce qui signifie que tous les points de terminaison doivent respecter le marquage QoS et la priorité des paquets. Les services Skype entreprise Online respectent le marquage QoS et la hiérarchisation au sein du réseau Microsoft. Toutefois, le trafic acheminé au sein d’une connexion publique telle que Internet de votre réseau d’entreprise vers le réseau Microsoft ne conserve pas les marques de QoS et la hiérarchisation des paquets. Les connexions privées entre votre réseau et Office 365 à l’aide d' [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) proposent une solution de déploiement qui préserve les marques de QoS et la hiérarchisation des paquets pour améliorer la qualité audio et vidéo globale de vos utilisateurs finaux.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Conditions requises de performances réseau pour une connexion à Skype entreprise Online
<a name="bkNetworkPerf"> </a>

Le contenu multimédia en temps réel de Skype entreprise est parcouru par divers appareils, applications clientes, logiciels serveur et sur différents réseaux. La latence de bout en bout de média en temps réel correspond au volume total de latence présenté sur l’ensemble des composants et des segments réseau. La qualité de la connexion réseau de bout en bout est déterminée par le segment réseau ayant la mauvaise qualité. Ce segment agit comme un goulet d’étranglement pour ce trafic réseau.
  
Le diagramme suivant illustre le flux audio unidirectionnel d’une conférence entre un participant Skype entreprise et un autre.
  
![Flux d’appels ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Dans ce scénario de conférence, le chemin multimédia est constitué des segments réseau suivants :
  
1. **Connexion de l’utilisateur 1 au bord du réseau Microsoft** Il s’agit généralement d’une connexion réseau telle que WiFi ou Ethernet, de la connexion WAN de l’utilisateur 1 au point de sortie Internet (votre appareil de périmètre réseau) et de la connexion Internet entre le périmètre réseau et le réseau de périmètre Microsoft.
    
2. **Connexion au sein du réseau Microsoft** C’est entre le Microsoft Edge et le centre de données Skype entreprise Online dans lequel les serveurs de conférence A/V sont utilisés.
    
3. **Connexion au sein du réseau Microsoft** C’est entre le centre de données Skype entreprise Online et le réseau de périmètre Microsoft.
    
4. **Connexion du Microsoft Network Edge à l’utilisateur 2** Cela inclut la connexion Internet entre le périmètre réseau et le réseau de périmètre Microsoft, la connexion WAN de l’utilisateur 2 au point de sortie Internet (votre périmètre réseau) et la connexion réseau telle qu’un réseau Wi-Fi ou Ethernet.
    
Le schéma suivant illustre la répartition des composants et des segments réseau d’un appel RTC de Skype entreprise Online :
  
![Flux d’appels d’opérateur RTC ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Dans un scénario d’appel RTC, le chemin multimédia passe par les segments réseau suivants :
  
1. **Connexion d’un client appelant Skype entreprise au bord du réseau Microsoft** Il s’agit généralement d’une connexion réseau telle que WiFi ou Ethernet, de la connexion WAN de l’appelant du client Skype entreprise au point de sortie Internet (votre appareil de périmètre réseau) et de la connexion Internet à partir du réseau de périmètre Microsoft.
    
2. **Connexion au sein du réseau Microsoft** Entre le Microsoft Edge et le centre de données Skype entreprise Online, dans lequel un serveur de médiation est utilisé.
    
3. **Connexion au sein du réseau Microsoft** C’est entre le centre de données Skype entreprise Online et le réseau de périmètre Microsoft.
    
4. **Connexion entre le réseau de Microsoft et les partenaires du fournisseur de services RTC** Il s’agit de la connexion qui permet de passer un appel RTC à partir du client Skype entreprise hors du réseau Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Conditions requises de performances réseau entre un client Skype entreprise et le réseau de périmètre Microsoft
<a name="bkSfBClienttoEdge"></a>

Pour garantir une qualité multimédia optimale, vous devez disposer des cibles ou des seuils de mesure de performance réseau suivantes pour une connexion entre le réseau de votre entreprise et le réseau de périmètre Microsoft. Ce segment du réseau inclut votre réseau interne, ainsi que les connexions Wi-Fi et Ethernet, le trafic site-à-site d’une entreprise sur une connexion WAN, par exemple le changement d’étiquette multiprotocole (MPLS), ainsi que les connexions Internet ou ExpressRoute partenaires au réseau de périmètre Microsoft.
  
> [!CAUTION]
> **La connectivité entre un client Skype entreprise sur votre réseau d’entreprise et les services 365 Office doit répondre aux exigences et aux seuils de performances réseau suivantes.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< elle  <br/> |
|Latence (RTT ou durée de l’aller-retour)  <br/> |100 millions de <  <br/> |
|Perte de paquets en rafale  <br/> |<10% pendant tout intervalle de 200 millions  <br/> |
|Perte de paquets  <br/> |<1% pendant tout intervalle 15s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |<30ms pendant tout intervalle 15s  <br/> |
|Réorganisation des paquets  <br/> |<0,05% de paquets hors commande  <br/> |
   
 **Autres objectifs de performances requis :**
  
- Microsoft Network possède plus de 160 emplacements dans le monde. Nous travaillons avec des fournisseurs de services Internet importants dans le monde entier par le biais de ces sites latéraux. La cible métrique de latence suppose que le site ou les sites de votre entreprise et les bords Microsoft se trouvent sur le même continent.
    
- Le site ou les sites de votre entreprise vers la connexion au réseau de périmètre Microsoft inclut un accès réseau de premier saut, qui peut être WiFi ou une autre technologie sans fil. 
    
- Le ciblage des performances du réseau adopte une bande passante et/ou une qualité de service correcte. En d’autres termes, cela s’applique directement au trafic multimédia en temps réel de Skype entreprise lorsque la connexion réseau est en retard.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Conditions requises de performances réseau entre le périmètre réseau et le réseau de périmètre Microsoft
<a name="bkYourNetworkEdge"> </a>

Vous trouverez ci-après les cibles de performance réseau ou les seuils requis pour la connexion entre le périmètre réseau et le réseau de périmètre Microsoft. Ce segment du réseau exclut le réseau interne du client ou le WAN, et est destiné aux recommandations en matière de test du trafic réseau envoyé via Internet ou par le biais d’un réseau de partenariat ExpressRoute et peut également être utilisé lors de la négociation d’un contrat de niveau de service de performance avec votre fournisseur de services de ExpressRoute.
  
> [!CAUTION]
> **La connectivité entre le périmètre de votre réseau d’entreprise et le réseau de périmètre Microsoft doit répondre aux exigences et aux seuils de performances réseau suivantes.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< 30ms  <br/> |
|Latence (RTT)  <br/> |< 60ms  <br/> |
|Perte de paquets en rafale  <br/> |<1% pendant tout intervalle de MS 200  <br/> |
|Perte de paquets  <br/> |<0,1% pendant tout intervalle 15s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |<15ms pendant tout intervalle 15s  <br/> |
|Réorganisation des paquets  <br/> |<0,01% de paquets hors commande  <br/> |
   
 **Autres objectifs de performances requis :**
  
- L’objectif de performance nécessite une connexion entre l’un des bords du réseau de votre entreprise et le réseau de périmètre Microsoft le plus proche, qui se trouve sur le même continent.
    
- Le ciblage des performances du réseau adopte une bande passante et/ou une qualité de service correcte. Cela s’applique également au trafic multimédia en temps réel de Skype entreprise lorsque la connexion réseau est en retard. Pour obtenir une bande passante et une planification de qualité de service appropriées, consultez la [ExpressRoute et la qualité de service (QoS) dans Skype entreprise Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
    
## <a name="measuring-network-performance"></a>Mesure des performances du réseau
<a name="bkNetworkPerf"> </a>

Pour mesurer les performances réelles du réseau, en particulier en matière de latence et de perte de paquets, de tout site du réseau d’entreprise à un réseau d’entreprise, vous pouvez utiliser des outils tels que ping, test par l’intermédiaire d’un ensemble de services de relais de médias Skype entreprise qui s’exécutent à partir des sites Microsoft Edge et du centre de données. 

>[!NOTE]
> La mesure des performances réseau via le protocole ping (ICMP) n’est pas effective. C’est la raison pour laquelle l’adresse IP anycast suivante cesse de répondre aux demandes ICMP à partir de janvier 2020. Pour mesurer efficacement les performances du réseau, Microsoft recommande l’outil d’évaluation [réseau](https://www.microsoft.com/download/details.aspx?id=53885).
  
Pour tester les connexions Internet au réseau Microsoft, il est recommandé d’effectuer des tests par rapport aux VIP suivantes des relais multimédias Skype entreprise. Le protocole *VIP de anycast* sera résolu en une adresse IP d’un relais multimédia dans un site Microsoft Edge Network le plus proche de l’emplacement de test.
  
||||
|:-----|:-----|:-----|
|**Adresse IP** <br/> |**Type** <br/> |**Emplacement** <br/> |
|13.107.8.2  <br/> |VIRTUELLE  <br/> |IP anycast dans le monde  <br/> |
   
 **Voici quelques recommandations générales à suivre pour évaluer les performances du réseau :**
  
- Vous devez évaluer votre réseau interne ainsi que les connexions à Office 365.
    
- Vous devez évaluer et recueillir des données pour tous vos réseaux sur une longue période. Nous vous recommandons d’effectuer des tests sur les performances du réseau pour une durée d’une semaine minimum, afin que vous puissiez voir les modèles d’utilisation pour tous les jours et heures de travail. Cela vous permettra de montrer les heures de pointe.
    
- Vous devez prendre plusieurs exemples de mesures de performance réseau. Nous vous recommandons de suivre une mesure toutes les 10 minutes du site d’une entreprise au cours de la période pendant laquelle vous rassemblez les données. Pour comparer les exigences en matière de performances réseau de Skype entreprise Online, prenez la valeur de mesure de quatre-dixièmes à partir de cet exemple de jeu de données. 
    
- Vous devez en permanence évaluer les performances du réseau. L’utilisation du réseau varie en fonction de la proportion d’utilisation, des nouvelles applications d’entreprise qui utilisent une grande quantité de bande passante et des modifications apportées à vos emplacements d’entreprise ou physiques. Il est important de surveiller en continu les performances de votre réseau par rapport aux exigences et aux seuils de performances de votre réseau et de procéder à des ajustements adaptés pour garantir une qualité multimédia optimale en temps réel. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Mesure des performances du réseau à l’aide d’Azure VM
<a name="bkNetworkPerf"> </a>

Au lieu d’effectuer des tests sur les sites Microsoft Network Edge, il existe des solutions d’évaluation du réseau pour les clients Skype entreprise et les partenaires qui exploitent la configuration des tests pour les services dans Microsoft Azure Cloud. Dans ces solutions, les outils d’évaluation réseau latence de test, de perte de paquets et de gigue par rapport aux points de terminaison personnalisés configurés en tant que service dans le Cloud Azure. Par conséquent, le trafic réseau de test traverse un segment réseau supplémentaire, qui est la connexion au sein du réseau Microsoft entre les bords du réseau et les centres de données Azure qui héberge le service d’analyse du réseau.
  
Pour les solutions d’évaluation réseau basées sur des services de tests hébergés par Azure. Nous vous recommandons d’effectuer l’évaluation du réseau dans le pays ou la région. Par exemple, pour les sites de clients résidant aux États-Unis, l’analyse doit être effectuée sur une instance de service de test hébergée dans la région du centre de données américaine d’Azure. 
  
Vous trouverez ci-dessous les cibles de latence (RTT) pour la configuration de l’analyse réseau basée sur Azure service. Les cibles de latence à sens unique seront la moitié des cibles RTT correspondantes. Les objectifs de perte de paquets et de gigue restent les mêmes que ceux définis pour les tests basés sur le relais multimédia Skype.
  
|||||
|:-----|:-----|:-----|:-----|
|**Région du client** <br/> |**Région Azure** <br/> |**Votre périmètre réseau-Azure Round-Trip Time (RTT)** <br/> |**Votre site-Azure Round-Trip Time (RTT)** <br/> |
|Centre des États-Unis  <br/> |Centre des États-Unis  <br/> |99  <br/> |139  <br/> |
|Est américaine  <br/> |Est américaine  <br/> |86  <br/> |126  <br/> |
|Centre Nord des États-Unis  <br/> |Centre Nord des États-Unis  <br/> |97  <br/> |137  <br/> |
|Centre Sud des États-Unis  <br/> |Centre Sud des États-Unis  <br/> |94  <br/> |134  <br/> |
|Ouest des États-Unis  <br/> |Ouest des États-Unis  <br/> |94  <br/> |134  <br/> |
|Hawaï États-Unis  <br/> |Ouest des États-Unis  <br/> |116  <br/> |156  <br/> |
|Centre Canada  <br/> |Centre Canada  <br/> |138  <br/> |178  <br/> |
|Canada est  <br/> |Canada est  <br/> |131  <br/> |171  <br/> |
|Europe du Nord  <br/> |Europe du Nord  <br/> |99  <br/> |139  <br/> |
|Europe de l’ouest  <br/> |Europe de l’ouest  <br/> |95  <br/> |135  <br/> |
|Asie de l’est  <br/> |Asie de l’est  <br/> |118  <br/> |158  <br/> |
|Asie du sud-est  <br/> |Asie du sud-est  <br/> |97  <br/> |137  <br/> |
|Japon est  <br/> |Japon est  <br/> |111  <br/> |151  <br/> |
|Japon ouest  <br/> |Japon ouest  <br/> |118  <br/> |158  <br/> |
|Sud du Brésil  <br/> |Sud du Brésil  <br/> |70  <br/> |110  <br/> |
|Australie est  <br/> |Australie est  <br/> |124  <br/> |164  <br/> |
|Australie sud-est  <br/> |Australie sud-est  <br/> |124  <br/> |164  <br/> |
|Centre de l’Inde  <br/> |Centre de l’Inde  <br/> |103  <br/> |143  <br/> |
|Sud de l’Inde  <br/> |Sud de l’Inde  <br/> |103  <br/> |143  <br/> |
|Inde de l’ouest  <br/> |Inde de l’ouest  <br/> |103  <br/> |143  <br/> |
|Chine orientale  <br/> |Chine orientale  <br/> |120  <br/> |160  <br/> |
|Nord de la Chine  <br/> |Nord de la Chine  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualité multimédia et ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute pour Office 365 est une connexion réseau dédiée pour la connexion à Office 365. Il offre aux utilisateurs la possibilité de contrôler la trajectoire du trafic réseau d’Office 365. Ils ne doivent plus être préoccupés du routage inattendable qui se produit sur Internet, où les données sont transmises par des opérateurs, fournisseurs et FAI inconnus. Le trafic réseau envoyé via ExpressRoute est envoyé directement par le biais du réseau du partenaire ExpressRoute sur le réseau de Microsoft. Cela permet aux utilisateurs de traiter Office 365 comme s’il se trouve dans leur propre centre de données extérieur-site avec une connexion dédiée.
  
Azure ExpressRoute est disponible pour toutes les offre de licences Office 365. Toutefois, le module complémentaire Azure ExpressRoute Premium est requis pour que Office 365 active le routage global. Les clients disposant d’au moins 500 sièges qui implémentent ExpressRoute peuvent obtenir le *module complémentaire ExpressRoute Premium* requis sans frais supplémentaires.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute est-il requis pour obtenir une bonne qualité multimédia ?

Azure ExpressRoute n’est pas une obligation pour obtenir la meilleure qualité multimédia de Skype entreprise online. Il s’agit toutefois de l’une des options de déploiement qui vous permettent de vous assurer que votre connectivité Cloud répond aux objectifs ou aux seuils de performances réseau de Skype entreprise.
  
Office 365 est un service de grande performance et sécurisé qui utilise Internet. Nous continuons à investir dans de nouvelles fonctionnalités de sécurité et de nœuds de bordure régionale pour améliorer en permanence la sécurité et les performances. Azure ExpressRoute n’est pas requis pour les services Office 365, dont Skype entreprise online. Azure ExpressRoute est l’une des options de déploiement disponibles qui vous permettront de garantir que la connectivité à Office 365 répond aux exigences en matière de performances réseau de Skype entreprise et qu’elle assure une meilleure qualité multimédia de Skype entreprise online.
  
Dans le cadre de la qualité multimédia de Skype entreprise Online, il est important que la connexion entre les sites de votre entreprise et les bords du réseau Microsoft réponde aux objectifs de performances [réseau des clients Skype entreprise](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) et au réseau Microsoft, et que la connexion entre les bords de votre réseau et les bords du réseau Microsoft répond aux cibles de performance dans les [exigences de performances réseau du](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)périmètre réseau Microsoft.  
  
Il est également important que la connectivité réseau physique de votre entreprise, y compris la capacité de votre réseau interne et de la connectivité Cloud, atteigne le volume de trafic multimédia maximal. Azure ExpressRoute est l’un des nombreux moyens qui permettront aux clients de s’assurer que leur connectivité Cloud Skype entreprise Online répond à toutes ces exigences de performances.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute est-il requis pour le SLA de qualité vocale ?

Non, ExpressRoute n’est pas requis pour le SLA de qualité vocale de Skype entreprise online. Le [SLA de qualité vocale de Skype entreprise Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) s’applique aux appels éligibles placés par n’importe quel utilisateur du service vocal de Skype entreprise Online dans le cadre de la licence et de l’abonnement appropriés qui permettent à l’utilisateur de passer des appels VoIP ou PSTN. Un SLA de qualité vocale devrait inclure toutes les conditions suivantes :
  
- Appels à partir de téléphones IP certifiés Microsoft.
    
- Connexions Ethernet filaires.
    
- Problèmes de qualité vocale liés à des problèmes liés au réseau Microsoft.
    
> [!NOTE]
> Le SLA de qualité vocale exclut les appels dont la mauvaise qualité est causée par des problèmes provenant de réseaux non Microsoft, y compris le partenaire ExpressRoute et d’autres réseaux. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou Azure ExpressRoute ?

Avant de prendre une décision quant aux options de connectivité réseau dans Skype entreprise Online, les clients doivent évaluer leur réseau et la connectivité Internet actuelle en fonction des exigences de performances réseau décrites dans la rubrique [exigences de performances réseau pour vous connecter à Skype entreprise Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si les performances réseau sont configurées sur la connexion Internet actuelle et qu’elles sont configurées sur une capacité maximale et qu’elles répondent aux exigences de performances réseau des sites aux bords du réseau Microsoft et des bords du réseau aux bords du réseau Microsoft, vous pouvez continuer à utiliser votre connexion Internet existante pour vous connecter à Skype entreprise online.
  
Pour les sites d’entreprise pour lesquels les exigences de performances réseau ne sont pas satisfaites, nous vous recommandons vivement de commencer par collaborer avec vos prestataires de services réseau existants pour améliorer les performances globales de votre réseau. Toutefois, s’ils ne sont pas encore satisfaits, l’utilisation d’Azure ExpressRoute peut vous aider à garantir que votre connectivité Cloud Skype entreprise online peut vous aider à répondre aux exigences en matière de performances réseau.
  
Azure ExpressRoute offre les avantages supplémentaires suivants :
  
- Un contrat de niveau de service (SLA) sur la disponibilité de la connexion entre votre réseau et Microsoft Network. ExpressRoute a un SLA de disponibilité garantie de 99,9%.
    
- Bande passante planifiée et garantie requise pour les services Office 365. Pour cela, il vous suffit d’envoyer uniquement du trafic Office 365 ou du trafic Skype entreprise à l’aide du ExpressRoute et de faire en sorte que tout le trafic Internet passe par d’autres points de sortie Internet/entrants pour votre réseau.
    
- ExpressRoute est conçu pour préserver les marquages de la qualité de service DSCP entre votre réseau et celui de Microsoft.
    
Pour plus d’informations sur la QoS ExpressRoute et la planification des capacités, reportez-vous à la rubrique [ExpressRoute et QoS dans Skype entreprise Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Puis-je configurer Azure ExpressRoute pour Skype entreprise Online uniquement ?

Oui, vous pouvez configurer Azure ExpressRoute pour garantir une excellente connectivité réseau du réseau de votre entreprise à Skype entreprise online. La qualité multimédia en temps réel sera ainsi optimale pour vos utilisateurs, mais vous pourrez continuer à vous connecter à d’autres services Office 365 via Internet.
  
Le protocole BGP (Border Gateway Protocol) est un protocole de routage sur Internet qui est utilisé pour acheminer le trafic réseau sur Internet. Il est conçu pour échanger des informations de routage entre les systèmes autonomes disponibles sur Internet. Communautés BGP les valeurs sont des balises d’attribut qui peuvent être appliquées aux itinéraires entrants ou sortants. Les communautés BGP sont souvent utilisées pour signaler la réception en tant que lien sortant à utiliser pour atteindre une destination donnée en fonction de la géographie, du type de service ou d’autres critères.
  
Grâce à la prise en charge des communautés BGP, Microsoft marque les préfixes et itinéraires avec les valeurs de la communauté BGP appropriées en fonction du service auquel elles appartiennent. Microsoft balise les préfixes annoncés par le biais de l’homologation publique et de l’homologation Microsoft avec des valeurs de communauté BGP appropriées indiquant la région dans laquelle les préfixes sont hébergés. Vous pouvez compter sur les valeurs de la communauté pour prendre des décisions de routage appropriées afin de fournir un routage optimal. Vous pouvez utiliser la valeur de la communauté BGP de Skype entreprise Online pour configurer une connexion ExpressRoute uniquement pour Skype entreprise online. Vous pouvez en savoir plus sur la [Configuration requise](https://azure.microsoft.com/documentation/articles/expressroute-routing/)pour le routage de ExpressRoute.
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scénarios de connectivité ExpressRoute pour Skype entreprise Online
<a name="bkNetworkPerf"> </a>

Si vous décidez que ExpressRoute en fonction des recommandations ci-dessus est pour vous, Voici les recommandations sur l’emplacement et le nombre de connexions ExpressRoute à obtenir.
  
### <a name="online-only-deployment---single-site"></a>Déploiement en ligne uniquement-site unique

Si tous vos utilisateurs utilisent le service Skype entreprise Online et si vos bureaux sont centrés sur un emplacement physique unique et que vous décidez de déployer Azure ExpressRoute, vous devez configurer une connexion ExpressRoute unique entre le site de votre entreprise et l' [emplacement d’homologation ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)le plus proche.
  
Le graphique suivant montre un exemple de ce type de déploiement. Pour cet exemple, contoso est une université située à Orlando, FL. Contoso a 10 000 membres de l’Université et étudiants. Les tests Internet de leur emplacement vers des sites Microsoft Edge montrent une perte de paquets de 5% au cours des heures de cours de la période. Ils ont décidé d’obtenir une connexion dédiée à Office 365 à l’aide de ExpressRoute et de la bande passante déployée afin d’éviter la congestion du réseau pour Office 365 en particulier pour le trafic en temps réel de Skype entreprise online. Ils se connectent à Microsoft Cloud via ExpressRoute à partir du site MeetMe d’Atlanta, disponible en Géorgie.
  
![Site unique ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Déploiement en ligne uniquement-plusieurs sites sur le même continent

Si votre entreprise utilise les services Skype entreprise Online de plusieurs bureaux au sein d’une même région ou de votre continent, et que vous avez choisi d’implémenter Azure ExpressRoute, il est recommandé de connecter votre site principal via ExpressRoute, puis d’ajouter d’autres options d’homologation ExpressRoute pour d’autres emplacements qui ne satisfont pas aux cibles de performances réseau recommandées.
  
Dans l’exemple ci-dessous, contoso est une société américaine de voyages qui est implanté à New York mais qui a d’autres bureaux aux États-Unis. Leurs bureaux sont connectés via un réseau WAN qui utilise MPLS pour la connexion à Office 365. Il a initialement configuré une connexion ExpressRoute à partir de son routeur Internet dans Hoboken, New Jersey vers le site New York MeetMe. 
  
Dans le cadre de ce programme d’installation, le trafic réseau de la plupart de ses sites vers le réseau Microsoft (site de New York) peut correspondre aux cibles de performances du réseau de connexion du client Skype entreprise [et au réseau Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Toutefois, la latence entre les bureaux de la côte ouest de contoso et celle de New York va de elle à sens unique. En outre, Honolulu est le deuxième bureau Office pour Contoso le plus important, la latence de Honolulu à New York dépasse 80ms à sens unique. Pour garantir une qualité multimédia optimale pour les utilisateurs de ces bureaux, Contoso a décidé d’ajouter une connexion ExpressRoute Coast West entre son site San José et le site MeetMe Silicon Vallée ExpressRoute.
  
![Routeur rapide sur plusieurs sites sur le même continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Déploiement en ligne uniquement-plusieurs sites sur différents continents

Si tous vos utilisateurs utilisent le service Skype entreprise Online et si vos bureaux se trouvent à plusieurs endroits physiques sur plusieurs continents, si vous décidez de déployer Azure ExpressRoute, vous devez configurer au moins une connexion ExpressRoute pour chaque continent entre le site principal de chaque continent et l' [emplacement d’homologation ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)le plus proche. En fonction du coût et de l’avantage, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir des sites dans lesquels les cibles de performance réseau ne sont pas satisfaites.
  
Dans l’exemple ci-dessous, contoso est une entreprise de grande législation pour les entreprises qui dispose de bureaux dans les principales villes des États-Unis et de l’Europe. Sur la base de la connexion Internet et de l’évaluation de ses performances réseau interne, Contoso a décidé de déployer deux connexions ExpressRoute en Amérique du Nord et un circuit ExpressRoute unique pour tous leurs bureaux européens.
  
![ExpressRoute avec plusieurs sites et continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Déploiement hybride

Si vous disposez d’un déploiement Lync local ou Skype entreprise et que vous décidez de mettre en œuvre une intégration hybride Skype entreprise Online, nous vous recommandons d’avoir au moins une connexion ExpressRoute pour chaque site Lync ou Skype entreprise local et au moins une connexion ExpressRoute pour chaque continent possédant des bureaux d’une autre personne. En fonction du coût et de l’avantage, pour chaque continent, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de bureaux dans lesquels les cibles de performance réseau ne sont pas satisfaites.
  
Si vous disposez d’un déploiement Skype entreprise local, vous devez suivre le Guide de [planification et de déploiement de Edge Server](https://technet.microsoft.com/library/mt346417.aspx). Plus précisément, les serveurs Edge doivent être accessibles à partir de l’extérieur de votre réseau. Pour ce faire, vous devez attribuer une adresse IP publique routable au serveur Edge, ou à l’aide de la traduction d’adresses réseau (NAT).
  
Dans l’exemple suivant, contoso dispose d’un déploiement de voix entreprise Skype entreprise local. Ils souhaitent migrer des utilisateurs locaux vers les services en ligne d’Office 365. Ils ont également décidé d’utiliser un déploiement hybride pour pouvoir continuer à utiliser leur infrastructure RTC existante pour tous les utilisateurs locaux et en ligne. Le centre de données sur site de contoso et les serveurs Edge Skype entreprise sont situés à Chicago. Dans le cadre de leur déploiement, Contoso a décidé de configurer une connexion ExpressRoute entre le centre de données de Chicago et l’ExpressRoute Chicago. Ils ont également ajouté une connexion ExpressRoute Coast West pour améliorer leur bureau Honolulu.
  
![ExpressRoute hybride.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Déploiement de Online avec la version Cloud Connector

Skype entreprise Online Cloud Connector Edition est une offre hybride composée d’un ensemble d’ordinateurs virtuels empaquetés qui implémentent une connectivité PSTN locale. Le déploiement d’une topologie de serveur Skype entreprise minimale dans un environnement virtualisé vous permet d’envoyer et de recevoir des appels avec des téléphones fixes et mobiles dans l’infrastructure RTC RTC locale.
  
Si vous décidez de déployer Azure ExpressRoute et la version Cloud Connector, nous vous recommandons de configurer au moins une connexion de routage rapide pour chaque continent entre le site principal de chaque continent et l’emplacement d' [homologation](https://azure.microsoft.com/documentation/articles/expressroute-locations/)le plus proche ExpressRoute. En fonction du coût et de l’avantage, pour chaque continent, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir des sites dans lesquels les cibles de performance réseau ne sont pas satisfaites.
  
Si vous disposez d’un déploiement Skype entreprise local, vous devez suivre le [Guide de planification de Skype entreprise version Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx). Plus précisément, il convient d’attribuer des adresses IP publiques aux services Edge d’accès et aux services Edge A/V et de joindre les centres de données Office 365.
  
Dans l’exemple suivant, contoso est une entreprise comptable européenne ayant une présence dans quelques pays et villes importants. Lorsqu’il s’inscrit à Skype entreprise Online pour tous ses besoins en matière de collaboration, il a décidé de mettre en place un connecteur Cloud pour chaque pays où il possède un emplacement physique pour continuer à utiliser ses contrats d’infrastructure PSTN et de transporteur qui existent déjà. D’après les tests effectués sur tous leurs sites et sur le réseau de réseau Microsoft, il a déterminé qu’une seule connexion ExpressRoute à Londres permettra de répondre aux objectifs de performances réseau de connexion du client Skype entreprise décrits dans la rubrique [exigences des performances réseau d’un client Skype entreprise à Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Vous trouverez ci-dessous une autre option de déploiement pour contoso. Le cas échéant, il a décidé de configurer une connexion ExpressRoute sur chaque site sur lequel un connecteur Cloud est déployé. 
  
![ExpressRoute Cloud Connector 2.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Voir aussi

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
