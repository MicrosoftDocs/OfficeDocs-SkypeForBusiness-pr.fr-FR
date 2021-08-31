---
title: Conditions préalables et dépendances sur l’environnement pour la mise à niveau vers Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales pour le déploiement Teams votre organisation
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725453"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Conditions préalables et dépendances de l’environnement pour Teams

![Diagramme de voyage de mise à niveau mettant en relief la phase de préparation technique.](media/upgrade-banner-tech-readiness.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la phase de préparation technique")

Cet article fait partie de la phase de préparation technique de votre voyage de mise à niveau, une activité que vous terminez en parallèle de la phase de préparation utilisateur. Avant de poursuivre, confirmez que vous avez effectué ces activités à partir des étapes précédentes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combine plusieurs services Microsoft 365 Office 365 et dépend donc de l’implémentation et de l’opération correctes de ces services. Ces services comprennent , mais ne sont pas limités, SharePoint Online, Exchange Online et OneDrive Entreprise.

Bien que certains services ne soient pas obligatoires, nous vous recommandons vivement de les implémenter tous. Si vous choisissez de ne pas implémenter certains services, cela affectera les fonctionnalités que Teams pouvez offrir à votre organisation. Par exemple, même si vous n’avez pas à implémenter SharePoint Online, Teams utilise SharePoint Online pour certaines fonctionnalités telles que le partage de fichiers dans les conversations de groupe. Par donc, si vous ne l’implémentez pas, les fonctionnalités offertes par le client seront réduites.

Consultez les articles suivants pour en savoir plus sur les conditions préalables et Teams interactions entre les autres technologies :

- Si votre organisation n’a pas déployé d’Microsoft 365 charges Office 365 charges de travail, voir [Commencer.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez [le Forum aux questions des](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)domaines.

- Si votre organisation n’a pas synchronisé les identités avec les Azure Active Directory, consultez les modèles d’identité et [l’authentification dans Microsoft Teams.](identify-models-authentication.md)

- Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Comprendre l’interaction entre Exchange et Microsoft Teams](Exchange-Teams-interact.md).

- Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Comprendre l’interaction entre SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).

- Pour découvrir comment les [Microsoft 365 et comment Microsoft Teams interagir.](Office-365-groups.md)

- Si votre organisation est un établissement d’enseignement et que vous utilisez un système d’information sur les étudiants, voir Bienvenue dans [Microsoft Synchronisation des données scolaires](/schooldatasync) avant de déployer Microsoft Teams.

- Si votre organisation envisage d’envisager des options d’appel de réseau téléphonique commuté (RST), consultez la connectivité Voix - Système téléphonique et [RSTN,](cloud-voice-landing-page.md)le [plan](calling-plan-landing-page.md)d’appel qui vous est le plus exact et [Système téléphonique routage direct.](direct-routing-landing-page.md)

- Pour vous assurer que toutes les exigences réseau ont été respectées avant de Teams, voir Préparer le réseau de votre organisation [pour l’Microsoft Teams.](prepare-network.md)

- Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants. Pour [plus d’Skype Entreprise, voir Déplacer du connecteur en ligne vers Teams module PowerShell.](teams-powershell-move-from-sfbo.md)

Après avoir vérifié que votre environnement répond à toutes les conditions préalables applicables, évaluez votre environnement [actuel pour Teams.](upgrade-plan-journey-evaluate-environment.md)