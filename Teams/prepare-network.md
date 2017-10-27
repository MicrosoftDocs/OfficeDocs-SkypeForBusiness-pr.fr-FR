---
title: "Préparer le réseau de votre organisation pour Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment préparer et gérer votre réseau pour Microsoft Teams. Les informations comprennent la configuration réseau requise, la condition requise en matière de bande passante ainsi que des remarques supplémentaires."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 79e7cd9e9ebef793c138e9482c7bc56c692e4ed1
ms.sourcegitcommit: a052a9d4db0a543f491bbd4708ca5a453145e2ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams
=================================================

Microsoft Teams associe trois types de trafic :

-   Trafic de données entre l'environnement en ligne Office 365 et le client Microsoft Teams (signalisation, présence, conversation, chargement et téléchargement de fichiers, synchronisation OneNote)

-   Trafic des communications P2P en temps réel (audio, vidéo, partage de bureau)

-   Trafic des communications liées aux réunions en temps réel (audio, vidéo, partage de bureau)

Cela affecte le réseau sur deux niveaux : le trafic est acheminé des clients Microsoft Teams directement pour les communications P2P et le trafic est acheminé entre l'environnement Office 365 et les clients Microsoft Teams dans le cas des réunions. Pour assurer un flux optimal, le trafic doit pouvoir être acheminé à la fois entre les segments réseau (par ex. : entre des sites sur le réseau WAN) et entre les sites réseau et Office 365. Si les ports appropriés ne sont pas ouverts ou que des ports spécifiques sont activement bloqués, cela risque de dégrader la qualité de l'expérience.

|  |  |
|---------|---------|
|![](media/Prepare_your_organizations_network_for_Microsoft_Teams_image1.png)<br></br>Important    |Les réunions sont actuellement prises en charge sur les appareils iOS et Android, mais pas sur les appareils Windows (disponible très prochainement).       |

Pour bénéficier d'une expérience optimale avec le multimédia en temps réel dans Microsoft Teams, la configuration réseau requise pour Office 365 doit être satisfaite (pour plus de détails, consultez la source suivante : [Qualité multimédia  et performances de connectivité réseau dans Skype Entreprise Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US) )

Les deux segments réseau de définition (Client vers Microsoft Edge et périphérie client vers Microsoft Edge) doivent respecter la configuration requise suivante :


