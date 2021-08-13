---
title: Configurer le tableau de bord de qualité des appels (CQD)
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
description: Découvrez comment activer et utiliser le Tableau de bord de qualité des appels et obtenir des rapports récapitulatifs sur la qualité des appels.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300450"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Comment configurer le tableau de bord de qualité des appels

Ouvrez le Tableau de bord de qualité des appels Microsoft (CQD) à [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) l’adresse (connectez-vous avec vos informations d’identification d’administrateur). Ou allez dans le Centre d Teams’administration et sélectionnez **Tableau de bord de qualité des appels.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration":::

Dans la page qui s’ouvre, cliquez sur **Se** connectez et entrez votre compte Administrateur général ou Microsoft Teams’administrateur général. Une fois que vous vous connectez pour la première fois, le CQD commence la collecte et le traitement des données. N’oubliez pas que le traitement d’un nombre suffisant de données peut prendre une ou plusieurs heures pour afficher des résultats significatifs dans les rapports.

Le CQD indique la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019. 

> [!IMPORTANT]
> Pour utiliser le CQD avec Skype Entreprise Server 2019, vous devez configurer le connecteur de [données d’appel.](/skypeforbusiness/hybrid/configure-call-data-connector) Voir [Planifier le connecteur de données d’appel](/skypeforbusiness/hybrid/plan-call-data-connector) avant de commencer.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Attribuer des rôles d’administrateur pour l’accès au CQD

Attribuez [des rôles](/microsoft-365/admin/add-users/about-admin-roles) pour accéder au CQD aux personnes qui doivent l’utiliser.

Si vous souhaitez que les utilisateurs non administrateurs (tels que les ingénieurs du support technique et les agents du support technique) utilisent le Tableau de bord de qualité des appels, vous pouvez attribuer à ces utilisateurs l’un des rôles suivants, ce qui donne accès au tableau de bord de qualité des appels. 


|&nbsp;  |Affichage des rapports  |Afficher les champs EUII  |Créer des rapports  |Télécharger de création de données  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général     |Oui         |Oui         |Oui         |Oui         |
|Teams Administrateur     |Oui         |Oui         |Oui         |Oui         |
|Administrateur des communications Teams     |Oui         |Oui         |Oui         |Oui         |
|Ingénieur de support des communications Teams     |Oui         |Oui         |Oui         |Non         |
|Spécialiste du support des communications Teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype Entreprise     |Oui         |Oui         |Oui         |Oui         |
|Lecteur général |Oui         |Oui         |Oui         |Non         |
|Lecteur de<sup>rapports 1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1 En</sup> plus de lire les rapports CQD, le lecteur de rapports peut afficher tous les rapports d’activité dans le Centre d’administration et tous les rapports du [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) [pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)de contenu adoption Microsoft 365.

> [!NOTE]
> Si vous ne voyez pas eu d’EUII [(informations d’identification](CQD-data-and-reports.md#euii-data) d’utilisateur final) et que vous avez l’un des rôles autorisés à voir ces informations, n’oubliez pas que le CQD ne conserve l’EUII que pendant 28 jours. Tout ce qui est plus ancien que 28 jours est supprimé.

Pour plus d’informations sur ces rôles, voir [à Office 365 rôles d’administrateur.](/office365/admin/add-users/about-admin-roles)


Une fois que vous vous connectez pour la première fois, le CQD commence la collecte et le traitement des données. À partir de décembre 2019, vous pouvez toujours accéder à l’ancienne version de CQD (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier CQD (cqd.teams.microsoft.com). Finalement, l’ancienne version de CQD sera mise hors service. Depuis le 1er juillet 2020, l’ancienne version du CQD accède aux données à partir du dernier CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrer des données de génération et des rapports à partir d’une version précédente du CQD

> [!IMPORTANT]
> À compter du 1er juillet 2020, vous ne pouvez plus migrer les données de création et les rapports à partir de l’ancien CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données TBQA

Nouveauté de janvier 2020 : téléchargez Power BI de requête [pour CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modèles Power BI personnalisés que vous pouvez utiliser pour analyser et signaler vos données de qualité de service.

En lecture Utilisez Power BI pour analyser les données [du CQD](CQD-Power-BI-query-templates.md) pour en savoir plus.


## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)
