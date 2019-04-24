---
title: Déploiement de la fonctionnalité vocale cloud
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4089e0e9ff9ce0ecbff63e55a43d2dc9f2ca7d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194756"
---
# <a name="cloud-voice-deployment"></a>Déploiement de la fonctionnalité vocale cloud

Microsoft Teams, la plateforme dédiée au travail en équipe et aux communications dans Office 365, fournit désormais des fonctionnalités d'audioconférence, de système téléphonique avec des forfaits d’appels et de routage direct via le système téléphonique, afin de répondre à des besoins supplémentaires en étendant l'expérience d'appels et de réunions Teams pour inclure les participants externes qui se connectent via le réseau téléphonique commuté (PSTN).


> [!Tip] 
> Regarder la session pour une introduction aux systèmes téléphoniques suivante : [Introduction au système téléphonique dans les équipes Microsoft](https://aka.ms/teams-phone-system)
 
Nous allons mettre à jour cette page fonctionnalités de voix sur le nuage supplémentaires pour les équipes sont libérées au fil du temps.



## <a name="audio-conferencing-in-microsoft-teams"></a>Audioconférence dans Microsoft Teams


L’audioconférence dans Office 365 permet aux participants de rejoindre vos réunions Teams depuis n’importe quel téléphone.

Voici ce que vous obtenez à une [Conférence Audio](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) dans Office 365.


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Système téléphonique par l’appel de Plans (« Plans d’appel ») dans les équipes Microsoft

Système téléphonique est une fonctionnalité d’Office 365 qui offre la possibilité de gérer le routage des appels, des stratégies et mise en service de l’utilisateur. Cela inclut le système de gestion, le routage des appels et le contrôle d’appel téléphonique.

Plans d’appel sont un service complémentaire pour la fonctionnalité de système téléphonique, remis par le biais d’équipes et Skype pour Business Online. Plans d’appel requiert que l’utilisateur en question être hébergés sur Skype pour Business Online travailler dans Microsoft Teams. Plans d’appel fournir un numéro de téléphone principal des personnes dans votre entreprise et leur permet d’émettre et recevoir des appels téléphoniques à l’extérieur de votre organisation via le réseau RTC.

Pour plus d’informations, voir [Voici ce que vous obtenez avec un système téléphonique dans Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) et [système téléphonique et Plans de l’appel](calling-plan-landing-page.md)


## <a name="phone-system-direct-routing-direct-routing"></a>Système de téléphone Direct routage (« routage Direct »)

Direct routage fonctionne avec la fonctionnalité de système téléphonique pour accorder au sein de votre organisation la possibilité d’émettre et recevoir des appels téléphoniques à l’extérieur de l’organisation via le réseau RTC, où une connectivité PSTN est fournie par le biais de fournisseurs de services tiers.

Pour plus d’informations, consultez [Planifier le routage Direct](direct-routing-plan.md) et [Configurer le routage Direct](direct-routing-configure.md).

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Conseils pratiques pour l’audioconférence, l’appel des Plans et au routage Direct dans Microsoft Teams

Ce guide pratique est organisé à l’aide de l’infrastructure de route du client Office 365 FastTrack et ses trois phases&mdash;prévoir, intégrée et la valeur lecteur. Il est destiné à vous aider à planifier, fournir et utiliser une mise en œuvre réussie de conférence Audio, des Plans de l’appel ou routage Direct.

> [!div class="mx-tableFixed"]
> |Concevoir  |Intégrer  |Générer une valeur ajoutée  |
> |---------|---------|---------|
> |[Définir ma réussite](1-envision-define-my-success-cloud-voice.md) <br> Prendre des décisions de mon service pour <br>&nbsp;&nbsp;[Services d’audioconférence](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[Plans d’appel](2-envision-make-my-service-decisions-phone-system.md)ou [directe de routage](2-envision-make-my-service-decisions-direct-routing.md) <br> [Évaluer mon environnement](3-envision-evaluate-my-environment.md) <br> [Planifier ma gestion des services](4-envision-plan-my-service-management.md) <br> [Planifier l’expérience des utilisateurs](5-envision-plan-my-users-experience.md) <br> [Documenter mon plan de réussite](6-envision-document-my-success-plan.md)    | [Préparer mon service](1-onboard-prepare-my-service.md) <br> [Préparer mes utilisateurs](2-onboard-prepare-my-users.md) <br> [Déployer mon service](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [Exploiter mon service](1-drive-value-operate-my-service.md) <br> [Améliorer mon service](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

Le contenu est présenté de manière ordonnée et est conçu pour vous guider un déplacement de déploiement de bout en bout de bout en bout. Si vous déployez déjà activement, nous conseillons toujours référencer les zones de contenu applicables.


> [!TIP]
> Dans ce guide pratique, nous proposons dans l’exemple, pour chaque discussion clée et de l’activité. Les exemples dans ce document sont placés à l’intérieur des légendes de Conseil et servir d’un modèle que vous pouvez réutiliser. Vous verrez « À déterminer » (à ajouter) pour les informations dont vous avez besoin pour effectuer dans le cadre de votre processus de planification.
