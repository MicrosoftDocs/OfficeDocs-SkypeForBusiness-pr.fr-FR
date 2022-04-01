---
title: Connecteurs Shifts
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez les connecteurs Shifts et comment les utiliser pour connecter Shifts à votre système de gestion du personnel.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592889"
---
# <a name="shifts-connectors"></a>Connecteurs Shifts

## <a name="overview"></a>Vue d’ensemble

Les connecteurs Shifts vous permettent d’intégrer Shifts, l’outil de gestion des plannings de Microsoft Teams, à votre système de gestion du personnel (WFM). Une fois que vous avez établi une connexion, vos employés en contact direct peuvent consulter et gérer leurs plannings en toute transparence dans votre système WFM à partir de Shifts.

La connexion de votre système WFM à Teams à votre personnel de première ligne à gérer les plannings plus efficacement et à rationaliser les processus quotidiens pour un engagement et une productivité supérieurs. Vos employés en contact direct ont un endroit pour la planification, la communication et la collaboration, qui doivent travailler où qu’ils soient, sur n’importe quel appareil.

Nous proposons des connecteurs Shifts gérés et open source. Cet article vous donne une vue d’ensemble des connecteurs Shifts et de leur fonctionnement.

## <a name="how-shifts-connectors-work"></a>Fonctionnement des connecteurs Shifts

Connecteurs de données de planification de synchronisation entre votre système WFM et Shifts, ce qui permet de mettre en place les plannings de votre organisation Teams. Shifts est l’endroit où vos employés en première ligne travaillent pour leurs besoins en planification. Votre système WFM est le système d’enregistrement des règles professionnelles, de la conformité et de l’intelligence.

Le flux de données via le connecteur permet de vérifier que les échéanciers sont toujours à jour. Les plannings dans votre système WFM sont synchronisés avec Shifts. De plus, les modifications apportées aux plannings dans Shifts sont synchronisées avec votre système WFM en temps réel. En tant que système d’enregistrement, toutes les règles métier sont appliquées par votre système WFM avant que les données ne soient enregistrées dans Shifts.

## <a name="managed-shifts-connectors"></a>Connecteurs Shifts gérés

Les connecteurs Shift gérés sont des connecteurs développés en collaboration avec nos partenaires. Les connecteurs gérés sont hébergés et gérés par nous ou par nos partenaires. Avec les connecteurs gérés, une configuration minimale est nécessaire.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams de connexion Shifts pour Blue Yonder
<a name="blue_yonder"> </a>

Le Teams Shifts pour Blue Yonder est une offre tierce hébergée et gérée par Microsoft. Avec ce connecteur, vous pouvez intégrer Shifts avec Blue Yonder Workforce Management (Blue Yonder WFM) versions 2020.3, 2021.1 ou 2021.2 pour gérer vos plannings et les tenir à jour.  

> [!NOTE]
> Si vous avez blue Yonder WFM version 2020.3 ou 2021.1, appliquez le correctif 2020.3.0.4 ou 2021.1.0.3. Ce correctif corrige un problème dans lequel les utilisateurs obtiennent un message d’erreur permanente dans Shifts. Elle résout également un problème qui empêche les utilisateurs de mettre à jour leur disponibilité dans Shifts.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Capture d’écran montrant une demande d’échange dans Shifts sur un appareil mobile, une demande d’approbation dans Teams sur un ordinateur de bureau et un planning dans Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Les responsables en ligne peuvent :

- Publiez des shifts et des plannings dans Blue Yonder WFM et affichez-les dans Shifts.
- Créez, gérez et affectez des shifts ouverts dans Blue Yonder WFM et affichez-les dans Shifts.
- Affectez les shifts ouverts créés dans Blue Yonder WFM dans Shifts.
- Créez, modifiez et supprimez des congés dans Blue Yonder WFM et affichez dans Shifts.
- Affichez et approuvez les demandes de planification des employés dans Blue Yonder WFM et Shifts.
- Définissez et mettez à jour la disponibilité des travailleurs dans Blue Yonder WFM et affichez-les dans Shifts.

Les employés en ligne peuvent :

- Consultez les shifts et plannings des membres de leur équipe et de leur propre équipe dans Shifts.
- Demandez un congé, ouvrez des shifts et échangez des shifts dans Shifts.
- Définissez leur disponibilité dans Shifts.

Les actions suivantes ne sont actuellement pas prises en charge :

- Ajoutez, modifiez, supprimez, enregistrez ou publiez des shifts dans Shifts.
- Ajoutez, modifiez, supprimez, enregistrez ou publiez des congés dans Shifts.
- Ajoutez, modifiez, supprimez, enregistrez ou publiez des shifts ouverts dans Shifts.

