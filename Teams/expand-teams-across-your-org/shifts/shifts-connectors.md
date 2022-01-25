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
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192479"
---
# <a name="shifts-connectors"></a>Connecteurs Shifts

## <a name="overview"></a>Présentation

Les connecteurs Shifts vous permettent d’intégrer Shifts, l’outil de gestion des plannings de Microsoft Teams, à votre système de gestion du personnel (WFM). Une fois que vous avez établi une connexion, vos employés en contact direct peuvent consulter et gérer leurs plannings en toute transparence dans votre système WFM à partir de Shifts.

La connexion de votre système WFM à Teams à votre personnel de première ligne à gérer les plannings plus efficacement et à rationaliser les processus quotidiens pour un engagement et une productivité supérieurs. Vos employés en contact direct ont un endroit pour la planification, la communication et la collaboration, qui doivent travailler où qu’ils soient, sur n’importe quel appareil.

Nous proposons des connecteurs Shifts gérés et open source. Cet article vous donne une vue d’ensemble des connecteurs Shifts et de leur fonctionnement.

## <a name="how-shifts-connectors-work"></a>Fonctionnement des connecteurs Shifts

Connecteurs de synchronisation des données de planification entre votre système WFM et Shifts, ce qui permet de mettre en place les plannings de votre organisation Teams. Shifts est l’endroit où vos employés en première ligne travaillent pour leurs besoins en planification. Votre système WFM est le système d’enregistrement des règles professionnelles, de la conformité et de l’intelligence.

Le flux de données via le connecteur permet de vérifier que les échéanciers sont toujours à jour. Les plannings dans votre système WFM sont synchronisés avec Shifts. De plus, les modifications apportées aux plannings dans Shifts sont synchronisées avec votre système WFM en temps réel. En tant que système d’enregistrement, toutes les règles métier sont appliquées par votre système WFM avant que les données ne soient enregistrées dans Shifts.

## <a name="managed-shifts-connectors"></a>Connecteurs Shifts gérés

Les connecteurs Shift gérés sont des connecteurs développés en collaboration avec nos partenaires. Les connecteurs gérés sont hébergés et gérés par nous ou par nos partenaires. Avec les connecteurs gérés, une configuration minimale est nécessaire.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connecteur Reflexis Shifts pour Microsoft Teams

Le connecteur Reflexis Shifts pour l Microsoft Teams est hébergé et géré par Le bleu. Avec ce connecteur, vous pouvez intégrer shifts au système Reflexis WFM pour gérer vos plannings et les tenir à jour.

Les employés en ligne ont accès à leur planning dans Shifts in Teams, et leurs demandes sont synchronisées de Shifts à Reflexis Workforce Scheduler (RWS). L’état des demandes et shifts créés dans RWS est synchronisé avec Shifts dans Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Capture d’écran montrant la liste des shifts sur un appareil mobile et un planning dans Les Réflexes" lightbox="../../media/shifts-connector-reflexis.png":::

Les responsables en ligne peuvent :

- Publiez des shifts et des plannings dans les Reflexis et affichez-les dans Shifts.
- Modifiez des shifts dans Les Réflexes et les Shifts.
- Créez, gérez et affectez des shifts ouverts à la fois dans Reflexis et Shifts.
- Affichez et approuvez les demandes de planification des employés dans Les Réflexes et Shifts.

Les employés en ligne peuvent :

- Consultez les shifts et plannings des membres de leur équipe et de leur propre équipe dans Shifts.
- Demandez un congé, ouvrez des shifts, échangez et proposez des shifts dans Shifts.

Pour en savoir plus, voir https://connect.zebra.com/microsoft-connectors .

## <a name="open-source-shifts-connectors"></a>Connecteurs Shifts open source

Les connecteurs Shifts open source sont des intégrations communautaires conçues sur [Shifts Graph API.](/graph/api/resources/shift) Les connecteurs open source suivants sont disponibles :

- Kronos-to-Teams WFC local
- Connecteur Shifts JDA-Teams (pour blue Yonder version 2017 à 2020.2)

Chaque connecteur est livré avec des instructions détaillées de déploiement et de configuration. Ils incluent des scripts de déploiement du Gestionnaire de ressources Azure (ARM) qui vous permettent d’héberger tous les services nécessaires dans Microsoft Azure. Le code source et les scripts de déploiement peuvent être téléchargés dans [GitHub référentiel.](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) Vous pouvez déployer tel que vous le souhaitez, ou le personnaliser ou l’étendre en respectant vos besoins.

Pour en savoir plus, [consultez les connecteurs Shifts](/microsoftteams/platform/samples/shifts-wfm-connectors)prêts pour la production.

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
