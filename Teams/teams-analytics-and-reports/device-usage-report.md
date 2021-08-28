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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation Teams’appareils dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation se connectent à Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdb7292ab36f41eb4c64233ea836f688cec49bb3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627526"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le Teams d’utilisation des appareils dans le Microsoft Teams d’administration vous fournit des informations sur la connexion des utilisateurs à Teams. Vous pouvez utiliser le rapport pour voir les appareils utilisés dans votre organisation, y compris le nombre d’appareils Teams utilisés à partir de leurs appareils mobiles lorsque vous êtes en cours.  

## <a name="view-the-device-usage-report"></a>Afficher le rapport utilisation des appareils

1. Dans la barre de navigation gauche du Centre Microsoft Teams’administration, cliquez sur **Analyse & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Teams’utilisation des appareils.**
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du Teams d’utilisation des appareils dans le Centre Teams’administration avec des appels](../media/teams-reports-device-usage-with-callouts.png "Capture d’écran du Teams d’utilisation des appareils dans le Centre d’administration Teams avec des appels")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le Teams d’utilisation des appareils peut être pris en compte pour les tendances des 7 ou 30 derniers jours.  |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils **(Windows,** **Mac,** **Linux,** **iOS,** **Android Téléphone,** **Web)** utilisés pour se connecter à Teams. </li><li>L’axe Y est le nombre d’utilisateurs de l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un appareil pour voir le nombre d’utilisateurs utilisant l’appareil pour se connecter Teams.|
|**4**   |Le tableau vous offre une répartition de l’utilisation des appareils par utilisateur. <ul><li>**Nom d’utilisateur** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour aller à la page de paramètres de l’utilisateur dans le Microsoft Teams d’administration. </li><li>**Windows** est sélectionné si l’utilisateur a été actif dans le client Teams bureau sur un Windows ordinateur.</li><li>**Mac** est sélectionné si l’utilisateur a été actif dans le client Teams bureau sur un ordinateur macOS. </li> <li>**Linux** est sélectionné si l’utilisateur a été actif dans le client Teams bureau sur un ordinateur Linux. </li> <li>**iOS** est sélectionné si l’utilisateur était actif sur le client Teams mobile pour iOS.</li><li>**L’application Téléphone Android** est sélectionnée si l’utilisateur a été actif sur Teams client mobile pour Android. <li><li>**L’application Web** est sélectionnée si l’utilisateur a été actif sur Teams client web. <li>**La dernière** activité est la dernière date (UTC) à laquelle l’utilisateur a participé à Teams activité.</li> </ul> Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche sous la forme « - » dans le tableau. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel,** puis sous l’onglet **Téléchargements,** cliquez sur Télécharger pour télécharger le rapport lorsqu’il est prêt. <br><br>![Capture d’écran de l’onglet Téléchargements affichant les rapports exportés](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour anonymisation des données Teams rapport d’utilisation des appareils, vous devez être administrateur général. Cela a pour effet de masquer les informations identifiables telles que le nom d’affichage, le courrier électronique et l’ID AAD dans le rapport et leur exportation.

1. Dans Centre d’administration Microsoft 365, sélectionnez  l’Paramètres Paramètres organisation, puis sous l’onglet \>  **Services,** sélectionnez **Rapports.**
    
2. Sélectionnez **Rapports,** puis choisissez **d’afficher les identificateurs anonymes.** Ce paramètre est appliqué aux rapports d’utilisation dans Centre d’administration Microsoft 365 ainsi qu’Teams centre d’administration.
  
3. Sélectionnez **Enregistrer les modifications.**

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
