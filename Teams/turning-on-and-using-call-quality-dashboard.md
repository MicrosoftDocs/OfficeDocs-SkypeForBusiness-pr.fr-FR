---
title: Configurer le tableau de bord de qualité des appels (bord)
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
description: Apprenez-en davantage sur l’activation et l’utilisation du tableau de bord de qualité des appels et obtenez des rapports de synthèse sur la qualité des appels.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918649"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurer le tableau de bord de qualité des appels (bord)

Ouvrez le tableau de bord de qualité des appels bord ( [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Connectez-vous à l’aide de vos informations d’identification d’administrateur). Ou accédez au centre d’administration teams et sélectionnez **tableau de bord de qualité des appels**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

Dans la page qui s’ouvre, cliquez sur **se connecter** , puis entrez les informations de votre compte d’administrateur général ou du compte d’administrateur de service Microsoft Teams. Lorsque vous vous connectez pour la première fois, bord commence à collecter et à traiter les données. Gardez à l’esprit qu’il est possible que l’affichage des résultats pertinents dans les rapports puisse prendre une ou plusieurs heures.

BORD indique la qualité des appels et des réunions à un niveau de l’organisation, pour Microsoft Teams, Skype entreprise Online et Skype entreprise Server 2019. 

> [!IMPORTANT]
> Pour utiliser bord avec Skype entreprise Server 2019, vous devez [configurer un connecteur de données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Pour commencer, voir [connecteur des données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) .


## <a name="assign-admin-roles-for-access-to-cqd"></a>Attribuer des rôles d’administrateur pour accéder à bord

Attribuez des [rôles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) pour accéder à bord aux personnes qui ont besoin de les utiliser.

Si vous voulez que les utilisateurs qui ne sont pas des administrateurs (par exemple, les ingénieurs de support et les agents d’assistance) puissent utiliser le tableau de bord de qualité des appels, vous pouvez attribuer à ces utilisateurs l’un des rôles suivants, qui donnent accès à bord. 


|  |Afficher les rapports  |Afficher les champs de EUII  |Créer des rapports  |Télécharger les données de bâtiment  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général d’Office 365     |Oui         |Oui         |Oui         |Oui         |
|Administrateur du service Teams     |Oui         |Oui         |Oui         |Oui         |
|Administrateur des communications Teams     |Oui         |Oui         |Oui         |Oui         |
|Ingénieur du support technique pour les communications Teams     |Oui         |Oui         |Oui         |Non         |
|Spécialiste du support des communications teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype entreprise     |Oui         |Oui         |Oui         |Oui         |
|Lecteur global Azure AD |Oui         |Oui         |Oui         |Non         |
|Office 365-rapports sur le lecteur<sup>1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> en plus de lire des rapports bord, le lecteur de rapports d' 365 Office peut afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration et les rapports du [Pack de contenu adoption de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si vous ne voyez pas [EUII (informations d’identification de l’utilisateur final)](CQD-data-and-reports.md#euii-data) et que vous disposez de l’un des rôles autorisés à voir ces informations, n’oubliez pas que bord ne conserve que EUII pendant 28 jours. Les éléments datant de plus de 28 jours sont supprimés.

Pour plus d’informations sur ces rôles, voir [à propos des rôles d’administrateur Office 365](/office365/admin/add-users/about-admin-roles).


Lorsque vous vous connectez pour la première fois, bord commence à collecter et à traiter les données. À compter du 2019 de décembre, vous pouvez toujours accéder à l’ancienne version de bord (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier bord (cqd.teams.microsoft.com). Par la suite, l’ancienne version de bord sera mise hors service. À compter du 1er juillet 2020, l’ancienne version de bord accède aux données depuis la dernière bord.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrer des données et des rapports à partir d’une version précédente de bord

> [!IMPORTANT]
> À partir du 1er juillet 2020, vous ne pouvez plus migrer les données et les rapports à partir de l’ancien bord ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser des données de bord

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.

Pour en savoir plus, voir [utiliser Power bi pour analyser les données de bord](CQD-Power-BI-query-templates.md) .


## <a name="related-topics"></a>Sujets associés

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)
