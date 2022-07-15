---
title: Rapport d’utilisation des périphériques de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser le rapport d’utilisation des appareils Teams dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation se connectent à Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 949ad172425f5e02da2fa67078193b198cb987d1
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825508"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport d’utilisation des appareils Teams dans le Centre d’administration Microsoft Teams vous fournit des informations sur la façon dont les utilisateurs se connectent à Teams. Vous pouvez utiliser le rapport pour voir les appareils utilisés au sein de votre organisation, y compris le nombre d’utilisateurs de Teams à partir de leurs appareils mobiles en déplacement.  

## <a name="view-the-device-usage-report"></a>Afficher le rapport d’utilisation de l’appareil

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des appareils Teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport d’utilisation des appareils Teams dans le Centre d’administration Teams avec des légendes.](../media/teams-reports-device-usage-with-callouts.png "Capture d’écran du rapport d’utilisation des appareils Teams dans le Centre d’administration Teams avec des légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation des appareils Teams peut être consulté pour les tendances des 7 ou 30 derniers jours.  |
|**2**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 heures par rapport au moment de l’activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) utilisés pour se connecter à Teams. </li><li>L’axe Y correspond au nombre d’utilisateurs utilisant l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un appareil pour voir le nombre d’utilisateurs qui utilisent l’appareil pour se connecter à Teams.|
|**4**   |Le tableau vous donne une répartition de l’utilisation de l’appareil par utilisateur. <ul><li>**Le nom d’utilisateur** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams. </li><li>**Windows** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur Windows.</li><li>**Mac** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur macOS. </li> <li>**Linux** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur Linux. </li> <li>**iOS** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour iOS.</li><li>**Le téléphone Android** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour Android. <li><li>**Le web** est sélectionné si l’utilisateur était actif sur le client web Teams. <li>**La dernière activité** est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li> </ul> Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche comme « - » dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **Téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport lorsqu’il est prêt.<br><br>![Capture d’écran de l’onglet Téléchargements montrant les rapports exportés.](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour rendre les données du rapport d’utilisation des appareils Teams anonymes, vous devez être administrateur général. Cela masque les informations d’identification telles que le nom d’affichage, l’e-mail et l’ID AAD dans le rapport et leur exportation.

1. Dans Centre d'administration Microsoft 365, accédez aux **paramètres de l’organisation** **Paramètres** \> et, sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **d’afficher les identificateurs anonymes**. Ce paramètre est appliqué à la fois aux rapports d’utilisation dans Centre d'administration Microsoft 365 ainsi qu’au Centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

## <a name="related-topics"></a>Rubriques connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
