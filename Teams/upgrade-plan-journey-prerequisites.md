---
title: Conditions préalables des équipes Microsoft | Mise à niveau de dépendances d’Adoption
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Utilisez ce guide pour en savoir plus sur les conditions préalables et les dépendances de l’environnement pour déployer des équipes au sein de votre organisation.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462043"
---
![Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique] (media/upgrade-banner-tech-readiness.png "Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de la phase de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez en parallèle à l’étape de préparation des utilisateurs. Avant de continuer, vérifiez que vous avez terminé ces activités à partir des étapes précédentes :

- [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choisi votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Conditions préalables et les dépendances de l’environnement pour les équipes

Les équipes combine plusieurs services Office 365 et est donc dépendent de la mise en oeuvre correcte et le fonctionnement de ces services. Ces services englobent, mais ne sont pas limitées à, SharePoint Online, Exchange Online et OneDrive for Business.

Bien que tous les services sont nécessaires, nous vous recommandons vivement de tous les implémenter. Si vous choisissez de ne pas mettre en œuvre certains services, elle affecte les fonctionnalités que les équipes peuvent offrir à votre entreprise. Par exemple, si vous ne disposez pas d’implémenter SharePoint Online, les équipes s’appuie sur SharePoint Online pour certaines fonctionnalités telles que le partage de fichiers dans des conversations de groupe, donc ne pas l’implémentation de ce service permet de réduire les fonctionnalités offertes par le biais de la client.

Voir les articles suivants pour en savoir plus sur les conditions préalables et la façon dont les équipes interagit avec d’autres technologies :

- Si votre organisation n’a pas déployé les charges de travail Office 365, voir [Mise en route avec Office 365 pour entreprises](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Office 365, voir [vérifier votre domaine à Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Si votre organisation n’a pas synchronisé identités pour Azure Active Directory, voir [modèles d’identité et authentification dans les équipes Microsoft](identify-models-authentication.md).

- Si vous disposez d’un doesn¹t de votre organisation Exchange Online, voir [comprendre interagissent entre Exchange et les équipes Microsoft](Exchange-Teams-interact.md).

- Si votre organisation ne possède pas SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec les équipes Microsoft](SharePoint-OneDrive-interact.md).

- Découvrez comment [interagissent groupes Office 365 et les équipes Microsoft](Office-365-groups.md).

- Si votre organisation est un établissement scolaire et que vous utilisez un système d’Information pour l’étudiant, [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync) avant de déployer Microsoft Teams.

Après avoir vérifié que votre environnement remplit les conditions préalables d’applicables tous, [évaluer l’environnement actuel pour les équipes](upgrade-plan-journey-evaluate-environment.md).