---
title: "Qualité du support et des performances pour la connectivité réseau"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Cette rubrique définit l’ensemble des exigences de performances réseau pour Skype pour les services professionnels en ligne, et comment vous pouvez utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et vos Skype pour entreprise en ligne en fonction de votre évaluation du réseau connectivité. Si vous avez décidé de déployer d’Azure ExpressRoute pour une connectivité dédiée à Office 365, ce document fournit également des conseils sur la planification de vos connexions ExpressRoute dans Skype différent pour des scénarios de déploiement professionnel en ligne."
ms.openlocfilehash: 438328058ace76beb24bbdf1d64804441694b045
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Média qualité et les performances de connectivité réseau dans Skype pour l’activité en ligne

Cette rubrique définit l’ensemble des exigences de performances réseau pour Skype pour les services professionnels en ligne, et comment vous pouvez utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et vos Skype pour entreprise en ligne en fonction de votre évaluation du réseau connectivité. Si vous avez décidé de déployer d’Azure ExpressRoute pour une connectivité dédiée à Office 365, ce document fournit également des conseils sur la planification de vos connexions ExpressRoute dans Skype différent pour des scénarios de déploiement professionnel en ligne.
  
La qualité du support en temps réel (audio, vidéo et partage d’application) sur IP est considérablement affectée par la qualité de la connectivité réseau de bout en bout. Pour Skype optimale pour la qualité de supports professionnels en ligne, il est important pour vous assurer qu'une connexion de haute qualité entre votre réseau d’entreprise et les Skype pour Business Online existe. Le meilleur moyen d’y parvenir est de configurer votre réseau interne et d’une connectivité de nuage basé sur la capacité de votre réseau pour prendre en compte pour le volume de trafic de pointe pour Skype pour l’activité en ligne pour toutes les connexions.
  
ExpressRoute Azure n’est pas une condition requise pour les services Office 365, notamment Skype pour l’activité en ligne. Toutefois, Azure ExpressRoute fait partie du déploiement options disponibles qui aideront à vous assurer que la connectivité vers Office 365 répond à la Skype pour les besoins de performances réseau et garantit le plus optimal Skype pour Business Online media expérience de la qualité.
  
