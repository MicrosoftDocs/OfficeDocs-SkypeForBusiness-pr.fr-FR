---
title: Faq sur les changements de données
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
description: Obtenez des réponses aux questions fréquemment posées sur les données Shifts, notamment l’emplacement où les données Shifts sont stockées, la conservation des données, la récupération et le chiffrement.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f7132f79936616ba66565cd133e5ab8616541254
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396855"
---
# <a name="shifts-data-faq"></a>Faq sur les changements de données

Cet article traite des questions fréquemment posées sur les données Shifts, notamment l’emplacement où les données Shifts sont stockées, la conservation des données, la récupération et le chiffrement.

## <a name="where-is-shifts-data-stored"></a>Où sont stockées les données Shifts ?

Les données de décalage sont stockées dans l’une des trois zones géographiques (zones géographiques) : Asie-Pacifique (APAC), Union européenne (UE) ou États-Unis. Chaque géo stocke les données dans au moins deux régions de centre de données Azure pour la haute disponibilité (HA) et la récupération d’urgence (DR). Aujourd’hui, la géo États-Unis/Amérique du Nord utilise des centres de données dans les États-Unis Centre Nord et Centre Sud. Pour plus [d’informations, consultez Où sont stockées les données client Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

Actuellement, Shifts offre la résidence des données en Australie, au Canada, en France, au Japon et au Royaume-Uni. Nous travaillons activement à étendre la prise en charge à d’autres emplacements.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Puis-je choisir l’emplacement de stockage des données Shifts ?

Lorsque vous configurez Teams pour la première fois, vous choisissez un pays ou une région, qui est défini au niveau de l’abonnement. Shifts respecte cette sélection et utilise les paramètres régionaux et la région définis dans Teams si nous prenons en charge cette région. Si nous ne sommes pas encore dans cette région, nous stockons des données dans une région proche que nous prenons en charge. À l’avenir, nous prévoyons de migrer des données existantes, si elles sont stockées dans une région proche, vers la région approvisionnée dans Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Puis-je accéder et exporter ou supprimer les données personnelles d’un utilisateur dans Shifts ?

Shifts est conforme au Règlement général sur la protection des données (RGPD). Une demande formelle d’une personne (connue sous le nom de personne concernée) d’entreprendre une action sur ses données personnelles est appelée demande d’objet de données (DSR). Vous pouvez rechercher et agir sur des données personnelles dans Shifts en réponse à une DSR.

Vous pouvez utiliser l’outil recherche de contenu eDiscovery dans le portail de conformité Microsoft Purview pour rechercher et exporter des données de planification et d’horloge dans Excel. Pour toutes les autres données Shifts, vous pouvez prendre des captures d’écran des données.

Pour en savoir plus, consultez [Office 365 demandes de personnes concernées pour le RGPD et le CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>Qu’advient-il des données Shifts si je désactive shifts pour mon organisation ?

La désactivation de Shifts dans votre organisation *ne supprime pas* les données. Si vous désactivez Shifts, puis que vous activez shifts plus tard, vos données Shifts restent disponibles.

Si vous supprimez votre locataire, toutes les données Shifts sont supprimées après la fin de la période de rétention.

Il n’existe aucune option permettant de supprimer uniquement les données Shifts. Si vous supprimez une équipe dans Teams, les shifts planifient les données associées à cette équipe sont supprimées une fois la période de rétention terminée. Pour en savoir plus, consultez [conservation, suppression et destruction des données dans Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>Puis-je récupérer une planification shifts qui a été supprimée ?

Vous pouvez récupérer une planification supprimée si le groupe Microsoft 365 qui le sauvegarde (ou l’équipe dans Teams) est restauré.

Par défaut, un groupe Microsoft 365 supprimé est conservé pendant 30 jours. Cette période de 30 jours est appelée « suppression réversible », car vous pouvez toujours restaurer le groupe. Pour plus d’informations, consultez [Restaurer un groupe Microsoft 365 supprimé](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Puis-je utiliser des stratégies de rétention personnalisées pour les données Shifts ?

Actuellement, Shifts ne prend pas en charge les stratégies de rétention personnalisées.

Pour en savoir plus sur les stratégies de rétention dans Teams, consultez [En savoir plus sur la rétention pour Teams](/microsoft-365/compliance/retention-policies-teams) et [gérer les stratégies de rétention pour Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>Puis-je récupérer des données Shifts pour un utilisateur dont la licence a été révoquée ?

Aujourd’hui, nous n’offrons pas la possibilité de récupérer des données pour un utilisateur dont la licence a été révoquée. Cette fonctionnalité est un élément vers lequel nous travaillons.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>Quel type de chiffrement Shifts utilise-t-il pour les données au repos et en transit ?

Les données de décalage sont chiffrées au repos par Azure Cosmos DB et Stockage Azure. Pour en savoir plus, consultez [le chiffrement des données Azure au repos](/azure/security/fundamentals/encryption-atrest) et [le chiffrement des données dans Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Shifts suit les instructions de Microsoft 365 pour le chiffrement des données en transit. Pour plus d’informations, consultez [Chiffrement pour les données en transit](/compliance/assurance/assurance-encryption-in-transit).

Le chiffrement des décalages des données au repos et en transit est vérifié chaque année par l’audit de conformité SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Puis-je accéder à des copies immuables des données Shifts ?

Nous ne stockons pas de copies immuables des données Shifts. Par exemple, un responsable peut apporter des modifications à une planification, comme ajouter des notes, modifier les heures de travail, affecter des tâches, etc.

## <a name="can-shifts-data-be-edited"></a>Les données Shifts peuvent-ils être modifiées ?

Certains aspects de Shifts ne peuvent pas être modifiés et certains aspects peuvent être modifiés. Par exemple, les détails de décalage tels que les notes et les couleurs peuvent être modifiés de la même façon que dans l’application Shifts. Les demandes de décalage ne peuvent pas être modifiées, sauf si la demande est retirée.

Pour voir quels champs ont été modifiés, vous pouvez rechercher des événements Shifts dans le journal d’audit Microsoft 365. Pour en savoir plus sur les événements enregistrés pour les activités Shifts dans le journal d’audit Microsoft 365, consultez [Shifts in Teams activities](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Mon organisation utilise un système de gestion de la main-d’œuvre pour la planification. Pouvons-nous intégrer et accéder aux données Shifts ?

Les API Shifts Graph vous permettent d’intégrer des données Shifts à des systèmes externes de gestion de la main-d’œuvre (WFM). Pour plus d’informations, consultez [les API Shifts Graph](/graph/api/resources/shift).

Nous proposons également des connecteurs Shifts managés. Avec ces connecteurs, vous pouvez intégrer votre système WFM directement à Shifts. Pour en savoir plus sur les connecteurs Shifts et les systèmes WFM pris en charge, consultez [Connecteurs Shifts](/microsoft-365/frontline/shifts-connectors).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Les données Shifts peuvent-ils être supprimées définitivement après une période spécifiée ?

Aujourd’hui, nous ne supprimons pas du tout vos données Shifts. À l’aide [des API Shifts Graph](/graph/api/resources/shift), il est possible de [créer une application à l’aide de Power Apps](/powerapps/maker/) pour conserver les données pendant une période spécifiée. Toutefois, nous ne prenons pas en charge cela en mode natif.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>Les données Shifts peuvent-ils être déplacées lors d’une migration de locataire à locataire ?

Les données de décalage peuvent être migrées d’un locataire vers un autre locataire sur une demande spécifique. Gardez à l’esprit que la migration de locataire à locataire n’est pas prise en charge de manière out-of-the-box, mais qu’elle peut être déclenchée en tant que demande du client.

## <a name="related-articles"></a>Articles connexes

- [Shifts pour Teams](../shifts-for-teams-landing-page.md)
- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
