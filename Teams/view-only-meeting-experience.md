---
title: Expérience de réunion en lecture seule
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur l’expérience de réunion en lecture seule pour les administrateurs, présentateurs et participants
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875054"
---
# <a name="teams-view-only-meeting-experience"></a>Expérience de réunion en lecture seule de Teams

> [!Note]
> Les diffusions en lecture seule sont disponibles dans Microsoft 365 E3/E5 et Microsoft 365 A3/A5. Cette fonctionnalité sera activée le 1er mars 2021 avec le mode par défaut désactivé. Le déploiement de la fonctionnalité du cloud de la communauté du secteur public Microsoft 365 (GCC) commencera à la fin du mois de mars 2021. Le déploiement du cloud de la communauté du secteur public de haut niveau (GCCH) et du Département de la Défense (DoD) s’effectuera à une date ultérieure. Vous devez modifier la stratégie par défaut après cette date si vous voulez que la fonctionnalité fonctionne par défaut. Utiliser PowerShell pour activer la valeur `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` de la stratégie.

> [!Note]
> Si votre réunion ou webinaire atteint sa capacité, Teams s’adaptera sans problème à une expérience de diffusion en lecture seule de 10 000 personnes. De plus, pendant cette période de travail à distance accru, tirez parti de diffusions encore plus importantes de 20 000 personnes jusqu’à la fin de cette année.

Microsoft Teams permet à 10 000 participants au plus de prendre part à une réunion Teams. Une fois la capacité de la réunion principale atteinte, d’autres participants y prendront part avec une expérience de lecture seule.

Les participants qui rejoignent en premier la réunion, avant que la capacité de la réunion soit atteinte, pourront obtenir l’expérience de réunion complète de Teams. Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.

Les participants qui rejoignent la réunion après la limite de la capacité de la réunion principale, ont une expérience en lecture seule.

Nous offrons un support mobile complet Android et iOS pour que les participants prennent part.

> [!Note]
> La limite actuelle pour le nombre de personnes autorisées à discuter et à appeler en réunion est de 300 en WW et 250 en, GCC, GCC de haut niveau, et DoD.

L’expérience lecture seule est désactivée par défaut pour tout organisateur ayant une référence SKU E3/E5/A3/A5. Aucune configuration supplémentaire n’est requise.

## <a name="disable-teams-view-only-experience"></a>Désactiver l’expérience lecture seule de Teams

Les administrateurs peuvent désactiver l’expérience lecture seule à l’aide de PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

Dans le futur, les administrateurs pourront également désactiver l’expérience lecture seule dans le centre d’administration Teams.

## <a name="impact-to-users"></a>Conséquences sur les utilisateurs

L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.

Une fois la capacité de la réunion principale atteinte, le participant ne peut pas prendre pas à la réunion si l’un de ces cas est avéré :

- Un administrateur a désactivé l’expérience lecture seule de Teams.
- Le participant n’est pas autorisé à contourner la salle d’attente.

Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que la capacité de la réunion est atteinte et que les nouveaux participants prendront part en lecture seule.

  ![Le client Teams et le message de la bannière pour les organisateurs et présentateurs](media/chat-and-banner-message.png)

Une fois la capacité de la réunion principale atteinte, les participants sont informés à l’écran de participation préalable qu’ils prennent part en mode lecture seule.

  ![L’écran de participation préalable de Teams et le message aux participants les informant de leur participation en mode lecture seule](media/view-only-pre-join-screen.png)

S’il y a de l’espace, l’utilisateur pourra toujours participer à la réunion principale. Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, il y aura encore de la place à la réunion principale. Les participants qui prennent part (ou qui participent à nouveau) à la réunion, participeront à la réunion principale jusqu’à la limite de sa capacité. Les participants en mode lecture seule ne peuvent pas rejoindre automatiquement la réunion principale et ne peuvent pas le faire manuellement pour l’instant.

Si les rôles de présentateur/participant n’ont pas été définis, les espaces de la réunion principale sont remplis selon le principe du premier arrivé, premier servi. Une fois la capacité de la réunion atteinte, tous les autres utilisateurs peuvent participer avec une expérience lecture seule.

## <a name="impact-to-meeting-presenters"></a>Impact sur les présentateurs de réunion

Les limitations pour les présentateurs de réunion sont :

- Vous n’avez aucune information sur le participant en lecture seule. La découverte électronique n’est pas prise en charge pour les participants en lecture seule.
- Les utilisateurs ne peuvent pas voir les participants en lecture seule.
- Vous ne pouvez pas supprimer un participant en lecture seule de la réunion.

> [!Note]
> Le nombre de participants reflète uniquement les participants à la réunion, et non les participants dans la salle de lecture seule. Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact de personnes qui ont l’expérience lecture seule.

## <a name="experience-for-view-only-attendees"></a>Expérience des participants en lecture seule

L’expérience lecture seule de Teams permet aux participants de :

- Écouter les participants à la réunion principale Teams.
- Consulter le flux vidéo de l’intervenant actif (si l’intervenant  actif partage une vidéo).
- Consulter le contenu partagé à l’aide de la fonctionnalité Partager le bureau.

Le participant en lecture seule ne pourra pas utiliser ces options dans les réunions :

- Participer à la réunion si le participant n’est pas autorisé à contourner la salle d'attente en fonction des stratégies ou options de salle d'attente définies.
- Rejoindre la salle de lecture seule à l’aide de la conférence audio.
- Rejoindre la salle de lecture seule à l’aide du système de salle Microsoft Teams ou des services Cloud Video Interop (CVI).
- Partager leur contenu audio ou vidéo.
- Consulter ou participer à la conversation de réunion.
- Consulter le flux vidéo des participants à la réunion, sauf si le participant est l’intervenant actif.
- Consulter les fichiers PowerPoint partagés à l’aide de la fonctionnalité de partage natif de PowerPoint ou des partages d’applications individuels (autres que le partage de bureau).

## <a name="view-only-feature-limitations"></a>Limitations de la fonctionnalité lecture seule

- Les participants en lecture seule voient toujours des sous-titres en direct, quel que soit le paramètre de sous-titres en direct de cette réunion. Seuls les sous-titres en anglais sont pris en charge pour l’instant.
- Les participants en lecture seule sont pris en charge par la technologie de diffusion en continu.
- Les participants en lecture seule ne sont pas inclus dans le rapport de participation.
- Les participants en lecture seule ont une expérience vidéo unique. Ils peuvent voir l’intervenant actif ou le contenu partagé, mais pas les deux.
- Pour le moment, les dispositions de la **Galerie**, la **Grade galerie**, ou du **Mode Ensemble** ne sont pas prises en charge pour les participants en lecture seule.  
- Les participants en lecture seule n’ont pas la même latence qu’un participant ordinaire. <sup>1</sup>

  <sup>1</sup> participants en lecture seule ont un retard audio et vidéo de 30 secondes pendant la réunion.  