|Valeur  |Client vers Microsoft Edge  |Périphérie client vers Microsoft Edge  |
|---------|---------|---------|
|**Latence (unidirectionnelle)**     |< 50 ms          |< 30 ms          |
|**Latence (RTT or durée de l'aller-retour)** |< 100 ms         |< 60 ms         |
|**Perte de paquets en rafale**    |< 10 % sur un intervalle de 200 ms         |< 1 % sur un intervalle de 200 ms         |
|**Perte de paquets**     |< 1 % sur un intervalle de 15 s          |< 0,1 % sur un intervalle de 15 s         |
|**Gigue entre les arrivées de paquets**    |< 30 ms sur un intervalle de 15 s         |< 15 ms sur un intervalle de 15 s         |
|**Réorganisation des paquets**    |< 0,05 % paquets désorganisés         |< 0,01 % paquets désorganisés         |

Pour tester les deux segments réseau, vous pouvez utiliser un outil d'évaluation de réseau (source : [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). Cet outil peut être déployé sur le PC client directement et sur un PC/ordinateur portable connecté au périphérique réseau client. La documentation de l'outil est limitée, mais vous trouverez plus de détails sur son utilisation en consultant le document suivant : [Évaluation de la disponibilité réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant l'outil d'évaluation de la disponibilité réseau, vous pouvez valider la disponibilité de votre réseau pour exécuter des applications multimédia en temps réel, telles que Microsoft Teams.

|  |  |
|---------|---------|
|![](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>Remarque    |Il s'agit de la même évaluation de disponibilité réseau recommandée pour les clients qui souhaitent déployer correctement Skype Entreprise.         |

<a name="bandwidth-requirements"></a>Condition requise pour la bande passante
----------

Les calculs de bande passante pour Microsoft Teams sont complexes et une calculatrice a été créée à cet effet. Pour accéder à la calculatrice, cliquez ici : <http://aka.ms/bwcalc/>.

Le contenu ci-après peut être utilisé comme informations générales supplémentaires ; il est toutefois recommandé aux clients d'utiliser la [calculatrice de bande passante](https://aka.ms/bwcalc) pour effectuer le suivi de leurs besoins.

|  |  |
|---------|---------|
|![](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>Remarque    |Si la bande passante requise n'est pas disponible, la pile multimédia de Microsoft Teams dégradera la qualité de la session audio/vidéo session pour s'adapter à la quantité de bande passante disponible plus faible, ce qui affectera la qualité de l'appel ou de la réunion. Le client Microsoft Teams tentera de privilégier la qualité de l'audio plutôt que la vidéo. C'est pourquoi il est très important de disposer de la bande passante requise.       |


|Activité  |Bande passante de téléchargement  |Bande passante de chargement  |Flux du trafic |
|---------|---------|---------|---------|
|**Appel audio P2P**     |0,1 Mo         |0,1 Mo         |Client <> Client         |
|**Appel vidéo P2P (plein écran)**     |4 Mo         |4 Mb         |Client <> Client          |
|**Partage de bureau P2P (résolution 1920*1080)**     |4 Mo         |4 Mo         |Client <> Client          |
|**Réunion comptant 2 participants**     |4 Mo         |4 Mo         |Client <> Office 365         |
|**Réunion comptant 3 participants**     |8 Mo         |6,5 Mo         |Client <> Office 365           |
|**Réunion comptant 4 participants**     |5,5 Mo         |4 Mo         |Client <> Office 365           |
|**Réunion comptant plus de 5 participants**     |6 Mo         |1,5 Mo         |Client <> Office 365           |


<a name="additional-network-considerations"></a>Remarques supplémentaires relatives au réseau
---------------

#### <a name="external-name-resolution"></a>**Résolution des noms externes**

Assurez-vous que tous les ordinateurs client exécutant Microsoft Teams peuvent résoudre les requêtes DNS externes pour détecter les services fournis par Office 365.

#### <a name="nat-pool-size"></a>**Taille du pool NAT**

Lorsque plusieurs utilisateurs/appareils accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les appareils placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.

Pour limiter ce risque, veillez à affecter des adresses IP publiques adéquates aux pools NAT pour éviter tout épuisement de port. L'épuisement de port implique des problèmes de connexion aux services Office 365 pour les utilisateurs finaux et les appareils internes. Pour plus d'informations, consultez le guide [Prise en charge NAT avec Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Instructions pour la détection et la prévention d'intrusion**

Si votre environnement disposent d'un système de détection et/ou de prévention d'intrusion (IDS/IPS) déployé pour obtenir une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout trafic vers des URL Office 365 est placé sur liste verte.

<a name="network-health-determination"></a>Détermination de l'intégrité réseau
-----------------

Lors de la planification de l'implémentation de Microsoft Teams dans votre réseau, vous devez vous assurer de disposer de la bande passante requise, d'accéder à toutes les adresses IP requises, que les ports corrects sont ouverts et respectent les conditions de performances pour le multimédia en temps réel.

Si vous êtes conscient que ces critères ne sont pas satisfaits, vos utilisateurs finaux ne bénéficieront pas d'une expérience optimale de Microsoft Teams en raison de la mauvaise qualité pendant les appels et les réunions.

Si les critères ne sont pas remplis, il convient d'interrompre le projet pour vous assurer de satisfaire les critères avant de continuer.


|  |  |  |
|---------|---------|---------|
|![](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Point de décision         |Avez-vous évalué les capacités de votre réseau pour la prise en charge multimédia en temps réel ?<br></br>Si votre réseau n'est pas correctement évalué ou que vous êtes conscient qu'il ne prendra pas en charge le trafic multimédia en temps réel, désactiverez-vous les fonctionnalités vidéo et de partage d'écran pour limiter l'impact sur le réseau et la qualité médiocre de l'expérience avec Teams ?         |
|![](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Étapes suivantes         |Qualité réseau inconnue : Suivez les instructions sur l'évaluation de la disponibilité réseau sur skypeoperationsframework.com pour déterminer si votre réseau est préparé pour le trafic multimédia en temps réel.<br></br>Qualité réseau médiocre : Réalisez les étapes de correction du réseau pour mettre à disposition un environnement adéquat pour le trafic multimédia en temps réel de haute qualité.<br></br>Réseau satisfaisant : Vérifiez que l'ensemble des adresses IP et des ports sont accessibles.           |

