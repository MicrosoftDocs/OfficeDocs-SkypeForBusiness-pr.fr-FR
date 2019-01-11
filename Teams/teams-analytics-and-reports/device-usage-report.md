---
title: Rapport d’utilisation des périphériques Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 01/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
description: Découvrez comment utiliser le rapport d’utilisation de périphériques équipes Microsoft Teams et Skype entreprise centre d’administration pour afficher le mode de connexion des utilisateurs de votre organisation aux équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8c6153970d5b8be9fd10336d0388f6e7a92ca0c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893292"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques Microsoft Teams

Le rapport d’utilisation de périphériques équipes Microsoft Teams et Skype entreprise centre d’administration fournit des informations sur la façon dont les utilisateurs se connectent aux équipes. Vous pouvez utiliser le rapport pour afficher les périphériques qui sont utilisés dans votre organisation, notamment combien utiliser équipes à partir de leurs appareils mobiles lorsque sur OK.  

![Capture d’écran du rapport d’utilisation équipes périphérique dans les équipes Microsoft & Skype entreprise centre d’administration] (../media/teams-reports-device-usage.png "Capture d’écran du rapport d’utilisation équipes périphérique dans les équipes Microsoft & Skype entreprise centre d’administration")

## <a name="view-the-report"></a>Afficher le rapport

1. Accédez au site Microsoft Teams & Skype pour la navigation de gauche, du centre d’administration Business, cliquez sur **Analytique et rapports**, puis, sous **état**, sélectionnez **utilisation du périphérique équipes**. 
2. Sous **plage de dates**, sélectionnez une plage, puis cliquez sur **exécuter le rapport**. 

## <a name="interpret-the-report"></a>Interprétation du rapport

![Capture d’écran du rapport d’utilisation équipes périphérique dans les équipes Microsoft & Skype entreprise centre d’administration] (../media/teams-reports-device-usage-with-callouts.png "Capture d’écran de l’état de l’utilisation des équipes périphérique dans les équipes Microsoft & Skype entreprise centre d’administration avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation du périphérique équipes peut être affiché pour les tendances sur la dernière 7 jours ou 28 jours.  |
|**2**   |Chaque rapport possède une date pour laquelle le rapport a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils (**Windows**, **Mac**, **iOS**, **Téléphone Android**) utilisées pour se connecter aux équipes. </li><li>L’axe des Y sont le nombre d’utilisateurs à l’aide de l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un périphérique pour afficher le nombre d’utilisateurs à l’aide de l’appareil pour se connecter à des équipes.|
|**4**   |Le tableau donne une répartition de l’utilisation de périphériques par utilisateur. <ul><li>**Nom complet** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom complet pour accéder à la page Paramètres de l’utilisateur dans le Microsoft Teams & Skype entreprise centre d’administration. </li><li>**Windows** est activée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur fonctionnant sous Windows.</li><li>**Mac** est sélectionnée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur Mac OS. </li> <li>**iOS** est activée si l’utilisateur a été actif sur le client mobile équipes pour iOS.</li><li>**Téléphone Android** est activée si l’utilisateur a été actif sur le client mobile équipes pour Android. <li>**Dernière activité** est la dernière date (UTC) que l’utilisateur a participé à une activité équipes.</li> </ul> Pour afficher les informations de votre choix dans la table, veillez à ajouter les colonnes à la table. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Sélectionnez **˙˙˙**, puis **Imprimer le graphique** pour imprimer le graphique. |

## <a name="related-topics"></a>Rubriques connexes
- [Création de rapports et des équipes analytique](teams-reporting-reference.md)
- [Rapport d’utilisation des équipes](teams-usage-report.md)
- [Rapport d’activité utilisateur équipes](user-activity-report.md)