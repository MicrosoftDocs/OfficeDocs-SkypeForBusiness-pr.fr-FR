---
title: Conditions préalables et dépendances sur l’environnement pour la mise à niveau vers Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales pour le déploiement d’Équipes dans votre organisation
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
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092192"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Conditions préalables et dépendances de l’environnement pour Teams

![Diagramme de voyage de mise à niveau mettant en relief la phase de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la phase de préparation technique")

Cet article fait partie de la phase de préparation technique de votre voyage de mise à niveau, une activité que vous terminez en parallèle de la phase de préparation utilisateur. Avant de poursuivre, confirmez que vous avez effectué ces activités à partir des étapes précédentes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combine plusieurs services Microsoft 365 et Office 365 et dépend donc de l’implémentation et de l’opération correctes de ces services. Ces services comprennent notamment SharePoint Online, Exchange Online et OneDrive Entreprise.

Bien que certains services ne soient pas obligatoires, nous vous recommandons vivement de les implémenter tous. Si vous choisissez de ne pas implémenter certains services, cela affectera les fonctionnalités que Teams peut offrir à votre organisation. Par exemple, même si vous n’avez pas à implémenter SharePoint Online, Teams s’appuie sur SharePoint Online pour certaines fonctionnalités telles que le partage de fichiers dans les conversations de groupe. Par donc, le fait de ne pas implémenter ce service réduit les fonctionnalités offertes par le biais du client.

Consultez les articles suivants pour en savoir plus sur les conditions préalables et la manière dont Teams interagit avec les autres technologies :

- Si votre organisation n’a pas déployé de charge de travail Microsoft 365 ou Office 365, voir [Commencer.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez le Forum aux [questions des domaines.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Si votre organisation n’a pas synchronisé les identités avec Azure Active Directory, consultez les modèles d’identité et [l’authentification dans Microsoft Teams.](identify-models-authentication.md)

- Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Comprendre l’interaction entre Exchange et Microsoft Teams](Exchange-Teams-interact.md).

- Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Comprendre l’interaction entre SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).

- Pour découvrir comment les [groupes Microsoft 365 et Microsoft Teams interagissent.](Office-365-groups.md)

- Si votre organisation est un établissement d’enseignement et que vous utilisez un système d’information sur les étudiants, voir Bienvenue dans [Microsoft School Data Sync](/schooldatasync) avant de déployer Microsoft Teams.

- Si votre organisation envisage d’envisager des options d’appel de réseau téléphonique commuté (PSTN), consultez la connectivité Voix - Système téléphonique et [PSTN,](cloud-voice-landing-page.md)le [plan](calling-plan-landing-page.md)d’appels qui vous est le plus exact et le routage direct du système [téléphonique.](direct-routing-landing-page.md)

- Pour vous assurer que toutes les exigences réseau ont été respectées avant de déployer Teams, consultez Préparer le réseau de votre organisation [pour Microsoft Teams.](prepare-network.md)

- Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants. Pour [plus d’informations,](teams-powershell-move-from-sfbo.md) voir Déplacer de Skype Entreprise Online Connector vers le module Teams PowerShell.

Après avoir vérifié que votre environnement répond à toutes les conditions préalables applicables, évaluez [votre environnement actuel pour Teams.](upgrade-plan-journey-evaluate-environment.md)