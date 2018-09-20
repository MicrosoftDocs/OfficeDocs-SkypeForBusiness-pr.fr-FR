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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cette rubrique définit l’ensemble des exigences de performances réseau pour Skype pour des services professionnels en ligne et comment vous pouvez choisir d’utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et de Skype pour Business Online en fonction de votre évaluation du réseau connectivité. Si vous avez décidé de déployer ExpressRoute Azure pour la connectivité dédiée à Office 365, ce document fournit également des instructions sur la planification de vos connexions ExpressRoute dans différents Skype pour les scénarios de déploiement en ligne Business.
ms.openlocfilehash: dbe927794d8660a801596dac32623574e314ee44
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057610"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online

Cette rubrique définit l’ensemble des exigences de performances réseau pour Skype pour des services professionnels en ligne et comment vous pouvez choisir d’utiliser Internet ou ExpressRoute pour la connectivité entre votre réseau et de Skype pour Business Online en fonction de votre évaluation du réseau connectivité. Si vous avez décidé de déployer ExpressRoute Azure pour la connectivité dédiée à Office 365, ce document fournit également des instructions sur la planification de vos connexions ExpressRoute dans différents Skype pour les scénarios de déploiement en ligne Business.
  
La qualité des médias en temps réel (audio, vidéo et partage d’application) sur IP est considérablement affectée par la qualité de la connectivité réseau de bout en bout. Pour bénéficier d'une qualité optimale pour Skype Entreprise Online, assurez-vous de la bonne qualité de la connexion entre votre réseau d'entreprise et Skype Entreprise Online. La meilleure façon d'y parvenir est de configurer la connectivité du réseau interne et du cloud en fonction de la capacité de votre réseau à s'adapter au volume du trafic maximal de Skype Entreprise Online sur l'ensemble des connexions.
  
ExpressRoute Azure n’est pas une condition requise pour les services Office 365, notamment Skype pour Business en ligne. Toutefois, ExpressRoute Azure est un du déploiement options disponibles qui aideront à vous assurer que connectivité à Office 365 respecte la Skype pour les besoins de performances réseau et garantit la plus optimale Skype pour le support d’entreprise en ligne expérience de qualité.
  
