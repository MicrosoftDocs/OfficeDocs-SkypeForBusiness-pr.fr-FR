---
title: Rapport d’utilisation des périphériques de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport Utilisation de Teams sur des appareils dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation se connectent à Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815644"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport Utilisation de Teams sur des appareils du Centre d’administration Microsoft Teams fournit des informations sur la connexion des utilisateurs à Teams. Vous pouvez utiliser le rapport pour voir les appareils utilisés dans votre organisation, y compris le nombre d’appareils mobiles utilisés par Teams lorsque vous êtes en cours.  

## <a name="view-the-device-usage-report"></a>Afficher le rapport utilisation des appareils

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse pour & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Utilisation de Teams sur les appareils.**
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Rapport d’utilisation de Teams sur des appareils dans le Centre d’administration Teams avec des appels](../media/teams-reports-device-usage-with-callouts.png "Rapport d’utilisation de Teams sur des appareils dans le Centre d’administration Teams avec des appels")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport Utilisation de Teams sur des appareils permet d’afficher les tendances des 7 ou 30 derniers jours.  |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils **(Windows,** **Mac,** **Linux,** **iOS,** **Téléphone Android,** **Web)** utilisés pour se connecter à Teams. </li><li>L’axe Y est le nombre d’utilisateurs de l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un appareil pour voir le nombre d’utilisateurs utilisant l’appareil pour se connecter à Teams.|
|**4**   |Le tableau vous offre une répartition de l’utilisation des appareils par utilisateur. <ul><li>**Nom d’utilisateur** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour afficher la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams. </li><li>**Windows** est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur Windows.</li><li>**Mac** est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur macOS. </li> <li>**Linux** est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur Linux. </li> <li>**iOS** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour iOS.</li><li>**Le téléphone Android** est sélectionné si l’utilisateur a été actif sur le client mobile Teams pour Android. <li><li>**L’application Web** est sélectionnée si l’utilisateur a été actif sur le client web Teams. <li>**La dernière** activité est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li> </ul> Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche sous la forme « - » dans le tableau. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel,** puis sous  l’onglet **Téléchargements,** cliquez sur Télécharger pour télécharger le rapport lorsqu’il est prêt.<br><br>![Capture d’écran de l’onglet Téléchargements affichant les rapports exportés](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
