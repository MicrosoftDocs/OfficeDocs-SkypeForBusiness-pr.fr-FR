---
title: Rapport d’utilisation des périphériques de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation de Microsoft teams dans le centre d’administration de Microsoft teams pour savoir comment les utilisateurs de votre organisation se connectent à Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfe8b11d633a8848d73e87c8fe0b4ecc8854062f
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667110"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport utilisation des appareils teams dans le centre d’administration Microsoft teams vous fournit des informations sur la façon dont les utilisateurs se connectent à Teams. Vous pouvez utiliser le rapport pour afficher les appareils utilisés au sein de votre organisation, y compris le nombre d’équipes de leur appareil mobile lorsque vous êtes en déplacement.  

## <a name="view-the-report"></a>Afficher le rapport

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse & rapports**puis sous **rapport**, sélectionnez **utilisation des appareils teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport sur l’utilisation de Microsoft teams sur les appareils dans le centre d’administration des équipes avec légendes] (../media/teams-reports-device-usage-with-callouts.png "Capture d’écran du rapport sur l’utilisation de Microsoft teams sur les appareils dans le centre d’administration des équipes avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport utilisation des appareils teams peut être consulté pour les tendances au cours des 7, ou 28 derniers jours.  |
|**2**   |Chaque rapport comporte une date à laquelle le rapport a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |<ul><li>L’axe X sur le graphique représente les différents appareils (**Windows**, **Mac**, **iOS**, **téléphone Android**) utilisés pour vous connecter à Teams. </li><li>L’axe Y indique le nombre d’utilisateurs de l’appareil sur la période sélectionnée.</li> </ul>Placez le pointeur de la souris sur la barre représentant un appareil pour connaître le nombre d’utilisateurs de l’appareil à se connecter à Teams.|
|**4**   |Le tableau présente une répartition de l’utilisation de l’appareil par l’utilisateur. <ul><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams. </li><li>**Windows** est sélectionné si l’utilisateur a été actif dans le client de bureau teams sur un ordinateur exécutant Windows.</li><li>L’option **Mac** est activée si l’utilisateur a été actif dans le client de bureau teams sur un ordinateur MacOS. </li> <li>**iOS** est sélectionné si l’utilisateur a été actif dans le client mobile teams pour iOS.</li><li>Le **téléphone Android** est sélectionné si l’utilisateur a été actif sur le client mobile teams pour Android. <li>**Dernière activité** correspond à la dernière date (UTC) à laquelle l’utilisateur a participé à une activité d’équipe.</li> </ul> Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur est affiché en tant que «--» dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br><br>![Capture d’écran de l’onglet téléchargements montrant les rapports exportés](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)