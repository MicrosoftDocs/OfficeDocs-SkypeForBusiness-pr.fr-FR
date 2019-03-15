---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Découvrez comment préparer et gérer votre réseau pour Microsoft Teams. Les informations comprennent la configuration réseau requise, la condition requise en matière de bande passante ainsi que des remarques supplémentaires.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640729"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams

> [!Tip]
> Regarder la session suivante pour en savoir comment les équipes s’appuie sur votre réseau et comment mieux planifier la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)


Les équipes combine les trois formes du trafic :

-   Trafic de données entre l’environnement en ligne d’Office 365 et le client équipes (signalisation, présence, conversation, téléchargement de fichier et téléchargement, la synchronisation de OneNote).

-   Trafic de communications en temps réel d’égal à égal (partage de bureau, vidéo et audio).

-   Trafic de communication en temps réel de conférence (audio, vidéo, bureau partage).

Cela a un impact sur le réseau à deux niveaux : flux de trafic entre les clients Microsoft Teams directement pour les scénarios d’égal à égal et passera le trafic entre l’environnement Office 365 et les clients Microsoft Teams pour les scénarios de réunion. Pour vérifier le flux de trafic optimales, le trafic doit être autorisé à circuler entre les segments réseau interne (par exemple, entre les sites sur le WAN) ainsi qu’entre les sites réseau et Office 365. Une expérience de dégradé n’entraîne pas ouvrir les ports corrects ou activement le blocage des ports spécifiques.

> [!NOTE]
> Les réunions sont pris en charge sur iOS et Android appareils mobiles. 

Pour obtenir une expérience optimale avec support en temps réel dans Microsoft Teams, votre réseau doit satisfaire la configuration réseau requise pour Office 365. Pour plus d’informations, voir [la qualité des médias et des performances pour la connectivité réseau pour Skype pour Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Pour les deux définition segments réseau (Client pour Microsoft Edge) et côté client pour Microsoft Edge, tenez compte des recommandations suivantes.


|Valeur  |Client Microsoft Edge  |Côté client pour Microsoft Edge  |
|:--- |:--- |:--- |
|**Latence (unidirectionnelle)**\*  |< aller-retour de 50 millisecondes          |< 30ms         |
|**Latence (durée aller-retour ou temps d’aller-retour)**\* |< 100 millisecondes   |< 60 MS |
|**Perte de paquets en rafale**    |<10 % au cours de l’intervalle de 200 MS         |<1 % au cours de l’intervalle de 200 MS         |
|**Perte de paquets**     |<1 % au cours des 15 s intervalle          |<0.1% pendant les 15 s intervalle         |
|**Gigue arrivée entre des batteries de paquets**    |<30ms pendant les 15 s intervalle         |<15ms pendant les 15 s intervalle         |
|**Réorganisation des paquets**    |paquets d’ordre <0.05%         |paquets d’ordre <0.01%         |

\*Les cibles de métrique latence supposent que votre entreprise ou les sites et les bords de Microsoft sont sur le même continent.

Connexion au site votre société et le bord du réseau Microsoft inclut premier accès tronçon réseau, qui peut être Wi-Fi ou une autre technologie sans fil.

Les objectifs de performances réseau supposent que la bande passante appropriée et/ou de [planification QoS](QoS-in-Teams.md). En d’autres termes, les conditions s’appliquent directement à du trafic multimédia en temps réel équipes lorsque la connexion réseau est soumis à une charge maximale.

Pour tester les deux segments réseau, vous pouvez utiliser l' [Outil d’évaluation de réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le client PC directement et sur un PC connecté à la périphérie du réseau client. L’outil comprend une documentation limitée, mais une documentation plue autour de l’utilisation de l’outil se trouvent ici : [Évaluation de préparation de réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant cette évaluation de préparation du réseau, vous pouvez valider la préparation de votre réseau d’exécuter des applications multimédia en temps réel, tels que Microsoft Teams.

> [!NOTE]
> Il s’agit de l’évaluation de préparation même réseau qui est recommandé d’exécuter pour les clients qui souhaitent pour déployer Skype pour les entreprises.


## <a name="bandwidth-requirements"></a>Bande passante requise

Calculs de bande passante pour Microsoft Teams sont complexes et pour aider, une calculatrice a été créée. Pour accéder à la Calculatrice, accédez au [Planificateur réseau](https://aka.ms/bwcalc/) dans MyAdvisor.

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

<a name="additional-network-considerations"></a>Considérations relatives au réseau supplémentaires
---------------

#### <a name="external-name-resolution"></a>Résolution de nom externe

Assurez-vous que tous les ordinateurs clients exécutant les équipes client peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365, et que votre pare-feu empêchent pas l’accès. Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Taille du Pool de NAT

Lorsque plusieurs utilisateurs/périphériques accéder à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou la traduction d’adresse de Port (PAT), vous devez vous assurer que les périphériques derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge.

Pour atténuer ce risque, assurez-vous adéquate des adresses IP publiques sont affectés aux pools de NAT pour éviter l’épuisement du port. Épuisement port entraînera interne aux utilisateurs et des périphériques de face problèmes lors de la connexion aux services Office 365. Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Détection d’intrusion et des conseils de prévention**

Si votre environnement comporte un système de prévention (intrusion) déployés pour un niveau supplémentaire de sécurité pour les connexions sortantes et/ou de détection d’Intrusion, vérifiez que tout le trafic à destination vers Office 365 URL autorisés.

<a name="network-health-determination"></a>Détermination de l’intégrité de réseau
-----------------

Lors de la planification de l’implémentation de Teams Microsoft au sein de votre réseau, vous devez vous assurer que la bande passante requise, vous avez accès à toutes les adresses IP requises, les ports corrects sont ouverts, et vous respectent les exigences de performances pour les médias en temps réel .

Si vous savez que vous ne respecte pas ces critères, vos utilisateurs finaux pas obtiendrez une expérience optimale des équipes en raison de la mauvaise qualité durant des réunions et appels.

Doivent pas répondre aux critères, c’est à la fois à prendre en compte l’interruption du projet afin de que vous répondent aux critères avant de poursuivre.


|  |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Point de décision         |Avez-vous évalué vos fonctionnalités de réseau pour la prise en charge multimédia en temps réel ?<br></br>Si votre réseau n’a pas été correctement évalué ou si vous savez qu’il ne prendra pas en charge multimédia en temps réel, vous désactivera vidéo et les capacités pour réduire l’impact sur le réseau et une mauvaise expérience équipes de partage d’écran ?         |
|![Icône Étapes suivantes.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Étapes suivantes         |Qualité du réseau inconnue : suivez les instructions de [l’Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) pour déterminer si votre réseau est prêt pour le média en temps réel.<br></br>Réseau qualité médiocre : Effectuez les étapes de correction de réseau pour fournir un environnement approprié pour une qualité multimédia en temps réel.<br></br>Réseau satisfaisant : Assurez-vous que tous les ports et adresses IP sont correctement accessibles.           |

## <a name="related-topics"></a>Rubriques connexes

[Vidéo : Planification du réseau](https://aka.ms/teams-networking)