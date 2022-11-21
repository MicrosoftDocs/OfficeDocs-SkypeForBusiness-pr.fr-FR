---
title: FAQ sur les données shifts
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenez des réponses aux questions fréquemment posées sur les données Shifts, notamment sur l’emplacement de stockage des données Shifts, la conservation, la récupération et le chiffrement des données.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 39dcbc391096db8edce7dee90abe6ee26e24f027
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131023"
---
# <a name="shifts-data-faq"></a>FAQ sur les données shifts

Cet article traite des questions fréquemment posées sur les données Shifts, notamment l’emplacement où les données Shifts sont stockées, la conservation des données, la récupération et le chiffrement.

## <a name="where-is-shifts-data-stored"></a>Où sont stockées les données Shifts ?

Les données shifts sont stockées dans l’une des trois zones géographiques (zones géographiques) : Asie-Pacifique (APAC), Union européenne (UE) ou États-Unis. Chaque géo stocke des données dans au moins deux régions de centre de données Azure pour la haute disponibilité (HA) et la récupération d’urgence (DR). Aujourd’hui, la zone géographique États-Unis/Amérique du Nord utilise des centres de données dans les États-Unis Centre Nord et Centre Sud. Pour plus [d’informations, consultez Où sont stockées les données client Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

Actuellement, Shifts offre la résidence des données en Australie, au Canada, en France, au Japon et au Royaume-Uni. Nous travaillons activement à étendre la prise en charge à d’autres emplacements.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Puis-je choisir l’emplacement de stockage des données Shifts ?

Lorsque vous configurez Teams pour la première fois, vous choisissez un pays ou une région, qui est défini au niveau de l’abonnement. Shifts respecte cette sélection et utilise les paramètres régionaux et la région définis dans Teams si nous prenons en charge cette région. Si nous ne sommes pas encore dans cette région, nous stockons les données dans une région proche que nous prenons en charge. À l’avenir, nous prévoyons de migrer les données existantes, si elles sont stockées dans une région proche, vers la région approvisionnée dans Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Puis-je accéder aux données personnelles d’un utilisateur et les exporter ou les supprimer dans Shifts ?

Shifts est conforme au Règlement général sur la protection des données (RGPD). Une demande formelle d’une personne (connue sous le nom de personne concernée) pour effectuer une action sur ses données personnelles est appelée demande de personne concernée (DSR). Vous pouvez rechercher et agir sur des données personnelles dans Shifts en réponse à une DSR.

Vous pouvez utiliser l’outil eDiscovery de recherche de contenu dans le portail de conformité Microsoft Purview pour rechercher et exporter des données de planification et d’horloge dans Excel. Pour toutes les autres données Shifts, vous pouvez prendre des captures d’écran des données.

Pour en savoir plus, consultez [Office 365 demandes des personnes concernées pour le RGPD et le CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Qu’advient-il des données Shifts si je désactive Shifts pour mon organisation ?

La désactivation de Shifts dans votre organisation *ne supprime pas* les données. Si vous désactivez Shifts, puis activez Majs ultérieurement, vos données Shifts sont toujours disponibles.

Si vous supprimez votre locataire, toutes les données Shifts sont supprimées une fois la période de rétention terminée.

Il n’existe aucune option pour supprimer uniquement les données Shifts. Si vous supprimez une équipe dans Teams, les données de planification Shifts associées à cette équipe sont supprimées après la fin de la période de rétention. Pour plus d’informations, consultez [Conservation, suppression et destruction des données dans Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Puis-je récupérer une planification Shifts qui a été supprimée ?

Vous pouvez récupérer une planification supprimée si le groupe Microsoft 365 qui la prend en charge (ou l’équipe dans Teams) est restauré.

Par défaut, un groupe Microsoft 365 supprimé est conservé pendant 30 jours. Cette période de 30 jours est appelée « suppression réversible », car vous pouvez toujours restaurer le groupe. Pour en savoir plus, consultez [Restaurer un groupe Microsoft 365 supprimé](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Puis-je utiliser des stratégies de rétention personnalisées pour les données Shifts ?

Actuellement, Shifts ne prend pas en charge les stratégies de rétention personnalisées.

Pour en savoir plus sur les stratégies de rétention dans Teams, consultez [En savoir plus sur la rétention pour Teams](/microsoft-365/compliance/retention-policies-teams) et [Gérer les stratégies de rétention pour Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Puis-je récupérer des données Shifts pour un utilisateur dont la licence a été révoquée ?

Aujourd’hui, nous n’offrons pas la possibilité de récupérer des données pour un utilisateur dont la licence a été révoquée. Nous travaillons à cette fonctionnalité.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Quel type de chiffrement Shifts utilise-t-il pour les données au repos et en transit ?

Les données shifts sont chiffrées au repos par Azure Cosmos DB et Stockage Azure. Pour plus d’informations, consultez [Chiffrement des données Azure au repos](/azure/security/fundamentals/encryption-atrest) et [Chiffrement des données dans Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Shifts suit les instructions de Microsoft 365 pour le chiffrement des données en transit. Pour plus d’informations, consultez [Chiffrement des données en transit](/compliance/assurance/assurance-encryption-in-transit).

Le chiffrement des shifts des données au repos et en transit est vérifié chaque année par l’audit de conformité SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Puis-je accéder à des copies immuables des données Shifts ?

Nous ne stockons pas de copies immuables des données Shifts. Par exemple, un responsable peut apporter des modifications à une planification, telles que l’ajout de notes, la modification des heures de travail, l’attribution de tâches, etc.

## <a name="can-shifts-data-be-edited"></a>Les données Shifts peuvent-elles être modifiées ?

Certains aspects de Shifts ne peuvent pas être modifiés et certains aspects peuvent être modifiés. Par exemple, les détails des décalages tels que les notes et les couleurs peuvent être modifiés de la même façon que dans l’application Shifts. Les demandes de décalage ne peuvent pas être modifiées, sauf si la demande est retirée.

Pour voir quels champs ont été modifiés, vous pouvez rechercher des événements Shifts dans le journal d’audit Microsoft 365. Pour en savoir plus sur les événements enregistrés pour les activités Shifts dans le journal d’audit Microsoft 365, voir [Shifts in Teams activities](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Mon organisation utilise un système de gestion de la main-d’œuvre pour la planification. Pouvons-nous intégrer aux données Shifts et y accéder ?

Les API Shifts Graph vous permettent d’intégrer des données Shifts à des systèmes de gestion des employés externes (WFM). Pour plus d’informations, consultez [API Shifts Graph](/graph/api/resources/shift).

Nous proposons également des connecteurs Shifts managés. Avec ces connecteurs, vous pouvez intégrer votre système WFM directement à Shifts. Pour en savoir plus sur les connecteurs Shifts et les systèmes WFM pris en charge, consultez [Connecteurs Shifts](/microsoft-365/frontline/shifts-connectors).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Les données Shifts peuvent-elles être supprimées définitivement après une période spécifiée ?

Aujourd’hui, nous ne supprimons pas vos données Shifts. À l’aide [des API Shifts Graph](/graph/api/resources/shift), il est possible de [créer une application à l’aide de Power Apps](/powerapps/maker/) pour conserver les données pendant une période spécifiée. Toutefois, nous ne prenons pas en charge cette option en mode natif.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Les données Shifts peuvent-elles être déplacées dans une migration de locataire à locataire ?

Pour migrer vos données Shifts existantes vers un autre locataire, vous devez exporter les planifications Shifts pour une plage de dates, modifier les noms d’utilisateur (si nécessaire), puis importer les planifications dans le locataire de destination. Vous pouvez exporter jusqu’à 100 jours de données Shifts à la fois. La plage de dates peut être passée ou future. Si vous avez besoin d’exporter des données pour une période plus longue que 100 jours, répétez le processus.

Avant de migrer vos données Shifts, vérifiez que les conditions suivantes sont remplies :

- Le domaine du locataire de destination, les équipes et les membres de l’équipe doivent déjà exister. La migration ne crée pas d’équipes ni ne modifie l’appartenance ou la propriété d’une équipe.
- L’application Shifts doit être configurée dans teams dans le locataire de destination et avoir une planification vide. Gardez à l’esprit que la migration ne remplace pas ou ne supprime pas les données existantes. Cela signifie que si une équipe a une planification existante, les utilisateurs peuvent voir des équipes en double ou en conflit, qui doivent être résolues manuellement.
- Les demandes ouvertes (telles que les demandes d’échange et de congé) qui sont en attente d’approbation ne sont pas migrées. Nous vous recommandons de fermer toutes les demandes ouvertes avant de commencer la migration des données.

Voici une vue d’ensemble des étapes de migration de vos données Shifts vers un autre locataire.

1. Dans le locataire source, pour chaque équipe, exportez la planification Shifts :
    1. Dans Shifts, dans la page **Planification**, accédez à **Plus d’options (...)** >  **Planification de l’exportation**.
    1. Sélectionnez une plage de dates.
    1. Activez **l’option Exporter dans un format qui peut être importé**, puis sélectionnez **Exporter**. Les données de planification shifts sont exportées vers un fichier Excel.
1. Dans le cadre de la migration, si des membres de l’équipe changent de domaine de messagerie, mettez à jour manuellement le fichier Excel pour remplacer le nom d’utilisateur principal (UPN) de ces utilisateurs par le domaine du locataire de destination.
1. Dans le locataire de destination, importez la planification dans chaque équipe.
    1. Dans Shifts, dans la page **Planification**, accédez à **Plus d’options (...)** >  **Importer la planification**.
    1. Sélectionnez **Charger un fichier**, accédez au fichier Excel de cette équipe, puis sélectionnez **Ouvrir**.

Pour plus d’informations, consultez [Le modèle Excel pour Shifts](https://support.microsoft.com/office/the-excel-template-for-shifts-6fc6a206-e7cc-4907-87b8-a296bae84ce3).

## <a name="related-articles"></a>Articles connexes

- [Shifts pour Teams](../shifts-for-teams-landing-page.md)
- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
