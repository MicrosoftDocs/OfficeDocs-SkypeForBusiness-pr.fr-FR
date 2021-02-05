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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Découvrez comment activer et utiliser le tableau de bord de qualité des appels et obtenir des rapports récapitulatifs sur la qualité des appels.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112837"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurer le tableau de bord de qualité des appels

Ouvrez le tableau de bord de qualité des appels microsoft (CQD) à l’adresse [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (connectez-vous avec vos informations d’identification d’administrateur). Vous pouvez également aller au Centre d’administration Teams et sélectionner **Tableau de bord de qualité des appels.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels dans le Centre d’administration Teams":::

Dans la page qui s’ouvre, cliquez sur Se **connectez** et entrez les informations de votre compte d’administrateur général ou d’administrateur de services Microsoft Teams. Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données. N’oubliez pas que le traitement d’un nombre suffisant de données peut prendre une ou plusieurs heures afin d’afficher des résultats significatifs dans les rapports.

Le CQD indique la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019. 

> [!IMPORTANT]
> Pour utiliser le CQD avec Skype Entreprise Server 2019, vous devez [configurer call Data Connector.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector) Voir [Planifier le connecteur de données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) avant de commencer.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Attribuer des rôles d’administrateur pour l’accès au CQD

Attribuez [des](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) rôles pour accéder au DQD aux personnes qui doivent l’utiliser.

Si vous souhaitez que les utilisateurs non administrateurs (par exemple, des ingénieurs du support technique et des agents du support technique) utilisent le tableau de bord de qualité des appels, vous pouvez leur attribuer un des rôles suivants, ce qui donne accès au tableau de bord de qualité des appels. 


|  |Afficher des rapports  |Afficher les champs EUII  |Créer des rapports  |Télécharger des données bâtiment  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général     |Oui         |Oui         |Oui         |Oui         |
|Administrateur du service Teams     |Oui         |Oui         |Oui         |Oui         |
|Administrateur des communications Teams     |Oui         |Oui         |Oui         |Oui         |
|Ingénieur du support technique pour les communications Teams     |Oui         |Oui         |Oui         |Non         |
|Spécialiste du support pour les communications dans Teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype Entreprise     |Oui         |Oui         |Oui         |Oui         |
|Lecteur global |Oui         |Oui         |Oui         |Non         |
|Lecteur de<sup>rapports 1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> En plus de lire les rapports du CQD, le Lecteur de rapports peut afficher tous les rapports d’activité dans le Centre d’administration et tous les rapports du pack de contenu Adoption de [Microsoft 365.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)

> [!NOTE]
> Si la fonction [EUII (identification](CQD-data-and-reports.md#euii-data) de l’utilisateur final) n’est pas disponibles et que vous avez l’un des rôles autorisés à consulter ces informations, n’oubliez pas que le DQD conserve la fonction EUII uniquement pendant 28 jours. Tous les éléments de plus de 28 jours sont supprimés.

Pour plus d’informations sur ces rôles, voir À propos des rôles d’administrateur [Office 365.](/office365/admin/add-users/about-admin-roles)


Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données. Depuis décembre 2019, vous pouvez toujours accéder à l’ancienne version du CQD (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier CQD (cqd.teams.microsoft.com). Finalement, l’ancienne version du CQD sera désaffectée. À compter du 1er juillet 2020, l’ancienne version du CQD accède aux données du dernier DQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrer des données de création et des rapports à partir d’une version précédente du CQD

> [!IMPORTANT]
> À compter du 1er juillet 2020, vous ne pourrez plus migrer de données et de rapports à partir de l’ancien CQD https://CQD.lync.com) (. 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données du CQD

Nouveautés de Janvier 2020 : Téléchargez les modèles de requête [Power BI pour CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler les données de votre CQD.

Lisez [Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md) et en savoir plus.


## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Charger des données client et bâtiment](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le CQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)
