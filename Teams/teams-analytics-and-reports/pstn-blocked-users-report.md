---
title: Rapport des utilisateurs bloqués rtc Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Utilisez le rapport des utilisateurs bloqués RTC dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble des utilisateurs Teams de votre organisation qui ne peuvent pas effectuer d’appels RTC.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 8f723a9aca6cc57510aaf526297f60966a27bcda
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267379"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Rapport des utilisateurs bloqués rtc Microsoft Teams

Le rapport des utilisateurs bloqués RTC dans le Centre d’administration Microsoft Teams vous montre les utilisateurs de votre organisation qui ne peuvent pas effectuer d’appels RTC dans Teams. Vous pouvez afficher plus d’informations sur chaque utilisateur bloqué, y compris son numéro de téléphone affecté et la raison pour laquelle il a été bloqué à passer des appels.

## <a name="view-the-pstn-blocked-users-report"></a>Afficher le rapport des utilisateurs bloqués rtc

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisateurs bloqués RTC**, puis cliquez sur **Exécuter le rapport**.

![Capture d’écran du rapport de rapport des utilisateurs bloqués rtc dans le Centre d’administration.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Capture d’écran du rapport des utilisateurs bloqués RTC dans le Centre d’administration Microsoft Teams avec des légendes numérotées")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |L’axe X est la date. L’axe Y correspond au nombre d’utilisateurs. <br>Pointez sur le point à une date donnée pour voir le nombre d’utilisateurs bloqués à cette date. |
|**3**   |Le tableau présente une répartition de tous les utilisateurs qui ne peuvent pas effectuer d’appels RTC.  Il affiche tous les utilisateurs auxquels le système téléphonique ou l’audioconférence est affecté et vous donne plus d’informations sur chaque utilisateur. <ul><li>**Le nom d’affichage** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams. </li> <li>**Le téléphone** est le numéro attribué à l’utilisateur.</li> <li>**La raison du blocage** est la raison pour laquelle l’utilisateur est bloqué à passer des appels.</li><li>**L’action bloquée**  vous indique si l’utilisateur est bloqué ou débloqué pour effectuer des appels RTC dans Teams.</li> <li>**L’heure bloquée** correspond à la date et à l’heure (UTC) auxquelles l’utilisateur a été bloqué pour passer des appels.</li></li> </ul>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**4**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**5**   |Sélectionnez **Plein écran** pour afficher le rapport en mode plein écran.|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)