---
title: Configurer le tableau de bord de qualité des appels
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Découvrez comment activer et utiliser le tableau de bord de qualité des appels et obtenir des rapports récapitulatifs sur la qualité des appels.
ms.openlocfilehash: 5a220ac01965623417354df35a9052648652f607
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60081613"
---
# <a name="set-up-call-quality-dashboard"></a>Configurer le tableau de bord de qualité des appels

Ouvrez le tableau de bord de qualité des appels microsoft (CQD) à l’adresse [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (connectez-vous avec vos informations d’identification d’administrateur). Ou bien, dans le centre Teams d’administration, sélectionnez **Analyse et**& de qualité des appels des  >  **rapports.**

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::

Dans la page qui s’ouvre, cliquez sur Se **connectez** et entrez les informations de votre compte d’Microsoft Teams administrateur général. Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données. N’oubliez pas que le traitement d’un nombre suffisant de données peut prendre une ou plusieurs heures pour afficher des résultats significatifs dans les rapports.

Le CQD affiche la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019. 

> [!IMPORTANT]
> Pour utiliser le CQD Skype Entreprise Server 2019, vous devez [configurer Call Data Connector.](/skypeforbusiness/hybrid/configure-call-data-connector) Voir [Planifier le connecteur de données d’appel](/skypeforbusiness/hybrid/plan-call-data-connector) avant de commencer.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Attribuer des rôles d’administrateur pour l’accès au CQD

Attribuez [des](/microsoft-365/admin/add-users/about-admin-roles) rôles pour accéder au DQD aux personnes qui doivent l’utiliser.

Si vous souhaitez que les utilisateurs non administrateurs (par exemple, des ingénieurs du support technique et des agents du support technique) utilisent le tableau de bord de qualité des appels, vous pouvez leur attribuer un des rôles suivants, ce qui donne accès au tableau de bord de qualité des appels. 


|&nbsp;  |Afficher les rapports  |Afficher les champs EUII  |Créer des rapports  |Télécharger de création de données  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général     |Oui         |Oui         |Oui         |Oui         |
|Administrateur Teams     |Oui         |Oui         |Oui         |Oui         |
|Administrateur des communications Teams     |Oui         |Oui         |Oui         |Oui         |
|Ingénieur du support technique pour les communications Teams     |Oui         |Oui         |Oui         |Non         |
|Teams Spécialiste du support pour les communications     |Oui         |Non         |Oui         |Non         |
|Skype Entreprise Administrateur     |Oui         |Oui         |Oui         |Oui         |
|Lecteur global |Oui         |Oui         |Oui         |Non         |
|Lecteur de<sup>rapports 1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> En plus de lire les rapports du CQD, le Lecteur de rapports peut afficher tous les rapports d’activité du Centre d’administration et tous les rapports du pack de contenu [Adoption Microsoft 365'équipe.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)

> [!NOTE]
> Si [l’EUII (informations d’identification](CQD-data-and-reports.md#euii-data) des utilisateurs finux) n’est pas identifiée et que vous avez un des rôles autorisés à consulter ces informations, n’oubliez pas que le DQD conserve la fonction EUII uniquement pendant 28 jours. Tous les éléments de plus de 28 jours sont supprimés.

Pour plus d’informations sur ces rôles, voir À propos [Office 365 rôles d’administrateur.](/office365/admin/add-users/about-admin-roles)


Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données du CQD

Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.

Lisez Utiliser Power BI pour analyser les données [du CQD](CQD-Power-BI-query-templates.md) et en savoir plus.

## <a name="related-topics"></a>Sujets associés

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Télécharger données client et bâtiment](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le DQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)
