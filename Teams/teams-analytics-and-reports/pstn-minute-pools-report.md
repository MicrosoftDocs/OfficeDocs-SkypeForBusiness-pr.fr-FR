---
title: Rapport sur les pools de minutes PSTN de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Comment utiliser le rapport des groupes de minutes PSTN Teams dans le Centre d’administration Microsoft Teams pour afficher les minutes consommées au sein de votre organisation pendant le mois en cours.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809344"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Rapport sur les pools de minutes PSTN de Microsoft Teams

Le rapport sur les pools de minutes PSTN Teams dans le Centre d’administration Microsoft Teams vous donne une vue d’ensemble de l’activité d’audioconférence et d’appels dans votre organisation en vous indiquant le nombre de minutes consommées au cours du mois en cours. Vous pouvez consulter le détail de l’activité, notamment la licence utilisée pour les appels, le nombre total de minutes disponibles, les minutes utilisées et l’utilisation des licences par emplacement.

## <a name="view-the-pstn-minute-pools-report"></a>Afficher le rapport sur les pools de minutes PSTN

Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse pour & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez des pools de **minutes PSTN,** puis cliquez sur **Exécuter le rapport.**

![Capture d’écran du rapport des pools de minutes PSTN Teams dans le Centre d’administration](../media/teams-reports-pstn-minute-pools-with-callouts.png "Capture d’écran du rapport des groupes de minutes PSTN Teams dans le Centre d’administration Microsoft Teams avec des appels numéroés")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**2**   |Cliquez sur une fonctionnalité (licence) pour afficher l’activité de celle-ci. |
|**3**   |L’axe X est le pays ou la région. L’axe Y compte le nombre de minutes. <br>Pointez sur une barre du graphique pour voir l’activité en fonction de cet emplacement d’utilisation.  |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez **sur Utilisateurs** non **utilisés,** Utilisateurs nationaux, Aucune donnée ou **International** pour voir uniquement les informations relatives à chacune de ces tâches. |
|**5**   |Le tableau offre une répartition des groupes de minutes par fonctionnalité et emplacement d’utilisation. <ul><li>**Le pays ou la région est** le lieu d’utilisation. </li><li>**La description de** la fonctionnalité est la description de la licence utilisée pour l’appel.  Les descriptions des fonctionnalités que vous verrez peut-être dans ce rapport sont les suivantes : <ul><li>Forfait d’appels nationaux et internationaux (1 200 minutes nationales)</li><li>Forfait d’appels nationaux et internationaux (3 000 minutes nationales)</li><li>Forfait d’appels nationaux et internationaux (600 minutes internationales)</li></ul></li><br><li>**Le nombre** total de minutes est le nombre total de minutes disponibles pour le mois.</li><li>**Le nombre de** minutes utilisées est le nombre de minutes utilisées chaque mois.</li> <li>**Le nombre de** minutes disponibles est le nombre de minutes restantes pour le mois.</li><li>**La fonctionnalité** est la licence utilisée pour l’appel. Les licences que vous pouvez voir sont les suivantes :<ul><li>**MCOPSTNPP** - Crédits de communication</li><li>**MCOPSTN1** - Plan d’appels nationaux (plans de 3 000 min POUR les États-Unis / 1 200 min pour l’UE)</li><li>**MCOPSTN2** - Forfait d’appels internationaux</li><li>**MCOPSTN5** - Forfait d’appels nationaux (forfait d’appels de 120 min)</li><li>**MCOPSTN6** - Forfait d’appels nationaux (plan d’appels de 240 min)</li><li>**MCOMEETADD** - Audioconférence</li><li>**MCOMEETACPEA** - Audioconférence avec paiement à la minute</li></ul></li> </ul> Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Sélectionnez **Plein écran** pour afficher le rapport en mode Plein écran.|

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)