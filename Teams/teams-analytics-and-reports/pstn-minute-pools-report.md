---
title: Rapport des pools de minutes RTC Microsoft Teams
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
description: Comment utiliser le rapport des pools de minutes RTC Teams dans le Centre d’administration Microsoft Teams pour afficher les minutes consommées au sein de votre organisation au cours du mois en cours.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: d3e2b4d7d0aba44929b7094c4146f9f69db0e8eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267369"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Rapport des pools de minutes RTC Microsoft Teams

Le rapport des pools de minutes RTC Teams dans le Centre d’administration Microsoft Teams vous donne une vue d’ensemble de l’activité d’audioconférence et d’appel dans votre organisation en vous indiquant le nombre de minutes consommées pendant le mois en cours. Vous pouvez voir une répartition de l’activité, notamment la licence utilisée pour les appels, le nombre total de minutes disponibles, les minutes utilisées et l’utilisation de la licence par emplacement.

## <a name="view-the-pstn-minute-pools-report"></a>Afficher le rapport des pools de minutes RTC

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez les **pools PSTN minute et SMS (préversion),** puis cliquez sur **Exécuter le rapport**.

![Capture d’écran du rapport des pools de minutes RTC Teams dans le centre d’administration.](../media/teams-reports-pstn-minute-pools-with-callouts.png "Capture d’écran du rapport des pools de minutes RTC Teams dans le Centre d’administration Microsoft Teams avec des légendes numérotées")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |Cliquez sur une fonctionnalité (licence) pour afficher l’activité de cette fonctionnalité. |
|**3**   |L’axe X est un pays ou une région. L’axe Y est le nombre de minutes. <br>Pointez sur une barre du graphique pour voir l’activité de cet emplacement d’utilisation.  |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **Non utilisé**, **Utilisateurs nationaux**, **Aucune donnée** ou **International utilisé** pour afficher uniquement les informations relatives à chacun d’eux. |
|**5**   |Le tableau vous donne une répartition des pools de minutes par capacité et emplacement d’utilisation. <ul><li>**Le pays ou la région** est l’emplacement d’utilisation. </li><li>**La description** de la fonctionnalité est la description de la licence utilisée pour l’appel.  Les descriptions des fonctionnalités que vous pouvez voir dans ce rapport sont les suivantes : <ul><li>Forfait d’appels nationaux et internationaux (1 200 minutes intérieures)</li><li>Forfait d’appels nationaux et internationaux (3 000 minutes nationales)</li><li>Forfait d’appels nationaux et internationaux (600 minutes internationales)</li></ul></li><br><li>**Le nombre total de minutes** correspond au nombre total de minutes disponibles pour le mois.</li><li>**Minutes utilisées** est le nombre de minutes utilisées chaque mois</li> <li>**Les minutes disponibles** sont le nombre de minutes restantes pour le mois.</li><li>**La fonctionnalité** est la licence utilisée pour l’appel. Les licences que vous pouvez voir sont les suivantes :<ul><li>**MCOPSTN1** - Forfait d’appels nationaux (3000 min US / 1200 min plans de l’UE)</li><li>**MCOPSTN2** - Plan d’appels internationaux</li><li>**MCOPSTN5** - Forfait d’appels nationaux (forfait d’appels de 120 minutes)</li><li>**MCOPSTN6** - Forfait d’appels nationaux (forfait d’appels de 240 minutes)</li><li>**MCOMEETADD** - Audioconférence</li></ul></li> </ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Sélectionnez **Plein écran** pour afficher le rapport en mode plein écran.|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
