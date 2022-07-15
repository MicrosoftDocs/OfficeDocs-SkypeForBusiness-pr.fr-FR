---
title: Configurer le tableau de bord de qualité des appels (CQD)
author: CarolynRowe
ms.author: crowe
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
description: Découvrez comment activer et utiliser le tableau de bord qualité des appels et obtenir des rapports récapitulatifs sur la qualité des appels.
ms.openlocfilehash: 052b38634d17aa6d0086c80ed2a638a7818a729f
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66797379"
---
# <a name="set-up-call-quality-dashboard"></a>Configurer le tableau de bord qualité des appels

Ouvrez le tableau de bord de qualité des appels Microsoft (CQD) à [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (connectez-vous avec vos informations d’identification d’administrateur). Ou bien allez dans le centre d'administration de Teams et sélectionnez **Analyses et rapports** > **Tableau de bord de la qualité des appels**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton Du tableau de bord De qualité des appels dans le Centre d’administration Teams.":::

Sur la page qui s’ouvre, cliquez sur **Connectez-vous** et entrez les informations de votre compte Administrateur général ou de votre compte d’administrateur Microsoft Teams. Après la première connexion, CQD commence à collecter et à traiter les données. Gardez à l’esprit qu’il peut prendre une ou plusieurs heures pour traiter suffisamment de données pour afficher des résultats significatifs dans les rapports.

CQD présente la qualité des appels et des réunions, à l’échelle de l’organisation, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019. 

> [!IMPORTANT]
> Pour utiliser CQD avec Skype Entreprise Server 2019, vous devez [Configurer le connecteur de données d’appel](/skypeforbusiness/hybrid/configure-call-data-connector). Voir [Planifier le connecteur de données d'appel](/skypeforbusiness/hybrid/plan-call-data-connector) avant de commencer.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Attribuer des rôles d’administrateur pour l’accès à CQD

Attribuez [rôles](/microsoft-365/admin/add-users/about-admin-roles) pour accéder au CQD aux personnes qui doivent l’utiliser.

Si vous souhaitez que des utilisateurs non administrateurs (tels que les ingénieurs de support et les agents du service d'assistance) utilisent Call Quality Dashboard, vous pouvez attribuer à ces utilisateurs l'un des rôles suivants, qui donne accès à CQD. 


|&nbsp;  |Affichage des rapports  |Afficher les champs EUII  |Créer des rapports  |Charger des données de génération  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général     |Oui         |Oui         |Oui         |Oui         |
|Administrateur Teams     |Oui         |Oui         |Oui         |Oui         |
|Administrateur des communications Teams     |Oui         |Oui         |Oui         |Oui         |
|Ingénieur du support technique pour les communications Teams     |Oui         |Oui         |Oui         |Non         |
|Spécialiste du support des communications Teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype Entreprise     |Oui         |Oui         |Oui         |Oui         |
|Lecteur général |Oui         |Oui         |Oui         |Non         |
|Lecteur de rapports<sup>1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> Outre la lecture des rapports CQD, le lecteur de rapports peut afficher tous les [rapports d'activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) du centre d'administration et tous les rapports du [pack de contenu Microsoft 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si vous ne voyez pas [EUII (informations d’identification de l’utilisateur final)](CQD-data-and-reports.md#euii-data) et que vous disposez de l’un des rôles autorisés à afficher ces informations, n’oubliez pas que CQD conserve uniquement EUII pendant 28 jours. Tout ce qui date de plus de 28 jours est supprimé.

Pour plus d’informations sur ces rôles, consultez [À propos des rôles d’administrateur Office 365](/office365/admin/add-users/about-admin-roles).


Après la première connexion, CQD commence à collecter et à traiter les données.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données TBQA

Nouveauté de janvier 2020 : [Télécharger Power BI modèles de requête pour les](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)CQD . Modèles de Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données CQD.

Lisez [Utilisez Power BI pour analyser les données CQD](CQD-Power-BI-query-templates.md) pour en savoir plus.

## <a name="related-topics"></a>Rubriques connexes

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)
