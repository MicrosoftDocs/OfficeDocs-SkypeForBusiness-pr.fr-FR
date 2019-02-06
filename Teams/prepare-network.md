---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Découvrez comment préparer et gérer votre réseau pour Microsoft Teams. Les informations comprennent la configuration réseau requise, la condition requise en matière de bande passante ainsi que des remarques supplémentaires.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6b95da8ee416d4f64d22a8c0622acd417b7bb1d
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742847"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams
=================================================

> [!Tip]
> Regarder la session suivante pour en savoir comment les équipes s’appuie sur votre réseau et comment mieux planifier la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)


Teams associe trois types de trafic :

-   le trafic de données entre l'environnement en ligne Office 365 et le client Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote) ;

-   le trafic des communications P2P en temps réel (audio, vidéo, partage de bureau) ;

-   le trafic des communications de conférence en temps réel (audio, vidéo, partage de bureau).

Cela affecte le réseau sur deux niveaux : le trafic est acheminé entre les clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.

> [!NOTE]
> Les réunions sont pris en charge sur iOS et Android appareils mobiles. 

Pour bénéficier d'une expérience optimale avec le multimédia en temps réel dans Microsoft Teams, la configuration réseau requise pour Office 365 doit être satisfaite. Pour plus d’informations, consultez la rubique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Pour les deux définition segments réseau (Client pour Microsoft Edge) et côté client pour Microsoft Edge, tenez compte des recommandations suivantes.


|Valeur  |Client vers Microsoft Edge  |Périphérie client vers Microsoft Edge  |
|---------|---------|---------|
|**Latence (unidirectionnelle)**     |< 50 ms          |< 30 ms          |
|**Latence (RTT or durée de l'aller-retour)** |< 100 ms         |< 60 ms         |
|**Perte de paquets en rafale**    |< 10 % sur un intervalle de 200 ms         |< 1% sur un intervalle de 200 ms         |
|**Perte de paquets**     |< 1 % sur un intervalle de 15 s          |< 0,1 % sur un intervalle de 15 s         |
|**Gigue entre les arrivées de paquets**    |< 30 ms sur un intervalle de 15 s         |< 15 ms sur un intervalle de 15 s         |
|**Réorganisation des paquets**    |< 0,05 % paquets désorganisés         |< 0,01% paquets désorganisés         |

Pour tester les deux segments réseau, vous pouvez utiliser l’[Outil d'évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le PC client directement et sur un PC connecté au périphérique réseau client. Il inclut une documentation restreinte, mais une documentation plus approfondie concernant l’utilisation de l’outil est disponible ici : [Évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant cet outil d’évaluation de la préparation du réseau, vous pouvez valider la préparation de votre réseau à exécuter des applications multimédias en temps réel telles que Microsoft Teams.

> [!NOTE]
> Il s'agit de la même évaluation de disponibilité réseau recommandée pour les clients qui souhaitent déployer correctement Skype Entreprise.

<a name="bandwidth-requirements"></a>Condition requise pour la bande passante
----------

Les calculs de bande passante pour Microsoft Teams sont complexes et une calculatrice a été créée à cet effet. Pour accéder à la calculatrice, cliquez ici : [Planificateur de réseau dans MyAdvisor](https://aka.ms/bwcalc/).

> [!NOTE]
> Améliore la gestion de bande passante équipes sur Skype pour Business Online : pour une haute qualité appelant ou l’expérience (audio, vidéo et partage) de la réunion, les équipes nécessite uniquement 1,2 Mbits/s. Il peut également évoluer davantage de très haute qualité s’il existe suffisamment de bande passante disponible. Lorsqu’une demande d’équipes rencontre une condition de faible bande passante, les équipes peuvent rapidement Ajustez à nouveau l’utilisation de la bande passante pour s’adapter à la bande passante disponible.

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

<a name="additional-network-considerations"></a>Remarques supplémentaires relatives au réseau
---------------

#### <a name="external-name-resolution"></a>**Résolution des noms externes**

Assurez-vous que tous les ordinateurs client exécutant Teams peuvent résoudre les requêtes DNS externes pour détecter les services fournis par Office 365.

#### <a name="nat-pool-size"></a>**Taille du pool NAT**

Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les appareils placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.

Pour atténuer ce risque, assurez-vous que les adresses IP publiques adéquates sont affectées aux pools NAT pour éviter toute insuffisance de ports. Si les ports sont insuffisants, les utilisateurs finaux internes et les périphériques rencontreront des problèmes lorsqu'ils se connecteront aux services Office 365. Pour plus d’informations, consultez la rubrique [Prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Instructions pour la détection et la prévention d'intrusion**

Si votre environnement disposent d'un système de détection et/ou de prévention d'intrusion (IDS/IPS) déployé pour obtenir une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout trafic vers des URL Office 365 est placé sur liste verte.

<a name="network-health-determination"></a>Détermination de l'intégrité réseau
-----------------

Lors de la planification de l'implémentation de Microsoft Teams dans votre réseau, vous devez vous assurer de disposer de la bande passante requise, d'avoir accès à toutes les adresses IP requises, que les ports corrects sont ouverts et que les conditions requises en matière de performances pour le multimédia en temps réel sont respectées.

Si ces critères ne sont pas satisfaits, vos utilisateurs finaux ne bénéficieront pas d'une expérience optimale de Teams en raison de la mauvaise qualité pendant les appels et les réunions.

Si les critères ne sont pas remplis, il convient d'interrompre le projet pour vous assurer de satisfaire les critères avant de continuer.


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Point de décision         |Avez-vous évalué les capacités de votre réseau pour la prise en charge multimédia en temps réel ?<br></br>Si votre réseau n'est pas correctement évalué ou que vous êtes conscient qu'il ne prendra pas en charge le trafic multimédia en temps réel, désactiverez-vous les fonctionnalités vidéo et de partage d'écran pour limiter l'impact sur le réseau et la qualité médiocre de l'expérience avec Teams ?         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Étapes suivantes         |Qualité réseau inconnue : suivez les instructions sur [l’évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est préparé pour le trafic multimédia en temps réel.<br></br>Qualité réseau médiocre : Réalisez les étapes de correction du réseau pour mettre à disposition un environnement adéquat pour le trafic multimédia en temps réel de haute qualité.<br></br>Réseau satisfaisant : Vérifiez que l'ensemble des adresses IP et des ports sont accessibles.           |

## <a name="related-topics"></a>Rubriques connexes

[Vidéo : Planification du réseau](https://aka.ms/teams-networking)