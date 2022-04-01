---
title: Shifts pour Teams
description: Obtenez les conseils d’administration dont vous avez besoin pour configurer et gérer Shifts, l’outil de gestion des plannings, Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592770"
---
# <a name="shifts-for-teams"></a>Shifts pour Teams

Shifts, l’outil de gestion des Teams, maintient en contact et en synchronisation votre personnel en avant-plan. Il est conçu avant tout pour une gestion de calendrier et des communications efficaces et rapides. Avec Shifts, les responsables et employés en contact peuvent gérer facilement les plannings et rester en contact.

Les responsables peuvent créer, mettre à jour et gérer les plannings des shifts de leurs équipes. Ils peuvent attribuer des shifts, ajouter des shifts ouverts et approuver les demandes de planification des employés. Les employés peuvent afficher les plannings de leur équipe et de leur propre, définir leur disponibilité, demander à échanger ou proposer un shift, demander un congé et pointer vers l’avant et vers l’arrière.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Utilisez les ressources suivantes pour configurer et gérer Shifts dans votre organisation.

## <a name="set-up-and-manage-shifts"></a>Configurer et gérer Shifts

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Gérer les shifts](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Découvrez comment gérer Shifts pour votre organisation.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Gérer les propriétaires de planning pour la gestion des shifts](shifts/schedule-owner-for-shift-management.md)** Cette fonctionnalité vous permet d’améliorer les autorisations d’un membre de l’équipe en tant que propriétaire de planning sans donner à l’employé le niveau de propriétaire de l’équipe.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[FAQ shifts de données](shifts/shifts-data-faq.md)** Découvrez où sont stockées les données Shifts et d’autres rubriques liées aux données Shifts, notamment la rétention, l’extraction et le chiffrement.        |

## <a name="shifts-connectors"></a>Connecteurs Shifts

Si vous utilisez un système tiers de gestion du personnel (WFM) pour la planification, vous pouvez l’intégrer directement à Shifts via les connecteurs Shifts gérés, et via shifts Graph API et SDK avec des connecteurs Shifts open source. Une fois que vous avez établi une connexion, vos employés en contact direct peuvent consulter et gérer leurs plannings en toute transparence dans votre système WFM à partir de Shifts.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Vue d’ensemble des connecteurs Shifts](shifts/shifts-connectors.md)** Obtenez une vue d’ensemble des connecteurs Shifts et de leur fonctionnement. En savoir plus sur les connecteurs gérés et open source disponibles et les systèmes WFM pris en charge.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Connecteurs Shifts gérés](shifts/shifts-connectors.md#managed-shifts-connectors)** Les connecteurs Shifts gérés, développés en collaboration avec nos partenaires, sont hébergés et gérés par nous ou par nos partenaires. Pour en savoir plus, voir [Microsoft Teams connecteur Shifts bleu Yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) et [Reflexis Shifts pour Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management](shifts/shifts-connector-wizard.md)** L’Assistant Connecteur Shifts du Centre d'administration Microsoft 365 vous aide à configurer rapidement une connexion à votre système WFM. Actuellement, l’Assistant prend en charge le Teams Shifts bleu Yonder pour intégrer Shifts à Blue Yonder Workforce Management.
|  | **[Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Découvrez comment utiliser PowerShell pour configurer une connexion à Blue Yonder Workforce Management via le connecteur Teams Shifts de Blue Yonder.         |
|   | **[Utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management](shifts/shifts-connector-powershell-manage.md)** Obtenez des instructions sur l’utilisation de PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management après l’avoir installé via l’Assistant Connecteur Shifts ou PowerShell.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Connecteurs Shifts open source](/microsoftteams/platform/samples/shifts-wfm-connectors)** Découvrez comment utiliser des [connecteurs open source pilotés](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) par la communauté pour intégrer votre système Kronos ou JDA WFM via Shifts Graph API et SDK.    |

## <a name="shifts-extensions"></a>Extensions Shifts

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Shifts Graph API vous permettent d’intégrer des données Shifts aux systèmes WFM (External Workforce Management). Vous avez la possibilité de créer des expériences Shifts personnalisées à l’arrière-plan, tout en offrant aux utilisateurs une expérience frontale enrichie en Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate vous permet de prendre des informations à partir de Shifts, de créer des flux de travail personnalisés avec d’autres applications et d’effectuer des opérations à l’échelle. Automatisez les processus clés avec peu ou pas de code. Les déclencheurs et modèles supportent différents scénarios tels que l’activation des approbations automatiques pour les demandes de shift lorsque l’approbation d’un responsable n’est pas nécessaire. |

## <a name="featured-training"></a>Formation proposée

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Vidéo : Qu’est-ce que Shifts ?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Vidéo : Créer un planning shifts](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Vidéo : Gérer un planning Shifts](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
