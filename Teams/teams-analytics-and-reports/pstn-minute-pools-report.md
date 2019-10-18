---
title: Rapport de pools de minutes RTC de Microsoft teams
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
- M365-voice
description: Pour connaître le nombre de minutes consommées au cours du mois en cours au sein de votre organisation, voir utiliser le rapport sur les pools RTC de Microsoft teams dans le centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f67bc5e20d9e1f23e63b0b4c78b3e198d4b30a40
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568387"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Rapport de pools de minutes RTC de Microsoft teams

Le rapport pools de minutes RTC dans le centre d’administration Microsoft teams vous donne une vue d’ensemble de la fonction de conférence et d’appel audio au sein de votre organisation en vous montrant le nombre de minutes consommées pendant le mois en cours. Vous pouvez voir une répartition des activités, y compris la licence utilisée pour les appels, les minutes totales disponibles, les minutes utilisées et l’utilisation des licences par emplacement.

## <a name="view-the-report"></a>Afficher le rapport

Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** > rapports d'**utilisation**des rapports. Dans l' **onglet Afficher les rapports** , sous **rapport**, sélectionnez **pools de minutes RTC**, puis cliquez sur exécuter un **rapport**.

![Capture d’écran du rapport équipes RTC minutes dans le centre d’administration](../media/teams-reports-pstn-minute-pools-with-callouts.png "Capture d’écran du rapport équipes RTC minutes RTC dans le centre d’administration Microsoft teams avec des légendes numérotées")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Date de génération de chaque rapport. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |Cliquez sur une fonctionnalité (licence) pour afficher l’activité de cette fonctionnalité. |
|**3**   |L’axe X est le pays ou la région. L’axe Y représente le nombre de minutes. <br>Placez le pointeur de la souris sur une barre du graphique pour afficher les activités correspondant à ce lieu d’utilisation.  |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur non **utilisé**, **utilisateurs nationaux**, **pas de données**ou **international** pour afficher uniquement les informations relatives à chacun d’eux. |
|**5**   |Le tableau fournit une répartition des regroupements de minutes par fonctionnalité et par lieu d’utilisation. <ul><li>Le **pays ou la région** correspond au lieu d’utilisation. </li><li>La description de la **fonctionnalité** est la description de la licence utilisée pour l’appel.  Les descriptions de fonctionnalités que vous pouvez voir dans ce rapport sont les suivantes : <ul><li>Forfait d’appels nationaux et internationaux (1200-minutes nationales)</li><li>Forfait d’appels nationaux et internationaux (3000-minutes nationales)</li><li>Forfait d’appels nationaux et internationaux (minutes internationales 600)</li></ul></li><br><li>Nombre **total de minutes** est le nombre total de minutes disponibles pour le mois.</li><li>**Minutes utilisée** est le nombre de minutes utilisées par mois</li> <li>**Minutes disponibles** est le nombre de minutes restantes pour le mois.</li><li>**Capability** est la licence utilisée pour l’appel. Les licences que vous pouvez voir sont les suivantes :<ul><li>**MCOPSTNPP** -crédits de communication</li><li>**MCOPSTN1** -forfait d’appels nationaux (3000 min US/1200 min Europe)</li><li>**MCOPSTN2** -forfait d’appels internationaux</li><li>**MCOPSTN5** -forfait d’appels nationaux (forfait d’appels min 120)</li><li>**MCOPSTN6** -forfait d’appels nationaux (forfait d’appels min 240)</li><li>**MCOMEETADD** -audioconférence</li><li>**MCOMEETACPEA** -audioconférence à la minute</li></ul></li> </ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Pour afficher le rapport en mode plein écran, sélectionnez **plein écran** .|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)