> [!TIP]
> Bien que cette rubrique vous donne des conseils pour les performances réseau globales, Guide d’évaluation du réseau est à l’extérieur de la portée de ce document. Pour rechercher une liste de Skype pour des partenaires professionnels en ligne qui peuvent vous aider avec les mesures de performances du réseau dans le cadre d’une évaluation du réseau et complet, visitez le site [Skype pour Solutions d’entreprise partenaire](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Besoins de connectivité de réseau à Skype pour professionnels en ligne

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Facteurs ayant un impact sur Skype pour la qualité de supports professionnels en ligne

Il y a plusieurs facteurs qui contribuent à Skype pour qualité de support (audio, vidéo et de l’application partage) en ligne en temps réel de Business qui incluent les périphériques qui sont utilisés, l’environnement et la connectivité réseau. 
  
#### <a name="devices"></a>Périphériques

Dans une session multimédia en temps réel, media capter et rendre les périphériques qui sont utilisés par tous les participants, tels que les casques et les caméras Web ont un impact important sur l’ensemble qualité audio et vidéo. Les unités de qualité inférieure ou avec les pilotes de périphérique incorrect produira qualité de sonore global pour une qualité d’image inférieure et audio pour la vidéo. Certifié de périphériques ou périphériques de bonne qualité, d’autre part, aide à l’annulation de l’écho, le filtrage de bruit, la résolution vidéo et diminuer la latence.
  
Bien qu’il est certifié que les périphériques audio et vidéo ne sont pas obligatoires, il est vivement recommandé de périphériques certifié pour Skype pour professionnels pour l’expérience multimédia optimale. Pour obtenir la liste de tous les Skype pour entreprise périphériques certifiés, voir [téléphones et périphériques pour Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947482). Vous pouvez utiliser le [Skype pour entreprise en ligne appeler tableau de bord qualité](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md)trouvé dans **Skype pour entreprise admin center**, pour vérifier le fonctionnement des périphériques en cours d’utilisation et contrôler la qualité de supports audio et vidéo.
  
> [!TIP]
> **Un périphérique certifié est requis pour le plus optimal Skype pour une expérience de qualité entreprise media**.
  
Il est important de se rappeler que tous les périphériques de supports, Skype pour les clients de l’entreprise et Skype des serveurs d’entreprise via le flux multimédia en temps réel, introduisent certains de latence. Le dispositif et logiciel de traitement de latence, ainsi que de la latence du réseau, ayant un impact important sur et contribuent à la latence globale de bout en bout et de l’expérience de l’utilisateur final.
  
#### <a name="environment"></a>Environnement

L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour obtenir une image plus claire de l’utilisation d’une expérience audio et vidéo d’un utilisateur au Skype pour Business application **Outils** > **Options** > **Périphérique Audio** ou **Vidéo** pour apporter des modifications au périphérique en cours d’utilisation et de personnaliser les paramètres de son. Vous pouvez également vérifier la qualité audio d’un appel en cliquant sur **Vérifier la qualité appeler**. En cliquant sur **Vérifier la qualité appeler**, ils peuvent signaler puis de la qualité et les problèmes rencontrés avec l’appel de test.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Réseau

La qualité du support en temps réel sur réseau IP est considérablement affectée par la qualité de la connectivité réseau, mais surtout par le montant de :
  
- **Temps de latence** C’est le temps que nécessaire pour obtenir un paquet IP du point A au point B sur le réseau. Ce délai de propagation réseau est essentiellement lié à la distance physique entre les deux points et de la vitesse de la lumière, y compris les frais supplémentaires prises par les routeurs différentes entre les deux. La latence est mesurée en temps à sens unique ou aller-retour (RTT).
    
- **Perte de paquets** Cela est souvent définie comme un pourcentage de paquets perdus dans une fenêtre donnée de temps. Perte de paquets affecte directement la qualité audio, de petites, individu perdu paquets n’ayant pratiquement aucune incidence, des pertes de rafale DOS à DOS qui provoquent les couper à la sortie audio complet.
    
- **Arrivée d’un paquet entre instabilité ou simplement d’instabilité** Il s’agit de la variation moyenne de retard entre les paquets successifs. Plus moderne logiciel VoIP, notamment Skype pour l’entreprise peut s’adapter à certains niveaux de gigue grâce à la mise en mémoire tampon. Il est uniquement lorsque la variation dépasse la mise en mémoire tampon qu’un participant remarquerez les effets de scintillement.
    
> [!NOTE]
>  Mise en mémoire tampon de gigue augmente la latence de bout en bout.
  
Avec beaucoup de Skype simultanées pour des sessions de support en ligne en temps réel de professionnels, ainsi que le trafic réseau généré par les autres services Office 365 et d’autres applications d’entreprise, assurez-vous qu’il y a suffisamment de bande passante sur le chemin d’accès de l’ensemble du réseau qui connecte votre réseau à la Skype pour Business Online service est essentiel pour éviter la congestion du réseau et garantir la media une excellente qualité de multimédia en temps réel (audio, vidéo et de l’application partage). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Mise en œuvre de la qualité de Service (QoS) des réseaux encombrés

En outre, congestion du trafic sur le réseau a une influence importante qualité du média. Pour autoriser les paquets audio et vidéo pour circulent sur le réseau plus rapide et la priorité sur le trafic réseau dans un réseau saturé, qualité de Service (QoS) peut être utilisée afin d’offrir une expérience utilisateur optimale pour les communications audio et vidéo.
  
QoS permet d’assigner des priorités les plus élevées pour les paquets réseau qui sont transportant des données audio ou vidéo. En attribuant une priorité plus élevée pour ces paquets, les communications audio et vidéo sont susceptibles de circuler sur le réseau, plus rapidement et avec une interruption moins, que les sessions de réseau impliquant des éléments tels que les transferts de fichiers, navigation sur le web ou les sauvegardes de base de données. C’est parce que les paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de base de données par défaut sont affectées « meilleur effort » comme une priorité et la congestion du réseau ne sont pas en tant que de grand impact. Si vous ne pas attribuer une priorité plus élevée aux paquets multimédia (audio, vidéo et de l’application partage) et les laisser également affecté comme « meilleur effort », ils seront trop traités ainsi que de tout autre trafic réseau. Selon la quantité de congestion du réseau, cette potentiellement finissent dans une expérience globale audio et vidéo de qualité inférieure pour vos utilisateurs.
  
Il est vivement recommandé de mettre en œuvre QoS sur votre réseau pour vous assurer que vous ne souhaitez pas une incidence pour la congestion du réseau au sein de votre réseau. Toutefois, pour cette option pour que l’incidence maximale, tous les points de terminaison de réseau doivent prendre en charge QoS, ce qui signifie que tous les points de terminaison doivent respecter la QoS de marquage et priorité des paquets. Skype pour les services professionnels en ligne respecte la QoS de marquage et définition des priorités au sein du réseau Microsoft. Toutefois, le trafic est routé via une connexion publique à Internet à partir de votre réseau d’entreprise sur le réseau Microsoft ne préserve pas les marques de qualité de service et de la priorité des paquets. Des connexions privées à votre réseau à Office 365 à l’aide de [ExpressRoute d’Azure](https://azure.microsoft.com/en-us/services/expressroute/) offrent une qualité vidéo et une solution de déploiement qui conserve les marques de qualité de service et de la priorité des paquets qui à son tour augmente globalement audio pour vos utilisateurs finaux.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Exigences de performances réseau pour se connecter sur Skype pour professionnels en ligne
<a name="bkNetworkPerf"> </a>

Skype pour le multimédia en temps réel d’entreprise est transmis par le biais de différents périphériques, les applications client, le logiciel serveur et sur des réseaux différents. La latence de bout en bout de multimédia en temps réel est le montant total de la latence introduite sur l’ensemble des composants et des segments de réseau. La qualité de la connexion réseau de bout en bout est déterminée par le segment de réseau avec la qualité la plus défavorable. Ce segment se comporte comme un goulet d’étranglement pour le trafic de ce réseau.
  
Le diagramme suivant illustre les flux audio à sens unique dans une conférence à partir d’un Skype participant de l’entreprise à l’autre.
  
![Flux d’appel de ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Dans ce scénario de conférence, le chemin d’accès de média se compose entre les segments de réseau suivants :
  
1. **Connexion de l’utilisateur 1 à la périphérie du réseau Microsoft** Cela inclut généralement une connexion réseau, telles que la connexion Internet de votre réseau de bord à bord de Microsoft network Wi-Fi ou Ethernet et la connexion WAN de l’utilisateur 1 et le point de sortie Internet (votre périphérique de périmètre de réseau).
    
2. **Connexion au réseau Microsoft** Il s’agit entre le Microsoft Edge à Skype pour centre de données commerciales en ligne, où le A / V Conferencing serveurs sont utilisés.
    
3. **Connexion au réseau Microsoft** Il s’agit entre le Skype pour centre de données commerciales en ligne et réseau de Microsoft Edge.
    
4. **Connexion à partir de la périphérie du réseau Microsoft à l’utilisateur 2** Cela inclut la connexion Internet de votre réseau de bord à bord, la connexion WAN à partir de l’utilisateur 2 pour le point de sortie Internet (votre réseau Edge) et la connexion de réseau comme un Wi-Fi ou Ethernet de Microsoft network.
    
Le diagramme suivant montre la répartition des composants et des segments de réseau d’un Skype pour les appels RTPC en ligne de Business :
  
![Flux d’appels de support ExpressRoute RTPC.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Dans un scénario d’appel RTC, le chemin d’accès de média traverse les segments de réseau suivants :
  
1. **Connexion à partir d’un Skype pour l’appelant de client d’entreprise à la périphérie du réseau Microsoft** Cela inclut généralement une connexion réseau, telles que la connexion Internet de votre réseau de bord à bord de Microsoft network Wi-Fi ou Ethernet et la connexion WAN à partir de la Skype pour l’appelant de client d’entreprise et le point de sortie Internet (votre périphérique de périmètre de réseau).
    
2. **Connexion au réseau Microsoft** Il s’agit entre le Microsoft Edge à Skype pour centre de données commerciales en ligne, où un serveur de médiation est utilisé.
    
3. **Connexion au réseau Microsoft** Il s’agit entre le Skype pour centre de données commerciales en ligne et réseau de Microsoft Edge.
    
4. **Connexion entre le réseau de Microsoft et les partenaires de fournisseur de service RTC** Il s’agit de la connexion qui existe pour passer un appel RTC de la Skype pour client d’entreprise qui n’est pas le réseau Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Exigences de performances réseau à partir d’un Skype pour client d’entreprise à bord de Microsoft network
<a name="bkSfBClienttoEdge"></a>

Skype optimale pour Business Support de qualité, les cibles de métriques de performances réseau ou les seuils suivants sont requis pour une connexion entre le réseau de votre entreprise et le bord du réseau Microsoft. Ce segment du réseau comprend votre réseau interne, cela inclut toutes les connexions Wi-Fi et Ethernet, tout trafic de site à site entreprise via une connexion WAN, par exemple de commutation d’étiquette multiprotocole (MPLS), ainsi que le partenaire Internet ou ExpressRoute connexions au bord du réseau Microsoft.
  
> [!CAUTION]
> **La connectivité entre un Skype pour client d’entreprise sur votre réseau d’entreprise pour les services Office 365 doit satisfaire à ces exigences de performances réseau suivantes et les seuils.**
  
|||
|:-----|:-----|
|**Métrique** <br/> |**Cible** <br/> |
|Latence (unidirectionnel)  <br/> |< 50 ms  <br/> |
|Latence (RTT ou temps d’aller-retour)  <br/> |< 100 ms  <br/> |
|Perte de paquets en mode rafale  <br/> |< 10 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 1 % sur un intervalle de 15 s  <br/> |
|Paquet arrivée entre GIGUE  <br/> |< 30 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,05 % paquets désorganisés  <br/> |
   
 **Autres exigences en matière de performance cible :**
  
- Le réseau Microsoft a plus de 160 emplacements de bord dans le monde entier. Nous travaillons avec les principaux fournisseurs de services Internet (ISP) dans le monde entier par le biais de ces sites de bord. La cible de mesure de latence suppose que votre site d’entreprise ou les sites et les Edges Microsoft sont sur le même continent.
    
- Votre entreprise ou les sites sur le réseau Microsoft connexion de bord comprennent le premier tronçon accès au réseau, qui peut être Wi-Fi ou une autre technologie sans fil. 
    
- La cible de performance de réseau suppose que la bande passante appropriée et/ou de la qualité de la planification du service. En d’autres termes, cela s’applique directement à Skype pour le trafic multimédia en temps réel de métier lors de la connexion réseau est sous une charge maximale.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Exigences de performances réseau à partir de votre réseau de bord à bord de Microsoft network
<a name="bkYourNetworkEdge"> </a>

Les éléments suivants sont des cibles de performances réseau ou les seuils qui sont requis pour la connexion entre votre réseau de bord et le bord du réseau Microsoft. Ce segment du réseau exclut le réseau du client interne ou un WAN et est conçu en tant que guide lors du test de votre trafic réseau qui est envoyé sur Internet, ou via un réseau de partenaires ExpressRoute et peut également être utilisé lors de la négociation d’une performance Niveau de contrat service (SLA) auprès de votre fournisseur de ExpressRoute.
  
> [!CAUTION]
> **La connectivité entre votre réseau d’entreprise bord à la périphérie du réseau Microsoft doit satisfaire à ces exigences de performances réseau suivantes et les seuils.**
  
|||
|:-----|:-----|
|**Métrique** <br/> |**Cible** <br/> |
|Latence (unidirectionnel)  <br/> |< 30 ms  <br/> |
|Latence (RTT)  <br/> |< 60 ms  <br/> |
|Perte de paquets en mode rafale  <br/> |< 1 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 0,1 % sur un intervalle de 15 s  <br/> |
|Paquet arrivée entre GIGUE  <br/> |< 15 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,01 % paquets désorganisés  <br/> |
   
 **Autres exigences en matière de performance cible :**
  
- La cible de performance nécessite une connexion entre des réseau de votre société Edge et son réseau de Microsoft le plus proche bord, soit sur le même continent.
    
- La cible de performance de réseau suppose que la bande passante appropriée et/ou de la qualité de la planification du service. Cela s’applique également à Skype pour le trafic multimédia en temps réel de métier lors de la connexion réseau est sous une charge maximale. Pour la bande passante appropriée et planification de QoS, reportez-vous à la [ExpressRoute et QoS dans Skype pour l’activité en ligne](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Mesure des performances réseau
<a name="bkNetworkPerf"> </a>

Pour mesurer les performances du réseau, en particulier pour les temps de latence et de perte de paquets, à partir de n’importe quel site de réseau d’entreprise à un réseau de bord, vous pouvez utiliser l’outil ping, par rapport à un ensemble de Skype pour les services de relais multimédia en cours d’exécution à partir du Microsoft Edge et les données de test sites du centre. 
  
Pour tester les connexions Internet au réseau Microsoft, il est recommandé de tester les VIP suivantes de la Skype pour Business Support de relais. Le *Système Anycast VIP* résout une adresse IP d’un relais de Media dans un site de bordure de réseau Microsoft le plus proche de l’emplacement de test.
  
||||
|:-----|:-----|:-----|
|**Adresse IP** <br/> |**Type de** <br/> |**Emplacement** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Voici quelques recommandations de haut niveau à suivre pour l’évaluation des performances du réseau :**
  
- Vous devez évaluer votre réseau interne, ainsi que les connexions à Office 365.
    
- Vous devez évaluer et collecter des données sur une longue période de temps pour l’ensemble de vos réseaux. Nous vous recommandons d’effectuer les tests des performances du réseau pendant une durée minimale d’une semaine, afin que vous puissiez voir les modèles d’utilisation pour tous les jours et les heures. Vous verrez heures de pointe.
    
- Vous devez prendre plusieurs exemples de mesures de performances réseau. Nous vous recommandons de prendre une mesure toutes les 10 minutes à partir d’un site de la société pendant toute la durée de temps que vous rassemblez des données. Pour comparer le Skype pour des exigences de performances réseau Business Online, prendre le 90e centile de mesure à partir de cet ensemble de données exemple. 
    
- Vous devez évaluer en permanence les performances du réseau. L’utilisation du réseau varie dans le temps en raison de modifications de modèle d’utilisation, nouvelles applications d’entreprise qui utilisent une grande quantité de bande passante et les modifications apportées à vos emplacements d’organisation ou physique de la société. Il est important de surveiller les performances de votre réseau par rapport à ces exigences de performances réseau et de la/des seuils cibles et effectuer des ajustements en temps utile pour assurer la qualité optimale de multimédia en temps réel en continu. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Mesure des performances du réseau à l’aide de machines virtuelles d’Azure
<a name="bkNetworkPerf"> </a>

Au lieu de tester sur les sites de bord de réseau de Microsoft, il existe des solutions d’évaluation de réseau de Skype pour les clients et les partenaires qui tirent parti des paramètres de test pour les services dans le nuage Microsoft Azure. Dans ces solutions, les outils d’évaluation réseau tester la latence, perte de paquets et la variation par rapport à des points de terminaison personnalisés défini en tant que service dans le nuage Azure. Par conséquent, le trafic réseau test traverse un seul segment de réseau supplémentaires, ce qui est de la connexion au sein du réseau Microsoft, entre les bords du réseau et les centres de données Azure, qui héberge le service d’évaluation de réseau.
  
Pour les réseau des solutions d’évaluation basées sur Azure services hébergés sur tests. Nous vous recommandons d’effectuer l’évaluation de réseau dans le pays ou la région. Par exemple, pour les sites des clients dans les États-Unis east, l’évaluation doit être effectuée par rapport à une instance de service de test hébergée dans l’east de Azure région de centre de données américain. 
  
Vous trouverez ci-dessous la latence cibles (RTT) pour l’installation d’évaluation de réseau service Azure en fonction. Les cibles de latence à sens unique sera la moitié des cibles RTT correspondants. Les objectifs d’instabilité et de perte de paquets reste le même, comme celles définies pour le relais multimédia Skype en fonction de tests.
  
|||||
|:-----|:-----|:-----|:-----|
|**Région client** <br/> |**Région Azure** <br/> |**Votre réseau bord - temps d’aller-retour d’Azure (RTT)** <br/> |**Votre Site - Azure temps d’aller-retour (RTT)** <br/> |
|États-Unis centre  <br/> |États-Unis centre  <br/> |99  <br/> |139  <br/> |
|Les États-Unis  <br/> |Les États-Unis  <br/> |86  <br/> |126  <br/> |
|États-Unis centre nord  <br/> |États-Unis centre nord  <br/> |97  <br/> |137  <br/> |
|États-Unis centre sud  <br/> |États-Unis centre sud  <br/> |94  <br/> |134  <br/> |
|États-Unis Ouest  <br/> |États-Unis Ouest  <br/> |94  <br/> |134  <br/> |
|Hawaii États-Unis  <br/> |États-Unis Ouest  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Est du Canada  <br/> |Est du Canada  <br/> |131  <br/> |171  <br/> |
|Europe du Nord  <br/> |Europe du Nord  <br/> |99  <br/> |139  <br/> |
|Europe de l’ouest  <br/> |Europe de l’ouest  <br/> |95  <br/> |135  <br/> |
|Asie de l’est  <br/> |Asie de l’est  <br/> |118  <br/> |158  <br/> |
|Asie du Sud-est  <br/> |Asie du Sud-est  <br/> |97  <br/> |137  <br/> |
|Nord-est du Japon  <br/> |Nord-est du Japon  <br/> |111  <br/> |151  <br/> |
|Ouest du Japon  <br/> |Ouest du Japon  <br/> |118  <br/> |158  <br/> |
|Sud du Brésil  <br/> |Sud du Brésil  <br/> |70  <br/> |110  <br/> |
|Est de l’Australie  <br/> |Est de l’Australie  <br/> |124  <br/> |164  <br/> |
|Sud-est de l’Australie  <br/> |Sud-est de l’Australie  <br/> |124  <br/> |164  <br/> |
|Central de l’Inde  <br/> |Central de l’Inde  <br/> |103  <br/> |143  <br/> |
|Sud-est de l’Inde  <br/> |Sud-est de l’Inde  <br/> |103  <br/> |143  <br/> |
|Ouest de l’Inde  <br/> |Ouest de l’Inde  <br/> |103  <br/> |143  <br/> |
|Chine orientale  <br/> |Chine orientale  <br/> |120  <br/> |160  <br/> |
|Nord de la Chine  <br/> |Nord de la Chine  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualité du support et ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure pour Office 365 est une connexion réseau dédiée pour se connecter à Office 365. Il offre aux clients la possibilité d’avoir un contrôle sur le chemin d’accès leur Office 365 prend du trafic réseau. Ils n’ont plus à se préoccuper de la rend le routage imprévisible qui se trouve sur Internet où de données transportées par des transporteurs inconnus, les fournisseurs et les fournisseurs de services Internet. Le trafic réseau qui est envoyé par le biais de ExpressRoute est envoyé directement sur le réseau du partenaire de l’ExpressRoute à réseau de Microsoft. Cela permet aux clients d’Office 365 les traite comme si elle se trouve dans son propre centre de données hors site avec une connexion dédiée.
  
ExpressRoute Azure est disponible pour toutes les offres de licence d’Office 365. Toutefois, le module Azure ExpressRoute prime complémentaire est requis pour Office 365 activer le routage global. Les clients d’Office 365 au moins 500 postes qui implémentent ExpressRoute peuvent obtenir le requis *ExpressRoute prime complémentaire* sans frais supplémentaires.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute est requis pour la qualité du support précédemment vérifié ?

ExpressRoute Azure n’est pas une exigence pour obtenir le plus optimal Skype pour la qualité de supports professionnels en ligne. Il est, toutefois, une du déploiement des options qui permettent de vous assurez-vous que votre connectivity nuage répond à la Skype pour des cibles de performances réseau professionnels ou les seuils.
  
Office 365 est un haute performance et un service sécurisé qui utilise Internet. Nous continuons d’investir dans nouvelles fonctions de sécurité et des noeuds régionaux à améliorer en permanence la sécurité et les performances. ExpressRoute Azure n’est pas une condition requise pour les services Office 365, notamment Skype pour l’activité en ligne. Azure ExpressRoute fait partie du déploiement options disponibles qui aidera à s’assurer que la connectivité vers Office 365 répond à la Skype pour les besoins de performances réseau et garantit le plus optimal Skype pour qualité de support en ligne de Business expérience.
  
Skype pour la qualité de supports professionnels en ligne, il est important que la connexion entre votre société et les bords du réseau Microsoft répond aux objectifs spécifiques de performances dans des conditions de [les performances du réseau à partir d’un Skype pour client d’entreprise au réseau Microsoft Bord](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) et que la connexion entre les bords de votre réseau et les bords du réseau Microsoft répond aux objectifs spécifiques de performances dans [les exigences de performances réseau à partir de votre réseau de bord à bord de Microsoft network](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
Il est également important que connectivité de réseau physique de votre entreprise, y compris votre capacité interne de connectivité réseau et nuage prendre en charge le volume de trafic de media de pointe. ExpressRoute Azure est une des nombreuses méthodes qui permettent aux clients de vérifier leur Skype pour la connectivité de cloud Business Online répond à toutes ces exigences de performance.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute est requis pour le contrat SLA de qualité vocale ?

Non, ExpressRoute n’est pas obligatoire pour Skype pour entreprise qualité vocale en ligne contrat SLA. Le [Skype pour entreprise qualité vocale en ligne contrat SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) s’applique à tout appel éligible par n’importe quel Skype pour Business Online utilisateur de service de voix au sein de la licence appropriée et l’abonnement qui permet à cet utilisateur pour tout type d’appel VoIP ou PSTN. Un SLA de qualité vocale doit comprendre que toutes les conditions suivantes sont traitées :
  
- Appels de Microsoft certified téléphones IP.
    
- Connexions Ethernet câblées.
    
- Problèmes de qualité vocale en raison de problèmes de Microsoft Network.
    
> [!NOTE]
> Le SLA de qualité vocale exclut ces appels où l’appel de faible qualité est dû à des problèmes dans les réseaux non Microsoft, y compris le partenaire de ExpressRoute et d’autres réseaux. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou ExpressRoute Azure ?

Avant de rendre une décision sur le réseau des options de connectivité à Skype pour entreprise en ligne, les clients doivent évaluer leur réseau et la connectivité Internet actuelle, selon les exigences de performances réseau décrits dans [des exigences de performances réseau pour se connecter à Skype pour Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si les performances du réseau via la connexion Internet en cours sont définie pour une capacité suffisante pendant les heures de pointe et qui il répond aux exigences de performances réseau à partir de sites aux bords du réseau Microsoft et à partir des bords de votre réseau à bords du réseau Microsoft, vous pouvez continuer à utiliser votre connexion Internet existante pour vous connecter à Skype pour l’activité en ligne.
  
Pour les sites de la société où les exigences de performances réseau ne sont pas respectées, nous vous recommandons vivement de vous tout d’abord travaillez avec vos fournisseurs de services réseau existants pour améliorer les performances générales de votre réseau. Toutefois, si elles ne sont pas encore remplies, à l’aide de ExpressRoute d’Azure peut garantir que votre Skype pour la connectivité de cloud Business Online peut vous aider à répondre aux exigences de performances réseau.
  
ExpressRoute Azure offre les avantages supplémentaires suivants :
  
- Un niveau accord de service (SLA) sur la disponibilité de la connexion entre votre réseau et le réseau Microsoft. ExpressRoute a un SLA de disponibilité garanti de 99,9 %.
    
- Planifié et garantie la bande passante requise pour les services d’Office 365. Vous pouvez y parvenir en envoyant uniquement le trafic d’Office 365 ou Skype pour le trafic d’entreprise à l’aide de la ExpressRoute, puis tous les autre Internet que le trafic passe par les autres points de sortie/entrée d’Internet pour votre réseau.
    
- ExpressRoute est conçu pour conserver des marquages DSCP QoS entre votre réseau et Microsoft Network.
    
Pour plus d’informations sur la QoS de ExpressRoute et de la planification de la capacité, reportez-vous à la [ExpressRoute et QoS dans Skype pour l’activité en ligne](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Puis-je configurer Azure ExpressRoute pour Skype pour entreprise en ligne uniquement ?

Oui, vous pouvez configurer Azure ExpressRoute afin de garantir une excellente connectivité à partir du réseau de votre société à Skype uniquement pour l’activité en ligne. Ceci fournira la qualité optimale de multimédia en temps réel pour vos utilisateurs, mais vous pouvez ensuite continuer à se connecter à d’autres services Office 365 via Internet.
  
Le protocole BGP (Border Gateway) est un protocole de routage sur Internet, qui est utilisé pour router le trafic réseau sur Internet. Il est conçu pour échanger des informations de routage entre systèmes autonomes (AS) trouvées sur Internet. Valeurs de communautés BGP sont des balises d’attribut peuvent être appliqués à des itinéraires entrants ou sortants. Les Communautés BGP sont souvent utilisées pour signaler à la réception en tant que le lien sortant à utiliser pour atteindre une destination donnée, en fonction de la géographie, type de service ou d’autres critères.
  
Avec la prise en charge des Communautés BGP, Microsoft permet d’identifier les préfixes et les itinéraires avec les valeurs de communauté BGP appropriés basés sur le service qu'auquel ils appartiennent. Microsoft permet d’identifier les préfixes annoncés via peering public et Microsoft homologue avec les valeurs de communauté BGP appropriées indiquant la région hébergées dans les préfixes. Vous pouvez compter sur les valeurs de la Communauté pour prendre des décisions de routage appropriées pour offrir un routage optimal. Vous pouvez utiliser le Skype pour valeur de communauté BGP en ligne des professionnels au programme d’installation d’une connexion ExpressRoute que pour Skype pour l’activité en ligne. Vous trouverez plus d’informations sur [les exigences de gamme ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scénarios de connexion ExpressRoute pour Skype pour professionnels en ligne
<a name="bkNetworkPerf"> </a>

Si vous avez décidé que ExpressRoute fondée sur les recommandations ci-dessus est pour vous, voici les recommandations sur l’emplacement et le nombre de connexions ExpressRoute, vous devez obtenir.
  
### <a name="online-only-deployment---single-site"></a>Déploiement en ligne - uniquement sur le même site

Si tous les utilisateurs utilisent le Skype pour service d’entreprise en ligne et si vos bureaux est centrées autour d’un seul emplacement physique et que vous décidez de déployer Azure ExpressRoute, vous devez configurer la connexion ExpressRoute entre le site de votre société à la plus proche [Emplacement d’homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
Le graphique suivant montre un exemple de ce type de déploiement. Pour cet exemple, Contoso est une université située à Orlando, en Floride. Contoso possède 10 000 membres du corps enseignant et les élèves. Les tests d’Internet à partir de leur emplacement de sites de bord de Microsoft a montré supérieures à la perte de paquets de 5 % pendant les heures de pointe classe. L’ont décidé d’obtenir une connexion dédiée à Office 365 à l’aide de ExpressRoute avec la bande passante excédentaire provisionnée afin de leur éviter la congestion du réseau pour Office 365 pour Skype pour le trafic en ligne en temps réel de Business. Ils se connectent au nuage Microsoft par le biais de ExpressRoute sur le site de rendez-vous réalisant un d’Atlanta, GA.
  
![Site de ExpressRoute unique.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Déploiement en ligne - plusieurs sites sur le même continent

Si votre société de services professionnels en ligne à partir de plusieurs succursales d’une même région ou continent est à l’aide de Skype et que vous avez choisi de mettre en œuvre des ExpressRoute d’Azure, il est recommandé de connecter votre site principal via ExpressRoute, puis éventuellement ajouter d’autres ExpressRoute d’homologation pour d’autres emplacements qui ne répondent pas à des cibles de performances du réseau recommandés.
  
Dans l’exemple suivant, Contoso est une société de services de voyage américaine qui a son siège social à New York mais qui possède d’autres bureaux dans toute la France. Les bureaux sont interconnectés via un réseau étendu utilisant MPLS pour se connecter à Office 365. Ils initialement définie d’une connexion ExpressRoute à partir de leur routeur Internet dans Hoboken, New Jersey, sur le site de rendez-vous réalisant un de New York. 
  
Avec cette configuration, le trafic de réseau à partir de la plupart des sites à Microsoft Network (site de bord de New York) peut répondre à la Skype pour Business client connexion réseau performances cibles décrit dans [des exigences de performances du réseau à partir d’un Skype pour client d’entreprise Bord réseau Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Toutefois, la latence entre les bureaux de côte ouest de Contoso à New York va sur unidirectionnel aller-retour de 50 millisecondes. En outre, Honolulu est la deuxième plus grande office pour Contoso, latence de Honolulu à New York dépasse 80ms à sens unique. Pour garantir la qualité de supports bon pour les utilisateurs de ces bureaux, Contoso a décidé d’ajouter une côte ouest ExpressRoute connexion entre leurs sites de San Jose et rendez-vous réalisant un ExpressRoute de Silicon Valley.
  
![Express routeur de plusieurs sites sur le même continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Déploiement en ligne - plusieurs sites sur différents continents

Si tous vos utilisateurs Utilisez Skype pour service d’entreprise en ligne, et si vos bureaux se trouvent dans plusieurs emplacements physiques sur plusieurs continents, si vous décidez de déployer ExpressRoute d’Azure, vous devez définir au moins une connexion de ExpressRoute pour chaque continent entre principal site du chaque continent à son plus proche [emplacement d’homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). En fonction des coûts et avantages, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir des sites où des cibles de performances réseau ne sont pas remplies.
  
Dans l’exemple suivant, Contoso est un cabinet d’entreprise volumineux avec des bureaux dans les grandes villes Amérique du Nord et en Europe. En fonction de leur connexion Internet et d’évaluation des performances de leur réseau interne, Contoso a décidé de déployer deux connexions de ExpressRoute en Amérique du Nord et un circuit de ExpressRoute unique pour tous leurs bureaux en Europe.
  
![ExpressRoute avec plusieurs sites et continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Déploiement hybride

Si vous avez un Lync sur site ou Skype pour le déploiement de l’entreprise et choisir d’implémenter un hybride Skype pour l’intégration de l’entreprise en ligne, nous vous recommandons que si vous décidez de déployer ExpressRoute d’Azure, vous devez disposer d’au moins une connexion de ExpressRoute pour chaque sur site Lync ou Skype pour site de bord d’entreprise et au moins une connexion de ExpressRoute pour chaque continent, avec des bureaux. En fonction des coûts et avantages, pour chaque continent vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de bureaux où des cibles de performances réseau ne sont pas respectées.
  
Si vous avez un Skype sur site pour le déploiement de l’entreprise, vous devez suivre [Guide de déploiement et de planification de serveur Edge](https://technet.microsoft.com/en-us/library/mt346417.aspx). Plus précisément, les serveurs Edge doivent être accessibles à partir d’en dehors de votre réseau. Cela est en général atteint par l’affectation d’une adresse IP publique de routable pour le serveur de transport Edge, soit en utilisant la traduction d’adresses réseau (NAT).
  
Dans l’exemple suivant, Contoso possède un Skype sur site existant pour un déploiement de Voix Entreprise entreprise. Ils souhaitent migrer les utilisateurs locaux aux services en ligne d’Office 365. Ils a également décidé d’utiliser un déploiement hybride afin qu’ils peuvent continuer à utiliser leur infrastructure existante de RTPC pour tous les utilisateurs en ligne et sur site. Centre de données sur site et Skype bord des serveurs d’entreprise de Contoso sont à Chicago. Pour leur déploiement, Contoso a décidé de configurer une connexion ExpressRoute entre leur centre de données de Chicago et la ExpressRoute de Chicago. Ils également ajouté une connexion de ExpressRoute pour mieux servir leur office Honolulu de côte ouest.
  
![Hybride de ExpressRoute.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Déploiement en ligne avec le nuage lien édition

Skype pour Business Edition du connecteur Cloud en ligne est un hybride offre qui se compose d’un ensemble de package Machines virtuelles (VM) qui implémentent la connectivité RTPC sur site. En déployant un minimum Skype pour la topologie du serveur de l’entreprise dans un environnement virtualisé, vous serez en mesure d’envoyer et de recevoir des appels avec les réseaux terrestres et les téléphones mobiles via l’infrastructure de voix RTC local existant.
  
Si vous décidez de déployer ExpressRoute d’Azure et le nuage lien édition, nous vous recommandons de configurer au moins une connexion Express itinéraire pour chaque continent entre le site principal de chaque continent son plus proche [emplacement d’homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). En fonction des coûts et avantages, pour chaque continent vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir des sites où des cibles de performances réseau ne sont pas respectées.
  
Si vous avez un Skype sur site pour le déploiement de l’entreprise, vous devez suivre le [Guide de planification pour Skype pour connecteur de Cloud Business Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Plus précisément, Edge d’accès et un / services V Edge doivent être affectés à des adresses IP publiques et est accessible à partir de centres de données d’Office 365.
  
Dans l’exemple suivant, Contoso est un cabinet d’expertise comptable européen avec présence dans quelques principaux pays européens et de villes. Lors de leur inscription pour Skype pour Business Online pour tous leurs besoins en matière de collaboration, ils a décidé de mettre un connecteur de nuage pour chaque pays, qu'ils ont un emplacement physique pour continuer à utiliser leur infrastructure RTPC et des contrats de support qui existent déjà. En fonction de leurs tests à partir de tous leurs sites et réseau de Microsoft Edge, ils déterminé qu’une seule connexion ExpressRoute à Londres aident le Skype pour Business client connexion réseau performances cibles décrite dans [, les performances du réseau configurations d’un Skype pour client d’entreprise à Microsoft réseau Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Connecteur de nuage de ExpressRoute un.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Vous trouverez ci-dessous une autre option de déploiement de Contoso. Dans ce cas, a décidé de définir une connexion ExpressRoute de chaque site où un connecteur de nuage est déployé. 
  
![Connecteur de nuage de ExpressRoute deux.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Rubriques connexes

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)

