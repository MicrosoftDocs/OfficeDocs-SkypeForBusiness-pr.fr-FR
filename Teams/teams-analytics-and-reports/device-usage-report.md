---
title: Rapport d’utilisation des périphériques de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation du périphérique équipes dans le centre d’administration Microsoft Teams pour afficher le mode de connexion des utilisateurs de votre organisation aux équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5b912a9a4d76fd1be2947cea6dd2750ddbaa49
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2019
ms.locfileid: "33495896"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport d’utilisation du périphérique dans le centre d’administration Microsoft Teams équipes fournit des informations sur la façon dont les utilisateurs se connectent aux équipes. Vous pouvez utiliser le rapport pour afficher les périphériques qui sont utilisés dans votre organisation, notamment combien utiliser équipes à partir de leurs appareils mobiles lorsque sur OK.  

![Capture d’écran du rapport d’utilisation équipes périphériques dans le centre d’administration Microsoft équipes] (../media/teams-reports-device-usage.png "Capture d’écran du rapport d’utilisation équipes périphériques dans le centre d’administration Microsoft équipes")

## <a name="view-the-report"></a>Afficher le rapport

1. Accédez au centre d’administration Microsoft Teams, dans la navigation de gauche, cliquez sur **rapports de & Analytique**, puis, sous **état**, sélectionnez **utilisation du périphérique équipes**. 
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**. 

## <a name="interpret-the-report"></a>Interpréter le rapport

![Capture d’écran du rapport d’utilisation équipes périphériques dans le centre d’administration Microsoft équipes] (../media/teams-reports-device-usage-with-callouts.png "Capture d’écran de l’état de l’utilisation des équipes périphérique dans le centre d’administration équipes Microsoft avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation du périphérique équipes peut être affiché pour les tendances sur la dernière 7 jours ou 28 jours.  |
|**2**   |Chaque rapport possède une date pour laquelle le rapport a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils (**Windows**, **Mac**, **iOS**, **Téléphone Android**) utilisées pour se connecter aux équipes. </li><li>L’axe des Y sont le nombre d’utilisateurs à l’aide de l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un périphérique pour afficher le nombre d’utilisateurs à l’aide de l’appareil pour se connecter à des équipes.|
|**4**   |Le tableau donne une répartition de l’utilisation de périphériques par utilisateur. <ul><li>**Nom complet** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom complet pour accéder à la page Paramètres de l’utilisateur dans le centre d’administration Microsoft Teams. </li><li>**Windows** est activée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur fonctionnant sous Windows.</li><li>**Mac** est sélectionnée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur Mac OS. </li> <li>**iOS** est activée si l’utilisateur a été actif sur le client mobile équipes pour iOS.</li><li>**Téléphone Android** est activée si l’utilisateur a été actif sur le client mobile équipes pour Android. <li>**Dernière activité** est la dernière date (UTC) que l’utilisateur a participé à une activité équipes.</li> </ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV pour l’analyse en mode hors connexion. Cliquez sur **Exporter vers Excel**, puis sur l’onglet **Downloads** , cliquez sur **Télécharger** pour télécharger le rapport lorsque celle-ci est prête.<br>![Capture d’écran de l’onglet Downloads affichant exportés pour télécharger les rapports](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Voir aussi
- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rapport d’utilisation Teams](teams-usage-report.md)
- [Rapport d’activité d’utilisateur Teams](user-activity-report.md)