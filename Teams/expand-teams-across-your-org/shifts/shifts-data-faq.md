---
title: FAQ shifts de données
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenez des réponses aux questions les plus fréquemment posées sur les données Shifts, notamment l’endroit où sont stockées les données Shifts, la rétention des données, l’extraction et le chiffrement.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3f26413aa746b37474e7035e313fc8ffff2fb93c
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039952"
---
# <a name="shifts-data-faq"></a>FAQ shifts de données

Cet article traite des questions fréquemment posées sur les données Shifts, notamment l’endroit où sont stockées les données Shifts, la rétention des données, l’extraction et le chiffrement.

## <a name="where-is-shifts-data-stored"></a>Où sont stockées les données Shifts ?

Les données shifts sont stockées dans l’une des trois zones géographiques (géographiques) : Asie-Pacifique (APAC), Union européenne (UE) ou États-Unis. Chaque geo stocke des données dans au moins deux régions de centre de données Azure pour les zones Haute disponibilité (HA) et DR (Disaster Recovery). Aujourd’hui, les états-Unis et l’Amérique du Nord utilisent des centres de données dans les centres de données central du Nord et du centre sud des États-Unis. Pour en savoir plus, [consultez où se trouve Microsoft 365 données client stockées](/microsoft-365/enterprise/o365-data-locations).

Actuellement, Shifts offre une résidence de données en Australie, au Canada, en France, au Japon et au Royaume-Uni. Nous travaillons activement au développement de la prise en charge vers d’autres emplacements.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Puis-je choisir l’endroit où sont stockées les données Shifts ?

La première fois que vous Teams d’abonnement, vous choisissez un pays ou une région, qui est définie au niveau de l’abonnement. Shifts honore cette sélection et utilise les paramètres régionaux et régionaux Teams si nous  appuyons cette région. Si nous ne sommes pas encore dans cette région, nous stockons des données dans une région proche que nous  prise en charge. À l’avenir, nous prévoyons de migrer des données existantes, si elles sont stockées dans une région proche, vers la région qui est mise en service dans Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Puis-je accéder aux données personnelles d’un utilisateur et les exporter ou les supprimer dans Shifts ?

Shifts est conforme au Règlement général sur la protection des données (R GDPR).Une demande formelle par une personne (appelée sujet de données) pour agir sur ses données personnelles est appelée demande d’accès à la personne qui en est la personne. Vous pouvez rechercher des données personnelles et agir dans Shifts en réponse à une demande de réponse.

Vous pouvez utiliser l’outil eDiscovery de recherche de contenu dans le Centre de conformité Microsoft 365 pour rechercher et exporter des données de calendrier et d’horloge dans Excel. Pour toutes les autres données Shifts, vous pouvez prendre des captures d’écran des données.

Pour plus d’informations, [voir Office 365 des sujets de données pour le R GDPR et le CENTRE DNS](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Qu’advient-il des données shifts si je les désactiver pour mon organisation ?

La suppression des shifts dans votre *organisation n’a pas pour effet de* supprimer des données. Si vous la désactiverez, puis l’activer par la suite, vos données Shifts seront toujours disponibles.

Si vous supprimez votre client, toutes les données shifts sont supprimées à l’issue de la période de rétention.

Aucune option ne permet de supprimer uniquement les données de Shifts. Si vous supprimez une équipe dans Teams, Shifts programme les données associées à cette équipe sont supprimées à l’issue de la période de rétention. Pour en savoir plus, consultez [la conservation, la suppression et la destruction des données dans Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Puis-je récupérer un planning Shifts qui a été supprimé ?

Vous pouvez récupérer un planning supprimé si le groupe Microsoft 365 le backs (ou l’équipe dans Teams) est restauré.

Par défaut, un groupe de Microsoft 365 supprimé est conservé pendant 30 jours. Cette période de 30 jours est appelée « suppression soft », car vous pouvez toujours restaurer le groupe. Pour en savoir plus, voir [Restaurer une Microsoft 365 groupe](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Puis-je utiliser des stratégies de rétention personnalisées pour les données Shifts ?

Actuellement, Shifts ne prend pas en charge les stratégies de rétention personnalisées.

Pour en savoir plus sur les stratégies de rétention dans Teams, voir Rétention pour les [Teams et Gérer](/microsoft-365/compliance/retention-policies-teams) les stratégies de rétention [pour Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Puis-je récupérer les données Shifts d’un utilisateur dont la licence a été révoquée ?

Aujourd’hui, nous ne proposons pas la possibilité de récupérer les données d’un utilisateur dont la licence a été révoquée. Nous travaillons actuellement sur cette fonctionnalité.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Quel type de chiffrement Shifts utilise-t-il pour les données au repos et en transit ?

Les données Shifts sont chiffrées au repos par Azure Cosmos DB et Azure Stockage. Pour en savoir plus, consultez [le chiffrement de données Azure au repos](/azure/security/fundamentals/encryption-atrest) et le chiffrement de données dans [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Shifts suit les Microsoft 365 en matière de chiffrement des données en transit. Pour plus d’informations, [voir Chiffrement des données en transit](/compliance/assurance/assurance-encryption-in-transit).

Le chiffrement des shifts des données au repos et en transit est vérifié chaque année par l’audit de conformité SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Puis-je accéder à des copies immutables des données Shifts ?

Nous ne stockons pas de copies immutables des données Shifts. Par exemple, un responsable peut apporter des modifications à un planning, comme ajouter des notes, modifier des horaires de travail, attribuer des tâches, etc.

## <a name="can-shifts-data-be-edited"></a>Les données Shifts peuvent-elles être modifiées ?

Certains aspects des shifts ne peuvent pas être modifiés et d’autres peuvent être modifiés. Par exemple, vous pouvez modifier les détails du shift tels que les notes et les couleurs de la même façon que dans l’application Shifts. Les demandes de shift ne peuvent pas être modifiées, sauf si elles sont retirées.

Pour savoir quels champs ont été modifiés, vous pouvez rechercher des événements Shifts dans le Microsoft 365 d’audit. Pour en savoir plus sur les événements enregistrés pour les activités Shifts dans le journal d’audit Microsoft 365, voir [Shifts in Teams activités](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Mon organisation utilise un système de gestion du personnel pour la planification. Pouvons-nous nous intégrer aux données Shifts et y accéder ?

Shifts Graph API vous permet d’intégrer des données Shifts aux systèmes de gestion du personnel externe (WFM). Pour en savoir plus, [voir Shifts Graph API](/graph/api/resources/shift).

Nous proposons également des connecteurs Shifts gérés et des connecteurs Shifts open source. Ces connecteurs vous permet d’intégrer votre système WFM directement avec Shifts. Pour en savoir plus sur les connecteurs Shifts et les systèmes WFM pris en charge, voir [Les connecteurs Shifts](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Les données Shifts peuvent-elles être supprimées définitivement après une période spécifiée ?

Aujourd’hui, nous ne supprimons pas du tout vos shifts. En [utilisant Shifts Graph API](/graph/api/resources/shift), il est possible de créer une application à [](/powerapps/maker/) l’aide d’Power Apps pour conserver les données pendant une période spécifiée. Cela n’est toutefois pas prise en charge en natif.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Les données Shifts peuvent-elles être déplacées dans une migration client-client ?

Les données shifts peuvent être migrées d’un client vers un autre client sur demande spécifique. N’oubliez pas que la migration client à client n’est pas prise en charge, mais peut être élevée en tant que demande client.

## <a name="related-articles"></a>Articles connexes

- [Shifts pour Teams](../shifts-for-teams-landing-page.md)
- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
