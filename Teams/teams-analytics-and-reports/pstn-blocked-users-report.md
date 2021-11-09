---
title: Microsoft Teams Rapport sur le blocage d’utilisateurs PSTN
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Utilisez le rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble des utilisateurs Teams de votre organisation qui ne peuvent pas passer d’appels PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a89e7ead560e3782d7120884a047110118d2ecd0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840686"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams Rapport sur le blocage d’utilisateurs PSTN

Le rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration Microsoft Teams affiche les utilisateurs de votre organisation qui sont bloqués et ne peuvent plus effectuer d’appels PSTN dans Teams. Vous pouvez afficher plus d’informations sur chaque utilisateur bloqué, y compris son numéro de téléphone affecté et la raison pour laquelle il a été bloqué.

## <a name="view-the-pstn-blocked-users-report"></a>Afficher le rapport sur le blocage d’utilisateurs PSTN

Dans le panneau de navigation gauche du Centre Microsoft Teams’administration, cliquez sur **Analyse & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Utilisateurs PSTN** bloqués, puis cliquez sur **Exécuter le rapport.**

![Rapport sur le blocage d’utilisateurs PSTN dans le Centre d’administration](../media/teams-reports-pstn-blocked-users-with-callouts.png "Capture d’écran du rapport sur le blocage d’utilisateurs PSTN dans le Centre d Microsoft Teams d’administration Microsoft Teams des appels numéroés")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |L’axe X est la date. L’axe Y est le nombre d’utilisateurs. <br>Pointez sur le point à une date donnée pour voir le nombre d’utilisateurs bloqués à cette date. |
|**3**   |Le tableau détailne tous les utilisateurs bloqués et ne peuvent plus effectuer d’appels PSTN.  Il affiche tous les utilisateurs Système téléphonique ou l’audioconférence et vous donne des informations supplémentaires sur chacun d’eux. <ul><li>**Le nom d’affichage** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour aller à la page de paramètres de l’utilisateur dans le Microsoft Teams d’administration. </li> <li>**Téléphone** est le numéro affecté à l’utilisateur.</li> <li>**La raison du blocage** est la raison pour laquelle l’utilisateur est bloqué et ne peut plus effectuer d’appels.</li><li>**L’action** bloquée vous indique si l’utilisateur est bloqué ou débloqué contre les appels PSTN dans Teams.</li> <li>**L’heure** bloquée est la date et l’heure (UTC) à laquelle l’utilisateur a été bloqué.</li></li> </ul>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**4**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**5**   |Sélectionnez **Plein écran** pour afficher le rapport en mode Plein écran.|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)