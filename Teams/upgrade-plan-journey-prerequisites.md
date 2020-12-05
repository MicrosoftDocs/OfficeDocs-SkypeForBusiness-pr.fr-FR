---
title: Conditions préalables et dépendances environnementales pour la mise à niveau vers teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales pour le déploiement d’équipes au sein de votre organisation.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578277"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Prérequis et dépendances environnementales pour les équipes

![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur. Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combine plusieurs services Microsoft 365 et Office 365 et dépend par conséquent du bon fonctionnement et de l’application de ces services. Ces services incluent, sans s’y limiter, SharePoint Online, Exchange Online et OneDrive entreprise.

Même si certains services ne sont pas requis, nous vous conseillons vivement de les implémenter. Si vous choisissez de ne pas implémenter certains services, cela a un impact sur les fonctionnalités que teams peut fournir à votre organisation. Par exemple, si vous n’avez pas besoin d’implémenter SharePoint Online, Teams ne dépend pas de SharePoint Online pour certaines fonctionnalités, telles que le partage de fichiers dans les conversations de groupe, de sorte qu’il n’est pas nécessaire d’implémenter ce service pour réduire les fonctionnalités proposées par le client.

Pour en savoir plus sur les conditions préalables et la façon dont les équipes interagissent avec d’autres technologies, voir les articles suivants :

- Si votre organisation n’a pas déployé de charges de travail Microsoft 365 ou Office 365, voir [commencer](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, voir [Forum aux questions sur les domaines](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Si votre organisation n’a pas de synchronisation des identités dans Azure Active Directory, voir [modèles d’identité et authentification dans Microsoft teams](identify-models-authentication.md).

- Si votre organisation n’a pas Exchange Online, voir [comprendre comment Exchange et Microsoft teams interagissent](Exchange-Teams-interact.md).

- Si votre organisation ne dispose pas de SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](SharePoint-OneDrive-interact.md).

- Pour plus d’informations sur l' [interaction entre les groupes microsoft 365 et Microsoft teams](Office-365-groups.md).

- Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, voir [Bienvenue dans Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) avant de déployer Microsoft Teams.

- Si votre organisation envisagez des options d’appel de réseau téléphonique commuté (PSTN), consultez la section [système téléphonique et connectivité PSTN](cloud-voice-landing-page.md), l' [offre qui vous convient et le](calling-plan-landing-page.md) [routage direct du système téléphonique](direct-routing-landing-page.md).

- Pour vous assurer que toutes les exigences réseau sont remplies avant le déploiement d’équipes, reportez-vous à [la rubrique préparer le réseau de votre organisation à Microsoft teams](prepare-network.md).

Après avoir vérifié que votre environnement répond à tous les éléments requis concernés, [évaluez votre environnement actuel pour teams](upgrade-plan-journey-evaluate-environment.md).
