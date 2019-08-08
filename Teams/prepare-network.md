---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Découvrez comment préparer et gérer votre réseau pour Microsoft Teams. Les informations comprennent la configuration réseau requise, la condition requise en matière de bande passante ainsi que des remarques supplémentaires.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31c06403dc3dec9322e984e012fe597254db8f33
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235178"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams


Teams associe trois types de trafic :

-   le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;

-   le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;

-   le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).

Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.

> [!NOTE]
> Les réunions sont prises en charge sur les appareils mobiles iOS et Android. 

Pour bénéficier d’une meilleure utilisation du contenu multimédia en temps réel au sein de Microsoft Teams, votre réseau doit respecter la configuration requise en matière de réseau pour Office 365. Pour plus d’informations, consultez la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter la configuration requise suivante.


|Valeur  |Client vers Microsoft Edge  |Périphérie client vers Microsoft Edge  |
|:--- |:--- |:--- |
|**Latence (unidirectionnelle)**\*  |< 50 ms          |< 30 ms         |
|**Latence (RTT ou durée de l’aller-retour)**\* |< 100 ms   |< 60 ms |
|**Perte de paquets en rafale**    |< 10 % sur un intervalle de 200 ms         |< 1% sur un intervalle de 200 ms         |
|**Perte de paquets**     |< 1 % sur un intervalle de 15 s          |< 0,1 % sur un intervalle de 15 s         |
|**Gigue entre les arrivées de paquets**    |< 30 ms sur un intervalle de 15 s         |< 15 ms sur un intervalle de 15 s         |
|**Réorganisation des paquets**    |< 0,05 % paquets désorganisés         |< 0,01% paquets désorganisés         |

\*Les cibles métriques de latence présupposent que le site ou les sites de votre entreprise et les bords Microsoft se trouvent sur le même continent.

La connexion au site de votre entreprise avec le réseau de périmètre Microsoft inclut un accès réseau de premier saut, qui peut être WiFi ou une autre technologie sans fil.

Les cibles de performance réseau adoptent une planification de bande passante et/ou de [QoS](QoS-in-Teams.md)correcte. En d’autres termes, les exigences s’appliquent directement au trafic multimédia en temps réel lors de la connexion réseau.

Pour obtenir de l’aide concernant la préparation de votre réseau pour Teams, voir [Planificateur de réseaux](https://docs.microsoft.com/microsoftteams/network-planner).


## <a name="bandwidth-requirements"></a>Condition requise pour la bande passante
Microsoft teams vous offre la meilleure expérience audio, vidéo et de partage de contenu quelle que soit l’état de votre réseau. Grâce aux codecs variables, le média peut être négocié dans les environnements à bande passante limitée avec un impact minimal. Même si la bande passante n’est pas un problème, les expériences peuvent être optimisées en matière de qualité, y compris jusqu’à 1080p résolutions vidéo, jusqu’à 30 IPS pour la vidéo et 15fps pour le contenu et le son haute fidélité.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>Considérations relatives au réseau supplémentaire
---------------

#### <a name="external-name-resolution"></a>Résolution de noms externes

Assurez-vous que tous les ordinateurs clients exécutant teams peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365 et que vos pare-feu n’empêchent pas l’accès. Pour plus d’informations sur la configuration des ports de pare-feu, voir [URL et plages d’adresses IP Office 365](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Taille du pool NAT

Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (PAT), vous devez vous assurer que les périphériques cachés derrière chaque adresse IP routable publique ne dépassent pas le numéro pris en charge.

Pour atténuer ce risque, assurez-vous que les adresses IP publiques appropriées sont affectées aux pools NAT pour empêcher l’épuisement du port. L’épuisement du port permettra aux utilisateurs finaux et aux appareils internes d’affronter de rencontrer des problèmes lors de la connexion aux services Office 365. Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Recommandations en matière de détection d’intrusion et de prévention**

Si votre environnement dispose d’une détection d’intrusions et/ou d’un système de prévention (IDS/IPS) déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout le trafic lié aux URL d’Office 365 est affiché dans la zone d’autorisation.

<a name="network-health-determination"></a>Détermination de l’état du réseau
-----------------

Lors de la planification de l’implémentation de Microsoft teams au sein de votre réseau, vous devez vous assurer que vous disposez bien de la bande passante requise, que vous avez accès à toutes les adresses IP requises, que les ports appropriés sont ouverts et que vous respectez les performances requises pour le média en temps réel. .

Si vous êtes certain de ne pas répondre à ces critères, vos utilisateurs finaux ne bénéficieront pas d’une meilleure connaissance des équipes en raison d’une mauvaise qualité lors des appels et des réunions.

Dans le cas contraire, il s’agit du délai nécessaire pour envisagez de suspendre le projet pour vous assurer que vous répondez aux critères avant de continuer.


|  |  |  |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Point de décision         |Avez-vous évalué vos capacités réseau pour la prise en charge de médias en temps réel?<br></br>Si votre réseau n’a pas été correctement évalué ou s’il ne prend pas en charge les contenus multimédias en temps réel, vous pouvez désactiver les fonctionnalités de partage vidéo et d’écran afin de réduire l’impact sur le réseau et de mauvaises expériences d’équipe.         |
|![Icône représentant les étapes suivantes](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Étapes suivantes         |Qualité du réseau inconnue: effectuez une analyse de compatibilité réseau pour déterminer si votre réseau est prêt pour le média en temps réel.<br></br>Qualité du réseau médiocre: suivez les étapes de la reconversion réseau pour proposer un environnement approprié pour le média en temps réel de haute qualité.<br></br>Réseau satisfaisant: Assurez-vous que toutes les adresses IP et tous les ports sont accessibles correctement.           |

## <a name="related-topics"></a>Rubriques connexes

[Vidéo: planification du réseau](https://aka.ms/teams-networking)