> [!TIP]
> Bien que cette rubrique fournit des conseils pour les performances réseau global, Guide d’évaluation du réseau est à l’extérieur de l’étendue de ce document. Pour obtenir la liste de Skype pour les partenaires professionnels en ligne qui peuvent vous aider avec les mesures de performances réseau dans le cadre d’une évaluation du réseau et complet, visitez le site [Skype pour des Solutions professionnelles partenaire](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Exigences de connectivité réseau à Skype pour Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Facteurs qui influent sur Skype pour la qualité des médias Business en ligne

Il existe de nombreux facteurs qui contribuent à Skype pour la connectivité réseau, l’environnement et la qualité des médias (partage d’application, audio et vidéo) en ligne en temps réel de métier qui incluent les périphériques qui sont utilisés. 
  
#### <a name="devices"></a>Périphériques

Dans une session multimédia en temps réel, media capture et le rendu des périphériques qui sont utilisés par tous les participants, tels que les casques et les webcams ont un impact important sur l’ensemble qualité audio et vidéo. Les périphériques de qualité inférieure ou dont les pilotes sont incorrects produiront globalement des sons et des images de moins bonne qualité. Les périphériques certifiés ou de bonne qualité, en revanche, améliorent l'annulation d'écho, le filtrage du bruit et la résolution vidéo, et réduisent les temps de latence.
  
Bien que certifié médias audio et vidéo ne sont pas obligatoires, il est vivement recommandé de périphériques certifié pour Skype pour les entreprises pour l’expérience multimédia optimale. Pour obtenir la liste de tous les Skype pour les entreprises certifiées d’appareils, voir [téléphones et appareils pour Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947482). Vous pouvez utiliser la [Skype pour Business Online Dashboard qualité des appels](/microsoftteams/turning-on-and-using-call-quality-dashboard), trouvés dans **Skype pour Business admin center**, pour vérifier le fonctionnement des périphériques en cours d’utilisation et surveiller la qualité des médias audio et vidéo.
  
> [!TIP]
> **Un périphérique certifié est requis pour la plus optimale Skype pour Business qualité multimédias**.
  
Il est important de noter que tous les périphériques multimédia, Skype pour les clients d’entreprise et Skype des serveurs d’entreprise via le flux de médias en temps réel, introduisent certains de latence. Le périphérique et les logiciels de traitement latence, ainsi que de la latence du réseau, ayant un impact important sur et contribuent à la latence globale de bout en bout et l’expérience de l’utilisateur final.
  
#### <a name="environment"></a>Environnement

L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour obtenir une image plus claire d’utilisation de l’expérience audio et vidéo d’un utilisateur le Skype pour l’application de gestion des **Outils** > **Options** > **Périphérique Audio** ou **Périphérique vidéo** pour apporter des modifications à l’appareil en cours d’utilisation et de personnaliser ses paramètres.

#### <a name="network"></a>Réseau

La qualité des médias en temps réel via le réseau IP est considérablement affectée par la qualité de la connectivité réseau, mais surtout par la quantité de :
  
- **Latence** Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B sur le réseau. Ce délai de propagation de réseau est essentiellement lié à distance physique entre les deux points et la vitesse de la lumière, y compris une surcharge supplémentaire prise par les routeurs différents entre les deux. Latence est exprimée en tant qu’heure à sens unique ou aller-retour (durée aller-retour).
    
- **Perte de paquets** Il est souvent définie sous forme de pourcentage des paquets sont perdus dans une fenêtre de temps donnée. Perte de paquets affecte directement la qualité audio, de petite, individuel perdu paquets n’ayant pratiquement aucune incidence, pertes rafale DOS à DOS provoquer complète Couper-sortie audio.
    
- **Arrivée entre les paquets gigue ou simplement gigue** Il s’agit de la variation moyenne de retard entre les paquets successives. Plus modernes VoIP logicielle notamment Skype pour les entreprises permettre s’adapter à certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon qu’un participant remarqueront les effets de gigue.
    
> [!NOTE]
>  Mise en mémoire tampon de gigue augmente la latence de bout en bout.
  
Avec nombreux Skype simultanés pour les sessions de support en ligne en temps réel de Business, ainsi que le trafic réseau généré par les autres applications et d’autres services Office 365, s’assurer qu’il y a suffisamment de bande passante sur le chemin d’accès de l’ensemble du réseau qui connecte votre réseau à le Skype pour Business Online service est fondamental pour éviter la congestion du réseau et assurez-vous multimédia excellente qualité des médias en temps réel (partage d’application, audio et vidéo). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>L’implémentation de qualité de Service (QoS) sur des réseaux saturées

En outre, congestion du trafic réseau considérablement impact sur la qualité des médias. Pour permettre aux paquets audio et vidéos pour le réseau plus rapidement en déplacement et la priorité sur le trafic réseau dans un réseau saturé, qualité de Service (QoS) peut être utilisée afin d’offrir une expérience utilisateur optimale pour les communications audio et vidéos.
  
QoS permet d’assigner priorité supérieure aux paquets réseau sont exécution des données audio ou vidéo. En attribuant une priorité plus élevée à ces paquets, communications audio et vidéos sont susceptibles de se déplacent sur le réseau plus rapide et moins interruption, que les sessions de réseau impliquant des transferts de fichiers, navigation sur le web ou des sauvegardes de base de données. C’est parce que les paquets réseau utilisés pour les transferts de fichiers ou des sauvegardes de base de données par défaut sont affectés « best effort » comme une priorité et une surcharge réseau ne sont pas en tant qu’impact important. Si vous n’attribuer une priorité plus élevée aux paquets multimédia (partage d’application, audio et vidéo) et les laisser également affecté comme « best effort », ils seront trop traités ainsi que tout autre trafic réseau. Selon la quantité de congestion du réseau, il potentiellement finissent dans une expérience de qualité audio et vidéo de global inférieure pour vos utilisateurs.
  
Il est vivement recommandé de mettre en œuvre QoS sur votre réseau pour vous assurer que la congestion du réseau au sein de votre réseau ne sont pas avoir un impact. Toutefois, pour cette option pour que l’incidence maximale, tous les points de terminaison de mise en réseau doivent prendre en charge QoS, ce qui signifie que tous les points de terminaison doivent respecter le marquage de QoS et hiérarchisation des paquets. Skype pour les services en ligne Business respectent le marquage qualité de service et définition des priorités au sein du réseau Microsoft. Toutefois, le trafic acheminé via une connexion à Internet depuis votre réseau d’entreprise pour le réseau Microsoft publique ne conserve les marques de qualité de service et hiérarchisation des paquets. Connexions à partir de votre réseau vers Office 365 à l’aide [d’Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) offrent une solution de déploiement qui conserve le marquage QoS et hiérarchisation des paquets qui à son tour augmente globale audio et la qualité vidéo pour vos utilisateurs finaux.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Exigences de performances réseau pour se connecter à Skype pour Business Online
<a name="bkNetworkPerf"> </a>

Skype pour les médias en temps réel Business transite par le biais de nombreux périphériques différents, applications clientes, logiciel du serveur et à travers différents réseaux. La latence de bout en bout de médias en temps réel est la quantité totale de la latence est une nouveauté dans tous les composants et les segments réseau. La qualité de la connexion réseau de bout en bout est déterminée par le segment de réseau avec la plus mauvaise qualité. Ce segment joue un goulot d’étranglement pour ce trafic réseau.
  
Le diagramme suivant illustre le flux audio à sens unique dans une conférence à partir d’un Skype participant d’entreprise à l’autre.
  
![Flux d’appels ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Dans ce scénario de conférence, le chemin d’accès des médias se compose entre les segments réseau suivants :
  
1. **Connexion de l’utilisateur 1 et le bord du réseau Microsoft** Cela inclut généralement une connexion de réseau telles que la connexion Internet de votre réseau de périphérie réseau Microsoft Edge Wi-Fi ou Ethernet et la connexion WAN de l’utilisateur 1 pour le point de sortie Internet (votre périphérique de périphérie réseau).
    
2. **Connexion au sein du réseau Microsoft** Il s’agit entre le Microsoft Edge à Skype pour le centre de données métiers en ligne, où A / V Conferencing serveurs sont utilisés.
    
3. **Connexion au sein du réseau Microsoft** Il s’agit entre le Skype pour le centre de données métiers en ligne et le réseau Microsoft Edge.
    
4. **Connexion à partir du côté du réseau Microsoft à l’utilisateur 2** Cela inclut la connexion Internet de votre réseau de périphérie réseau Microsoft Edge, la connexion WAN à partir de l’utilisateur 2 pour le point de sortie Internet (votre réseau Edge) et la connexion réseau comme un Wi-Fi ou Ethernet.
    
Le diagramme suivant illustre la répartition des composants et des segments réseaux d’un Skype pour appel PSTN en ligne d’entreprise :
  
![Flux d’appels PSTN ExpressRoute opérateur.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Dans un scénario d’appel RTC, le chemin d’accès des médias coupe les segments réseau suivants :
  
1. **Connexion à partir d’un Skype pour Business client de l’appelant vers le bord du réseau Microsoft** Cela inclut généralement une connexion de réseau telles que la connexion Internet de votre réseau de périphérie réseau Microsoft Edge Wi-Fi ou Ethernet et la connexion WAN à partir de la Skype pour l’appelant de client d’entreprise pour le point de sortie Internet (votre périphérique de périphérie réseau).
    
2. **Connexion au sein du réseau Microsoft** Il s’agit entre le Microsoft Edge à Skype pour le centre de données métiers en ligne, où un serveur de médiation est utilisé.
    
3. **Connexion au sein du réseau Microsoft** Il s’agit entre le Skype pour le centre de données métiers en ligne et le réseau Microsoft Edge.
    
4. **Connexion entre le réseau Microsoft et les partenaires de fournisseur de service RTC** Il s’agit de la connexion qui existe pour émettre un appel RTC à partir de la Skype pour client d’entreprise se trouvant en dehors du réseau de Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Exigences de performances réseau à partir d’un Skype pour client d’entreprise au réseau Microsoft Edge
<a name="bkSfBClienttoEdge"></a>

Skype optimale pour la qualité des médias, les objectifs de mesures de performances réseau ou les seuils suivants sont requis pour une connexion de réseau de votre société à Microsoft network Edge. Ce segment de réseau comprend votre réseau interne, cela inclut toutes les connexions Wi-Fi et Ethernet, le trafic de n’importe quel site à société via une connexion WAN, par exemple commutation étiquette multiprotocole (MPLS), ainsi que le partenaire Internet ou ExpressRoute connexions au réseau Microsoft Edge.
  
> [!CAUTION]
> **La connectivité entre un Skype pour client d’entreprise sur votre réseau d’entreprise aux services Office 365 doit répondre à ces exigences de performances réseau suivants et les seuils.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< 50 ms  <br/> |
|Latence (RTT or durée de l'aller-retour)  <br/> |< 100 ms  <br/> |
|Perte de paquets en rafale  <br/> |< 10 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |< 30 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,05 % paquets désorganisés  <br/> |
   
 **Autres exigences de cibles de performances :**
  
- Le réseau Microsoft a plus de 160 emplacements Edge dans le monde entier. Travail avec les principaux fournisseurs de services Internet (fournisseurs) dans le monde par le biais de ces sites Edge. La cible de métrique latence suppose que votre site de l’entreprise ou les sites et les Edges Microsoft sont sur le même continent.
    
- Votre société ou des sites pour le réseau Microsoft connexion Edge incluent le premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil. 
    
- La cible de performance réseau suppose que la bande passante appropriée et/ou de la qualité de la planification du service. En d’autres termes, cela s’applique directement à Skype pour le trafic multimédia en temps réel Business lorsque la connexion réseau est soumis à une charge maximale.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Exigences de performances réseau de votre réseau de périphérie réseau Microsoft Edge
<a name="bkYourNetworkEdge"> </a>

Voici les objectifs de performances réseau ou les seuils qui sont requis pour la connexion entre votre réseau de périphérie et le réseau Microsoft Edge. Ce segment de réseau exclut le réseau interne du client ou sur des liaisons réseau étendu et est destiné à des instructions lorsque vous testez le trafic réseau qui est envoyé via Internet ou via un réseau de partenaire ExpressRoute et peut également être utilisé lors de la négociation de performances Niveau de contrat service (SLA) avec votre fournisseur de ExpressRoute.
  
> [!CAUTION]
> **La connectivité entre votre réseau d’entreprise Edge et le bord du réseau Microsoft doit répondre à ces exigences de performances réseau suivants et les seuils.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< 30 ms  <br/> |
|Latence (durée aller-retour)  <br/> |< 60 ms  <br/> |
|Perte de paquets en rafale  <br/> |< 1 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 0,1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |< 15 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,01% paquets désorganisés  <br/> |
   
 **Autres exigences de cibles de performances :**
  
- La cible de performance nécessite une connexion entre un réseau de votre société Edge et son réseau de Microsoft le plus proche Edge, soit sur le même continent.
    
- La cible de performance réseau suppose que la bande passante appropriée et/ou de la qualité de la planification du service. Cela s’applique également à Skype pour le trafic multimédia en temps réel Business lorsque la connexion réseau est soumis à une charge maximale. Pour la bande passante appropriée et planification QoS, reportez-vous à [ExpressRoute et QoS dans Skype pour Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Mesure des performances réseau
<a name="bkNetworkPerf"> </a>

Pour mesurer les performances réseau, en particulier pour la latence et la perte de paquets, d’un site de réseau d’entreprise à un réseau de périphérie, vous pouvez utiliser des outils tels que ping, test par rapport à un ensemble de Skype pour les services de relais multimédia en cours d’exécution à partir des données et Microsoft Edge sites centre. 
  
Pour tester les connexions réseau Microsoft Internet, il est recommandé de tester les VIP suivantes de la Skype pour relais multimédia de Business. L' *Adresse IP virtuelle de diffusion aléatoire* résout l’adresse IP d’un serveur relais multimédia dans un site de périphérie réseau Microsoft le plus proche de l’emplacement de test.
  
||||
|:-----|:-----|:-----|
|**Adresse IP** <br/> |**Type** <br/> |**Emplacement** <br/> |
|13.107.8.2  <br/> |ADRESSE IP VIRTUELLE  <br/> |IP de diffusion aléatoire à l’échelle mondiale  <br/> |
   
 **Voici quelques recommandations à suivre pour évaluer les performances réseau de haut niveau :**
  
- Vous devez évaluer votre réseau interne, ainsi que les connexions à Office 365.
    
- Vous devez évaluer et recueillir des données sur une longue période de temps pour tous les réseaux. Nous vous recommandons d’effectuer les tests des performances du réseau au moins une semaine, afin que vous pouvez voir les modèles d’utilisation pour tous les jours et heures. Vous verrez heures de pointe.
    
- Vous devez prendre plusieurs exemples de mesures de performances réseau. Nous vous recommandons d’effectuer une mesure 10 minutes à partir d’un site de l’entreprise pendant toute la durée de temps que sont collecte de données. Pour comparer la Skype pour des exigences de performances réseau en ligne Business, prendre le 90e centile de mesure à partir de cet ensemble de données exemple. 
    
- Vous devez évaluer en permanence des performances du réseau. L’utilisation du réseau varie au fil du temps en raison des modifications de modèle d’utilisation, nouvelles applications entreprise qui utilisent une grande quantité de bande passante et les modifications apportées à vos emplacements d’organisation ou physique de la société. Il est important de surveiller les performances de votre réseau par rapport à ces exigences de performances réseau et les cibles/seuils et effectuer des ajustements en temps voulu pour garantir la qualité des médias en temps réel optimale en continu. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Mesure des performances réseau à l’aide de machines virtuelles Azure
<a name="bkNetworkPerf"> </a>

Au lieu de tester les sites de périphérie réseau Microsoft, il existe de solutions d’évaluation de réseau de Skype pour les entreprises et les partenaires qui tirent parti de test du programme d’installation pour les services dans le nuage Microsoft Azure. Dans ces solutions, les outils d’évaluation réseau tester la latence, la perte de paquets et la gigue par rapport à des points de terminaison personnalisés définis en tant que service dans le nuage Azure. Par conséquent, le trafic réseau test transite par un segment de réseau supplémentaires, qui est la connexion au sein du réseau Microsoft entre les bords du réseau et les centres de données Azure qui héberge le service d’évaluation de réseau.
  
Pour ces réseau solutions évaluation basées sur Azure hébergée services tests. Nous vous recommandons d’effectuer l’évaluation de réseau au sein des pays ou région. Par exemple, pour les sites des clients aux États-Unis east, l’évaluation doit être effectuée par rapport à une instance du service de test hébergée dans east de Azure région de centre de données américain. 
  
Vous trouverez ci-dessous la latence cibles (durée aller-retour) pour l’installation d’évaluation de réseau Azure service basé. Les cibles de latence à sens unique sera la moitié des cibles durée aller-retour correspondants. Les objectifs de gigue et de perte de paquets reste la même que ceux définis pour le relais multimédia Skype en fonction de test.
  
|||||
|:-----|:-----|:-----|:-----|
|**Région client** <br/> |**Région Azure** <br/> |**Votre réseau de périphérie - temps durée (Azure aller-retour aller-retour)** <br/> |**Votre Site : temps d’aller-retour Azure (durée aller-retour)** <br/> |
|États-Unis centre  <br/> |États-Unis centre  <br/> |99  <br/> |139  <br/> |
|Asie US  <br/> |Asie US  <br/> |86  <br/> |126  <br/> |
|États-Unis centre nord  <br/> |États-Unis centre nord  <br/> |97  <br/> |137  <br/> |
|États-Unis centre sud  <br/> |États-Unis centre sud  <br/> |94  <br/> |134  <br/> |
|États-Unis Ouest  <br/> |États-Unis Ouest  <br/> |94  <br/> |134  <br/> |
|Hawaï US  <br/> |États-Unis Ouest  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|East Canada  <br/> |East Canada  <br/> |131  <br/> |171  <br/> |
|Europe du Nord  <br/> |Europe du Nord  <br/> |99  <br/> |139  <br/> |
|Europe de l’ouest  <br/> |Europe de l’ouest  <br/> |95  <br/> |135  <br/> |
|Asie de l’est  <br/> |Asie de l’est  <br/> |118  <br/> |158  <br/> |
|Asie du Sud-est  <br/> |Asie du Sud-est  <br/> |97  <br/> |137  <br/> |
|East Japon  <br/> |East Japon  <br/> |111  <br/> |151  <br/> |
|Ouest Japon  <br/> |Ouest Japon  <br/> |118  <br/> |158  <br/> |
|Brésil sud  <br/> |Brésil sud  <br/> |70  <br/> |110  <br/> |
|Asie de l’Australie  <br/> |Asie de l’Australie  <br/> |124  <br/> |164  <br/> |
|Sud-est Australie  <br/> |Sud-est Australie  <br/> |124  <br/> |164  <br/> |
|Inde centrale  <br/> |Inde centrale  <br/> |103  <br/> |143  <br/> |
|Inde du Sud  <br/> |Inde du Sud  <br/> |103  <br/> |143  <br/> |
|Inde ouest  <br/> |Inde ouest  <br/> |103  <br/> |143  <br/> |
|East Chine  <br/> |East Chine  <br/> |120  <br/> |160  <br/> |
|Amérique Chine  <br/> |Amérique Chine  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>La qualité des médias et ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure pour Office 365 est une connexion réseau dédiée pour se connecter à Office 365. Elle offre aux clients la possibilité de contrôler le chemin d’accès leur Office 365 prend le trafic réseau. Ils n’ont plus être concernés par le routage imprévisible qui se trouve sur Internet où les données a lieu par des opérateurs inconnus, les fournisseurs et les fournisseurs de services Internet. Le trafic réseau qui est envoyé par le biais de ExpressRoute est envoyé directement sur le réseau du partenaire ExpressRoute au réseau de Microsoft. Cela permet aux clients traiter Office 365 comme s’il se trouve dans leur propre centre de données hors site avec une connexion dédiée.
  
ExpressRoute Azure est disponible pour toutes les offres de gestion des licences Office 365. Toutefois, le module complémentaire de Azure ExpressRoute Premium est requis pour Office 365 activer le routage global. Les clients Office 365 au moins 500 utilisateurs qui implémentent ExpressRoute peuvent obtenir le requis *Complémentaire ExpressRoute* sans frais supplémentaires.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute est requis pour la qualité des médias bonne ?

ExpressRoute Azure n’est pas une condition requise pour l’obtention de la plus optimale Skype pour la qualité des médias Business en ligne. Il est toutefois un du déploiement options qui vous aident à vérifier que votre connectivity nuage répond à la Skype pour les objectifs de performances réseau Business ou les seuils.
  
Office 365 est un service d’informations sécurisé qui utilise Internet et hautes performances. Nous continuer à investir dans des nouvelles fonctionnalités de sécurité et les nœuds Edge locaux pour améliorer les performances et la sécurité en continu. ExpressRoute Azure n’est pas une condition requise pour les services Office 365, notamment Skype pour Business en ligne. ExpressRoute Azure est un du déploiement options disponibles qui aideront à vous assurer que connectivité à Office 365 respecte la Skype pour les besoins de performances réseau et garantit la plus optimale Skype pour la qualité des médias Business en ligne expérience.
  
Skype pour la qualité des médias Business en ligne, il est important que la connexion entre les sites de votre entreprise et les bords du réseau Microsoft satisfait les objectifs de performances exigences [performances réseau à partir d’un Skype pour client d’entreprise de Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) et que la connexion entre les bords de votre réseau et les bords du réseau Microsoft satisfait les objectifs de performances dans [des exigences de performances réseau de votre réseau de périphérie réseau Microsoft Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
Il est également important que connectivité réseau physique de votre société, y compris la capacité de connectivité réseau et nuage interne prendre en charge le volume de trafic multimédia de pointe. Azure ExpressRoute est une des façons qui permettra aux clients de vérifier leur Skype pour la connectivité de cloud Business Online répond à toutes ces exigences de performances.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute est requis pour SLA de qualité vocale ?

Non, ExpressRoute n’est pas requis pour Skype pour SLA de qualité vocale en ligne Business. Le [Skype pour SLA de qualité vocale en ligne Business](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) s’applique à n’importe quel appel éligible par n’importe quel Skype pour l’utilisateur du service voix entreprise en ligne au sein de la licence correcte et d’abonnement qui permet à cet utilisateur d’effectuer n’importe quel type d’appel VoIP ou PSTN. Un contrat de qualité de voix doit comprendre que toutes les conditions suivantes sont résolus :
  
- Les appels à partir de Microsoft certified téléphones IP.
    
- Connexions Ethernet câblées.
    
- Problèmes de qualité vocale en raison de problèmes de Microsoft Network.
    
> [!NOTE]
> Le SLA de qualité vocale exclut ces appels où la qualité des appels faible est dû à des problèmes dans les réseaux non Microsoft, y compris le partenaire ExpressRoute et autres réseaux. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou ExpressRoute Azure ?

Avant de prendre une décision sur des réseaux options de connectivité à Skype pour Business Online, les clients doivent évaluer leur réseau et les cours selon les exigences de performances réseau décrites dans [des exigences de performances réseau pour la connectivité Internet se connecter à Skype pour Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Si les performances réseau via la connexion Internet en cours sont définie pour une capacité suffisante pendant les heures de pointe et qui il répond aux exigences de performances réseau à partir de sites aux bords du réseau Microsoft et de votre réseau des contours bords du réseau Microsoft, vous pouvez continuer à utiliser votre connexion Internet existante pour se connecter à Skype pour Business Online.
  
Pour les sites de la société où les exigences de performances réseau ne sont pas respectées, nous vous recommandons vivement de tout d’abord collaborer avec vos fournisseurs de services réseau existant pour améliorer les performances générales de votre réseau. Toutefois, si elles ne sont pas encore remplies, à l’aide d’Azure ExpressRoute peut aider à garantir votre Skype pour la connectivité de cloud Business Online peut vous aider à satisfaire les exigences de performances réseau.
  
ExpressRoute Azure offre les avantages supplémentaires suivants :
  
- Un niveau accord de service (SLA) sur la disponibilité de la connexion entre votre réseau et Microsoft. ExpressRoute possède une garantie SLA de disponibilité de 99,9 %.
    
- Planifié et garantie la bande passante requise pour les services Office 365. Vous pouvez effectuer cette opération en envoyant uniquement le trafic d’Office 365 ou Skype pour le trafic d’entreprise à l’aide de la ExpressRoute, puis tous les autres Internet que le trafic passe par les autres points de sortie/entrée Internet pour votre réseau.
    
- ExpressRoute est conçu pour conserver le marquage DSCP QoS entre votre réseau et Microsoft Network.
    
Pour plus d’informations sur la planification de capacité et ExpressRoute QoS, reportez-vous à [ExpressRoute et QoS dans Skype pour Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Puis-je configurer Azure ExpressRoute pour Skype pour Business Online uniquement ?

Oui, vous pouvez configurer Azure ExpressRoute pour garantir la connectivité réseau excellente entre le réseau de votre entreprise et Skype uniquement pour Business Online. Cela permettra la qualité des médias en temps réel optimale pour vos utilisateurs, mais vous pouvez ensuite continuer à se connecter à d’autres services Office 365 via Internet.
  
Le protocole BGP (Border Gateway) est un protocole de routage sur Internet, qui est utilisé pour acheminer le trafic réseau via Internet. Il est conçu pour échanger des informations de routage entre des systèmes autonomes (AS) trouvées sur Internet. Les valeurs de communautés BGP sont des balises d’attribut qui peuvent être appliqués aux itinéraires entrants ou sortants. Communautés BGP sont souvent utilisées pour signaler à la réception en tant que le lien sortant à utiliser pour atteindre une destination donnée en fonction de géographie, type de service ou d’autres critères.
  
Avec prise en charge des Communautés BGP, Microsoft permet d’identifier les itinéraires et les préfixes avec les valeurs de la Communauté BGP appropriés basés sur le service qu'auquel ils appartiennent. Microsoft permet d’identifier les préfixes publiés par le biais de peering public et Microsoft homologue avec les valeurs de la Communauté BGP appropriées indiquant la région hébergées dans les préfixes. Vous pouvez compter sur les valeurs de la Communauté pour prendre des décisions de routage appropriées pour offrir un routage optimales. Vous pouvez utiliser la Skype pour la valeur de la Communauté Business Online BGP pour le programme d’installation d’une connexion ExpressRoute uniquement pour Skype pour Business Online. Vous trouverez plus d’informations sur [les exigences de gamme ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scénarios de connectivité ExpressRoute pour Skype pour Business Online
<a name="bkNetworkPerf"> </a>

Si vous avez décidé que ExpressRoute fondée sur les recommandations ci-dessus pour vous, voici les recommandations sur l’emplacement et le nombre de connexions ExpressRoute, vous devez obtenir.
  
### <a name="online-only-deployment---single-site"></a>Déploiement en ligne - uniquement sur le même site

Si tous vos utilisateurs utilisent le Skype pour le service Business en ligne et si vos sites sont centrés sur un seul emplacement physique et que vous décidez de déployer ExpressRoute Azure, vous devez configurer la connexion ExpressRoute unique entre le site de votre société à la plus proche [Emplacement homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
Le graphique suivant montre un exemple de ce type de déploiement. Cet exemple, Contoso est une université située dans Orlando, Floride. Contoso a 10 000 enseignants et étudiants. Les tests d’Internet à partir de leur emplacement aux sites de bord de Microsoft a montré supérieures à 5 % de perte de paquets pendant les heures de pointe classe. L’avez décidé d’obtenir une connexion à Office 365 à l’aide de ExpressRoute avec une bande passante excédentaire mis en service afin qu’ils ne la congestion du réseau pour Office 365 en particulier pour Skype pour le trafic en temps réel Online Business dédiée. Ils se connectent au cloud Microsoft par le biais de ExpressRoute au niveau du site de rendez-vous réalisant un Atlanta, GA.
  
![Site ExpressRoute unique.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Déploiement en ligne - plusieurs sites sur le même continent

Si votre société à l’aide Skype pour des services professionnels en ligne à partir de plusieurs bureaux dans la même zone ou continent et que vous décidez d’implémenter ExpressRoute Azure, il est recommandé pour connecter votre site principal via ExpressRoute et éventuellement ajouter puis supplémentaires ExpressRoute peering pour d’autres emplacements qui ne remplissent pas les objectifs de performances réseau recommandés.
  
Dans l’exemple suivant, Contoso est une société de services de déplacements US qui est basée à New York, mais dispose d’autres bureaux ensemble des États-Unis. Leurs bureaux sont reliées entre elles via un réseau étendu qui utilise MPLS pour se connecter à Office 365. Ils initialement configurer une connexion ExpressRoute à partir de leur routeur Internet dans Hoboken, New Jersey au site rendez-vous réalisant un New York. 
  
Dans cette configuration, le trafic réseau à partir de la plupart de leurs sites à Microsoft Network (site de New York Edge) peut répondre à la Skype pour Business client connexion réseau performances cibles décrites dans [des exigences de performances du réseau à partir d’un Skype pour client d’entreprise réseau Microsoft Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Toutefois, la latence entre bureaux d’ouest de Contoso à New York va sur aller-retour de 50 millisecondes à sens unique. En outre, Honolulu est la deuxième plus grande office pour Contoso, la latence de Honolulu de New York dépasse 80ms à sens unique. Pour garantir la qualité des médias bonne pour les utilisateurs dans les succursales, Contoso a décidé d’ajouter ouest ExpressRoute connexion entre leurs sites San Jose et rendez-vous réalisant un ExpressRoute de Silicon Valley.
  
![Express multisites routeur sur le même continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Déploiement en ligne - plusieurs sites sur différents continents

Si tous vos utilisateurs à l’aide Skype pour le service Business en ligne, et si vos sites sont dans plusieurs emplacements physiques sur plusieurs continents, si vous décidez de déployer ExpressRoute Azure, vous devez configurer au moins une connexion ExpressRoute pour chaque continent entre les sites de principale de chaque continent à son [emplacement homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)le plus proche. En fonction des coûts et avantages, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de sites où les objectifs de performances réseau ne sont pas remplies.
  
Dans l’exemple suivant, Contoso est un cabinet d’entreprise volumineux avec des bureaux en grandes villes Amérique du Nord et Europe. En fonction de leur connexion Internet et de leur évaluation des performances réseau interne, Contoso a décidé de déployer les deux connexions ExpressRoute en Amérique du Nord et circuit ExpressRoute unique pour toutes leurs bureaux en Europe.
  
![ExpressRoute avec plusieurs sites et continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Déploiement hybride

Si vous avez un Lync locaux ou Skype pour le déploiement d’entreprise et choisissez d’implémenter une hybride Skype pour l’intégration de l’entreprise en ligne, il est recommandé que si vous décidez de déployer ExpressRoute Azure, vous devez avoir au moins une connexion ExpressRoute pour chacun local Lync ou Skype pour le site de bord d’entreprise et au moins une connexion ExpressRoute pour chaque continent avec des bureaux. En fonction des coûts et avantages, pour chaque continent vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de bureaux où les objectifs de performances réseau ne sont pas remplies.
  
Si vous avez un Skype sur site pour le déploiement d’entreprise, vous devez suivre [Guide de déploiement et de planification de serveur Edge](https://technet.microsoft.com/en-us/library/mt346417.aspx). Plus précisément, les serveurs de périphérie doivent être accessibles à partir d’en dehors de votre réseau. Cela est généralement effectuée en affectant une adresse IP publique routable sur le serveur Edge ou en utilisant la traduction d’adresses réseau (NAT).
  
Dans l’exemple suivant, Contoso possède un Skype local existant pour le déploiement de voix entreprise. Ils souhaitent migrer les utilisateurs locaux vers Office 365 online services. Il est également décidé d’utiliser un déploiement hybride afin qu’ils peuvent continuer à utiliser leur infrastructure PSTN existante pour tous les utilisateurs en ligne et en local. Centre de données sur site et les Skype pour les serveurs de périphérie Business de Contoso sont à Chicago. Pour leur déploiement, Contoso a décidé de configurer une connexion ExpressRoute entre leurs centres de données de Chicago et la ExpressRoute Chicago. Ils également ajouté un ouest connexion ExpressRoute pour améliorer leur office Honolulu.
  
![ExpressRoute hybride.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Déploiement en ligne avec le nuage connecteur Edition

Skype pour l’édition Business Online nuage connecteur est un hybride offre qui se compose d’un ensemble de marchandises Machines virtuelles (VM) qui implémentent une connectivité PSTN sur site. En déployant un Skype minimal pour la topologie Business Server dans un environnement virtualisé, vous serez en mesure d’envoyer et recevoir des appels avec des réseaux terrestres et téléphones mobiles par le biais de l’infrastructure vocale PSTN locale existante.
  
Si vous décidez de déployer ExpressRoute Azure et le nuage connecteur Edition, que nous vous recommandons de configurer au moins une connexion itinéraire Express pour chaque continent entre le site principal de chaque continent à son plus proche [emplacement homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). En fonction des coûts et avantages, pour chaque continent vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires à partir de sites où les objectifs de performances réseau ne sont pas remplies.
  
Si vous avez un Skype sur site pour le déploiement d’entreprise, vous devez suivre le [Guide de planification pour Skype pour l’édition de connecteur Business Cloud](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Plus précisément, le serveur Edge d’accès et A / services Edge V doivent être affectées à des adresses IP publiques et est accessible à partir de centres de données Office 365.
  
Dans l’exemple suivant, Contoso est une entreprise comptable européenne dont la présence dans certains pays principales et villes. Lors de leur inscription pour Skype pour Business Online pour tous leurs besoins en matière de collaboration, ils décidé de mettre un connecteur dans le nuage pour chaque pays qu’ils ont un emplacement physique pour continuer à utiliser leur infrastructure PSTN et les contrats de support qui existent déjà. En fonction de leur test à partir de tous leurs sites et réseau Microsoft Edge, ils déterminé qu’une seule connexion ExpressRoute à Londres aider le Skype pour Business client connexion réseau performances cibles décrites dans [performances réseau configuration requise d’un Skype pour client d’entreprise à Microsoft réseau Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Un connecteur d’ExpressRoute Cloud.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Voici une autre option de déploiement de Contoso. Dans ce cas, a décidé de configurer une connexion ExpressRoute sur chaque site où un connecteur dans le nuage est déployé. 
  
![Connecteur de nuage ExpressRoute deux.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Rubriques connexes

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 