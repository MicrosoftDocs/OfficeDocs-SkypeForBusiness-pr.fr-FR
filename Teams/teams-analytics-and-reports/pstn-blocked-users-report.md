---
title: Rapport sur les utilisateurs bloqués RTC de Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport sur les utilisateurs bloqués RTC dans le centre d’administration de Microsoft teams pour obtenir une vue d’ensemble des utilisateurs de teams de votre organisation qui ne peuvent pas passer d’appels RTC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d7bfff166eec388247b65760c3338cb892984f3
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131676"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Rapport sur les utilisateurs bloqués RTC de Microsoft teams

Le rapport sur les utilisateurs bloqués RTC dans le centre d’administration Microsoft teams vous indique les utilisateurs de votre organisation qui ne peuvent pas passer d’appels RTC dans Teams. Vous pouvez afficher des informations supplémentaires sur chaque utilisateur bloqué, y compris son numéro de téléphone et la raison pour laquelle il a été bloqué.

## <a name="view-the-report"></a>Afficher le rapport

Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** > rapports d'**utilisation**des rapports. Dans l' **onglet Afficher les rapports** , sous **rapport**, sélectionnez **utilisateurs bloqués RTC**, puis cliquez sur **exécuter un rapport**.

![Capture d’écran du rapport de rapport sur les utilisateurs bloqués RTC dans le centre d’administration] (../media/teams-reports-pstn-blocked-users-with-callouts.png "Capture d’écran du rapport sur les utilisateurs bloqués RTC dans le centre d’administration Microsoft teams avec des légendes numérotées")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Date de génération de chaque rapport. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |L’axe X correspond à la date. L’axe Y indique le nombre d’utilisateurs. <br>Pointez sur le point d’une date donnée pour afficher le nombre d’utilisateurs bloqués à cette date. |
|**3**   |Le tableau fournit une répartition de tous les utilisateurs qui ne peuvent pas passer d’appels RTC.  Il affiche tous les utilisateurs disposant d’un système téléphonique ou d’une audioconférence attribué et vous donne des informations supplémentaires sur chaque utilisateur. <ul><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams. </li> <li>**Téléphone** correspond au numéro attribué à l’utilisateur.</li> <li>**Raison du blocage** est la raison pour laquelle l’utilisateur est empêché d’effectuer des appels.</li><li>L' **action bloqué** vous indique si l’utilisateur est bloqué ou débloqué pour passer des appels RTC dans Teams.</li> <li>Le **temps bloqué** est la date et l’heure (UTC) auxquelles l’utilisateur a été empêché de passer des appels.</li></li> </ul>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**4**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**5**   |Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** .|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)