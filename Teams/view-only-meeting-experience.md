---
title: Expérience de réunion en affichage seul
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur l’expérience de réunion en affichage seul teams pour les administrateurs, les présentateurs et les participants
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f65e1ff47caefd61a9b2753b12da23fd2184e9
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401318"
---
# <a name="teams-view-only-meeting-experience"></a>Expérience de réunion en affichage seul dans Teams

> [!Note]
> L’expérience de réunion en affichage seul sera disponible début mars 2021. Cette fonctionnalité sera activée par défaut le 1er mars 2021. Vous devez modifier la stratégie par défaut après cette date si vous souhaitez que la fonctionnalité par défaut soit sous l’option. Utilisez PowerShell pour activer la `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` stratégie.

> [!Note]
> Si la capacité de réunion ou de webinaire atteint sa capacité, Teams s’adaptera sans problème à une expérience de diffusion en affichage seul de 10 000 personnes. De plus, à cette période de travail à distance accrue, tirez parti de plus de 20 000 diffusions encore plus grandes jusqu’à la fin de cette année.

Microsoft Teams permet à jusqu’à 10 000 participants de participer à une réunion Teams. Une fois la capacité de la réunion principale atteinte, les participants supplémentaires la rejoignent avec une expérience de vue seule.

Les participants qui rejoignent la réunion en premier, jusqu’à la capacité de la réunion, auront accès à l’expérience complète de la réunion Teams. Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.

Les participants qui rejoignent la réunion une fois la capacité principale de la réunion atteinte auront une expérience en affichage seul.

Nous avons un support mobile Android et iOS complet pour qu’un participant participe.

> [!Note]
> La limite actuelle du nombre de personnes qui peuvent discuter et appeler pour une réunion est de 300 dans WW et 250 dans GCC, GCC High et DoD.

L’expérience en affichage seul est désactivée par défaut pour tout organisateur activant la référence SKU E3/E5/A3/A5. Aucune autre configuration ou configuration n’est requise.

## <a name="disable-teams-view-only-experience"></a>Désactiver l’affichage seul dans Teams

Les administrateurs peuvent désactiver l’expérience d’affichage seul à l’aide de PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

À l’avenir, les administrateurs pourront également désactiver l’expérience d’affichage seul dans le Centre d’administration Teams.

## <a name="impact-to-users"></a>Impact sur les utilisateurs

L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.

Une fois la capacité de la réunion principale atteinte, un participant ne pourra pas participer à la réunion si l’une des raisons suivantes est vraie :

- Un administrateur a désactivé l’expérience teams en affichage seul.
- Le participant n’est pas autorisé à contourner la salle d’accueil.

Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que la capacité de la réunion a été atteinte et que les nouveaux participants rejoindront un participant en affichage seul.

  ![Panne du client Teams et de la bannière pour les organisateurs et les présentateurs](media/chat-and-banner-message.png)

Une fois la capacité de la réunion principale atteinte, les participants à la réunion seront informés sur l’écran de pré-participation qu’ils la rejoignent en mode affichage seul.

  ![Écran de pré-participation à Teams et message pour les participants leur disant qu’ils seront rejoints en mode affichage seul](media/view-only-pre-join-screen.png)

S’il y a de l’espace, l’utilisateur rejoint toujours la réunion principale. Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, la réunion principale a une capacité disponible. Les participants qui rejoignent (ou rejoignent) la réunion rejoindront la réunion principale jusqu’à ce qu’elle atteigne à nouveau sa capacité. Les participants à l’expérience en affichage seul ne sont pas automatiquement promus à la réunion principale et ne peuvent pas actuellement être promus manuellement à la réunion principale.

Si les rôles de présentateur/participant n’ont pas été définies, les espaces de la réunion principale sont remplis sur la base du premier arrivé, premier servi. Une fois la capacité de la réunion atteinte, tous les autres utilisateurs la rejoignent avec une expérience en affichage seul.

## <a name="impact-to-meeting-presenters"></a>Impact sur les présentateurs de réunion

Les limitations pour les présentateurs de réunion sont les suivantes :

- Vous n’aurez aucune information sur le participant en affichage seul. La découverte électronique n’est pas prise en charge pour les participants en affichage seul.
- Les utilisateurs ne peuvent pas voir les participants en affichage seul.
- Vous ne pouvez pas supprimer un participant en affichage seul de la réunion.

> [!Note]
> Le nombre de participants reflète uniquement les participants à la réunion et non les personnes dans la salle de débordement. Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact des personnes présentes dans l’expérience en affichage seul.

## <a name="experience-for-view-only-attendees"></a>Expérience pour les participants en affichage seul

L’expérience Teams en affichage seul permet aux participants d':

- Écoutez les participants à la réunion Teams principale.
- Consultez le flux vidéo du haut-parleur actif (si celui-ci partage la vidéo).
- Voir le contenu partagé à l’aide de la fonctionnalité de partage du Bureau.

Le participant en affichage seul ne pourra pas découvrir les options suivantes dans les réunions :

- Participez à la réunion si le participant n’est pas autorisé à contourner la salle d’accueil en fonction des stratégies ou options définies en matière de salle d’accueil.
- Rejoignez la salle de débordement via l’audioconférence.
- Rejoignez la salle de débordement via le système de salle de Réunion de Microsoft Teams ou via les services Cloud Video Interop (CVI).
- Partagez l’audio ou la vidéo.
- Voir ou participer à la conversation de réunion.
- Consultez le flux vidéo des participants à la réunion, sauf s’il s’agit du haut-parleur actif.
- Consultez les fichiers PowerPoint partagés à l’aide de la fonctionnalité de partage native de PowerPoint ou des partages d’application individuels (autres que le partage de bureau).

## <a name="view-only-feature-limitations"></a>Limitations des fonctionnalités en affichage seul

- Les participants en affichage seul voient toujours les sous-titres en direct, quel que soit le paramètre de sous-titres en direct pour cette réunion. Seules les légendes anglaises sont actuellement pris en charge.
- Les participants en affichage seul seront pris en charge par la technologie de diffusion en continu.
- Les participants en affichage seul ne seront pas inclus dans le rapport de présence.
- Les participants en affichage seul auront une expérience vidéo unique. Ils peuvent voir le haut-parleur actif ou le contenu partagé, mais pas les deux.
- Pour le moment, les dispositions **Galerie,** **Grande galerie** ou **Ensemble** ne sont pas prise en charge pour les participants en mode Affichage seul.  
- Les participants en affichage seul n’auront pas la même latence qu’un participant ordinaire. <sup>1</sup>

  <sup>1</sup> Participants en affichage seul auront un délai audio et vidéo de 30 secondes dans la réunion.  

## <a name="related-topics"></a>Sujets associés

- [Modules de communication avancés pour Teams](teams-add-on-licensing/advanced-communications.md)
- [Spécifications et limites de Microsoft Teams](limits-specifications-teams.md)
