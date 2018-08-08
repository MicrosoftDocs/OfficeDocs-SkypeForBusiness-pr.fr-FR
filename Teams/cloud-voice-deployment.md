---
title: Déploiement de la fonctionnalité vocale cloud
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12c7f9378144134a0e09d90e838ca3bc62178ffb
ms.sourcegitcommit: 57c8211047e6e6501cd1f9eefddfe4da36cb7d7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20302134"
---
# <a name="cloud-voice-deployment"></a>Déploiement de la fonctionnalité vocale cloud

Microsoft Teams, le concentrateur de travail d’équipe et les communications dans Office 365, fournit à présent de conférence Audio, système téléphonique avec des Plans de l’appel, et système téléphonique Direct des fonctionnalités de routage pour répondre aux besoins métiers supplémentaires en étendant la réunion équipes et l’appel de l’expérience pour inclure les parties externes connectés via le réseau téléphonique commuté (RTC).
 
Nous allons mettre à jour cette page fonctionnalités de voix sur le nuage supplémentaires pour les équipes sont libérées au fil du temps.



## <a name="audio-conferencing-in-microsoft-teams"></a>Audioconférence dans Microsoft Teams


L’audioconférence dans Office 365 permet aux participants de rejoindre vos réunions Teams depuis n’importe quel téléphone.

Voici ce que vous obtenez à une [Conférence Audio](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) dans Office 365.


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Système téléphonique par l’appel de Plans (« Plans d’appel ») dans les équipes Microsoft

La fonctionnalité de système téléphonique d'Office 365 permet de gérer le routage des appels, les stratégies et l'affectation d'utilisateurs. Cela inclut le système de gestion des appels téléphoniques, le routage des appels et le contrôle des appels.

Plans d’appel sont un service complémentaire pour la fonctionnalité de système téléphonique, remis par le biais d’équipes et Skype pour Business Online. Plans d’appel requiert que l’utilisateur en question être hébergés sur Skype pour Business Online travailler dans Microsoft Teams. Plans d’appel fournir un numéro de téléphone principal des personnes dans votre entreprise et leur permet d’émettre et recevoir des appels téléphoniques à l’extérieur de votre organisation via le réseau RTC.

Pour plus d’informations, consultez [Voici ce que vous obtenez avec un système téléphonique dans Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) et [Quels sont les Plans de l’appel dans Office 365 ?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)


## <a name="phone-system-direct-routing-direct-routing"></a>Système de téléphone Direct routage (« routage Direct »)

Direct routage fonctionne avec la fonctionnalité de système téléphonique pour accorder au sein de votre organisation la possibilité d’émettre et recevoir des appels téléphoniques à l’extérieur de l’organisation via le réseau RTC, où une connectivité PSTN est fournie par le biais de fournisseurs de services tiers.

Pour plus d’informations, consultez [Planifier le routage Direct](direct-routing-plan.md) et [Configurer le routage Direct](direct-routing-configure.md).

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Conseils pratiques pour l’audioconférence, l’appel des Plans et au routage Direct dans Microsoft Teams

Ce guide pratique est organisé à l’aide de l’infrastructure de route du client Office 365 FastTrack et ses trois phases&mdash;prévoir, intégrée et la valeur lecteur. Il est destiné à vous aider à planifier, fournir et utiliser une mise en œuvre réussie de conférence Audio, des Plans de l’appel ou routage Direct.

> [!div class="mx-tableFixed"]
> |Concevoir  |Intégrer  |Générer une valeur ajoutée  |
> |---------|---------|---------|
> |[Définir mon réussite](1-envision-define-my-success-cloud-voice.md) <br> Prendre des décisions de mon service pour <br>&nbsp;&nbsp;[Services d’audioconférence](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[Plans d’appel](2-envision-make-my-service-decisions-phone-system.md)ou [directe de routage](2-envision-make-my-service-decisions-direct-routing.md) <br> [Évaluer mon environnement](3-envision-evaluate-my-environment.md) <br> [Planifier la gestion de mon service](4-envision-plan-my-service-management.md) <br> [Planifier l’expérience des utilisateurs](5-envision-plan-my-users-experience.md) <br> [Mon plan de réussite de documents](6-envision-document-my-success-plan.md)    | [Préparer mon service](1-onboard-prepare-my-service.md) <br> [Préparer les utilisateurs](2-onboard-prepare-my-users.md) <br> [Déployer mon service](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [Utiliser mon service](1-drive-value-operate-my-service.md) <br> [Améliorer mon service](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

Le contenu est présenté de manière ordonnée et est conçu pour vous guider un déplacement de déploiement de bout en bout de bout en bout. Si vous déployez déjà activement, nous conseillons toujours référencer les zones de contenu applicables.


> [!TIP]
> Dans ce guide pratique, nous proposons dans l’exemple, pour chaque discussion clée et de l’activité. Les exemples dans ce document sont placés à l’intérieur des légendes de Conseil et servir d’un modèle que vous pouvez réutiliser. Vous verrez « À déterminer » (à ajouter) pour les informations dont vous avez besoin pour effectuer dans le cadre de votre processus de planification.