Lorsqu’un responsable ou un employé en ligne tente d’faire l’une de ces actions dans Shifts, il reçoit un message pour l’en faire savoir que l’action n’est pas prise en charge.

#### <a name="example-scenario"></a>Exemple de scénario

responsable publie un planning dans Blue Yonder WFM, qui est synchronisé avec Shifts in Teams via le connecteur. Alex, un membre du personnel, reçoit une notification dans Teams sur son appareil mobile, et voit son planning et ses shifts assignés.

Alex doit prendre un congé et demande un jour de congé à l’aide de Shifts. La demande est envoyée à Blue Yonder WFM par le biais du connecteur en temps réel. Blue Yonder WFM garantit la conformité de la demande avec les règles métier et la demande est créée. You sees and approves the request in Blue Yonder WFM, and the approval is synced to Teams. (Il peut également voir et approuver la demande dans Shifts). Alex est averti dans un Teams que sa demande est approuvée et voit son planning mis à jour.

Alex souhaite échanger un shift avec un collègue. Dans Shifts, Alex voit une liste de tous les shifts éligibles à un échange en fonction de règles professionnelles dans Blue Yonder WFM. Alex choisit un shift actuellement affecté à Gena. Gena est averti dans l’Teams sur son appareil mobile et accepte la demande d’échange. You sees and approves the request in Shifts, and the approval is synced to Blue Yonder WFM. (Il peut également voir et approuver la demande dans Blue Yonder WFM). Alex et Gena sont avertis dans les Teams et visualisent leurs plannings mis à jour.

#### <a name="set-up-a-connection"></a>Configurer une connexion

L’intégration de Shifts à Blue Yonder WFM à l’aide du connecteur ne prend que quelques étapes. Vous pouvez utiliser l’Assistant Connecteur Shifts du Centre d'administration Microsoft 365 pour configurer rapidement une connexion. L’Assistant configure le connecteur en fonction des paramètres de votre choix et crée la connexion. Si vous préférez utiliser PowerShell, nous vous fournissons également des scripts PowerShell que vous pouvez utiliser pour vous connecter.

Pour obtenir une aide étape par étape, voir :

- [Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Une fois la connexion définie, vous pouvez utiliser PowerShell pour mettre à jour et modifier les paramètres de connexion à tout moment, selon vos besoins. Concernant le connecteur lui-même, vous n’avez pas à vous soucier des mises à niveau ou de la maintenance. Nous nous occupeons de cela.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connecteur Reflexis Shifts pour Microsoft Teams

Le connecteur Reflexis Shifts pour l Microsoft Teams est hébergé et géré par Le bleu. Avec ce connecteur, vous pouvez intégrer shifts au système Reflexis WFM pour gérer vos plannings et les tenir à jour.

Les employés en ligne ont accès à leur planning dans Shifts in Teams, et leurs demandes sont synchronisées de Shifts à Reflexis Workforce Scheduler (RWS). L’état des demandes et shifts créés dans RWS est synchronisé avec Shifts in Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Capture d’écran montrant la liste des shifts sur un appareil mobile et un planning dans Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Les responsables en ligne peuvent :

- Publiez des shifts et des plannings dans les Reflexis et affichez-les dans Shifts.
- Modifiez des shifts dans Les Réflexes et les Shifts.
- Créez, gérez et affectez des shifts ouverts à la fois dans Reflexis et Shifts.
- Affichez et approuvez les demandes de planification des employés dans Les Réflexes et Shifts.

Les employés en ligne peuvent :

- Consultez les shifts et plannings des membres de leur équipe et de leur propre équipe dans Shifts.
- Demandez un congé, ouvrez des shifts, échangez et proposez des shifts dans Shifts.

Pour en savoir plus, voir https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Connecteurs Shifts open source

Les connecteurs Shifts open source sont des intégrations communautaires [conçues sur shifts Graph API](/graph/api/resources/shift). Les connecteurs open source suivants sont disponibles :

- Kronos-to-Teams WFC local
- Connecteur Shifts JDA-Teams (pour blue Yonder version 2017 à 2020.2)

Chaque connecteur est livré avec des instructions détaillées de déploiement et de configuration. Ils incluent des scripts de déploiement d Resource Manager Azure (ARM) qui vous permettent d’héberger tous les services nécessaires dans Microsoft Azure. Le code source et les scripts de déploiement peuvent être téléchargés dans [un GitHub référentiel.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) Vous pouvez déployer tel que vous le souhaitez, ou le personnaliser ou l’étendre en respectant vos besoins.

Pour en savoir plus, [consultez les connecteurs Shifts prêts pour la production](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
