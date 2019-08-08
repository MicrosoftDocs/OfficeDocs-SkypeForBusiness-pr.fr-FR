---
title: Conditions préalables pour Microsoft teams | Mise à niveau des dépendances
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales du déploiement d’équipes au sein de votre organisation.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236070"
---
![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique] (media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur. Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Prérequis et dépendances environnementales pour les équipes

Teams combine plusieurs services 365 Office et dépend par conséquent de l’implémentation et de l’utilisation appropriées de ces services. Ces services incluent, sans s’y limiter, SharePoint Online, Exchange Online et OneDrive entreprise.

Même si certains services ne sont pas requis, nous vous conseillons vivement de les implémenter. Si vous choisissez de ne pas implémenter certains services, cela a un impact sur les fonctionnalités que teams peut fournir à votre organisation. Par exemple, si vous n’avez pas besoin d’implémenter SharePoint Online, Teams ne dépend pas de SharePoint Online pour certaines fonctionnalités, telles que le partage de fichiers dans les conversations de groupe, de sorte qu’il n’est pas nécessaire d’implémenter ce service pour réduire les fonctionnalités proposées via le sous.

Pour en savoir plus sur les conditions préalables et la façon dont les équipes interagissent avec d’autres technologies, voir les articles suivants:

- Si votre organisation n’a pas déployé de charges de travail 365 Office, voir [mise en route d’office 365 pour les entreprises](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Office 365, voir [vérifier votre domaine office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Si votre organisation n’a pas de synchronisation des identités dans Azure Active Directory, voir [modèles d’identité et authentification dans Microsoft teams](identify-models-authentication.md).

- Si votre organisation n’a pas l’application Exchange Online, voir [comprendre comment Exchange et Microsoft teams interagissent](Exchange-Teams-interact.md).

- Si votre organisation ne dispose pas de SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](SharePoint-OneDrive-interact.md).

- Découvrez comment [interagissent avec les groupes Office 365 et Microsoft teams](Office-365-groups.md).

- Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, vous devez [déployer School Data Sync](https://docs.microsoft.com/schooldatasync) avant de déployer Microsoft Teams.

Après avoir vérifié que votre environnement répond à tous les éléments requis concernés, [évaluez votre environnement actuel pour teams](upgrade-plan-journey-evaluate-environment.md).
