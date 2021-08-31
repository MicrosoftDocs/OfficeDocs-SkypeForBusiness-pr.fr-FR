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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2af0ae753357497be6ea54b89534f2220b7cbf6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732293"
---
# <a name="teams-view-only-meeting-experience"></a>Expérience de réunion en lecture seule de Teams

> [!Note]
> Les diffusions en lecture seule sont disponibles dans Microsoft 365 E3/E5 et Microsoft 365 A3/A5. Cette fonctionnalité sera activée le 1er mars 2021 avec le mode par défaut désactivé. Le déploiement de la fonctionnalité du cloud de la communauté du secteur public Microsoft 365 (GCC) commencera à la fin du mois de mars 2021. Le déploiement du cloud de la communauté du secteur public de haut niveau (GCCH) et du Département de la Défense (DoD) s’effectuera à une date ultérieure. Vous devez modifier la stratégie par défaut après cette date si vous voulez que la fonctionnalité fonctionne par défaut. Utiliser PowerShell pour activer la valeur `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` de la stratégie.

> [!Note]
> Si votre réunion atteint sa capacité, Teams’échelle sans problème pour tenir compte d’une expérience de diffusion en affichage seul de 10 000 personnes. De plus, pendant cette période de travail à distance accru, tirez parti de diffusions encore plus importantes de 20 000 personnes jusqu’à la fin de cette année. Les webinaires ne supportent pas actuellement une expérience de diffusion en affichage seul.

Microsoft Teams permet à 10 000 participants au plus de prendre part à une réunion Teams. Une fois la capacité de la réunion principale atteinte (lorsque 1 000 utilisateurs participent à une réunion), les participants supplémentaires la rejoignent avec une expérience en affichage seul.

Les participants qui rejoignent la réunion en premier, jusqu’à la capacité de la réunion principale, obtiennent l’expérience complète Teams réunion. Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.

Les participants qui rejoignent la réunion après la limite de la capacité de la réunion principale, ont une expérience en lecture seule.

Les participants pourront rejoindre l’expérience d’affichage seul via le Bureau, le web et Teams mobile (Android et iOS).

> [!Note]
> La capacité limite actuelle de la « réunion principale », c’est-à-dire le nombre d’utilisateurs entièrement interactifs, est de 1 000 et inclut des Cloud de la communauté du secteur public et des webinaires.

## <a name="teams-view-only-experience-controls"></a>Teams contrôles d’expérience en affichage seul

Vous activez l’expérience d’affichage seul à l’aide de l’cmdlet du [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) [module SkypeForBusiness PowerShell](/powershell/module/skype/?view=skype-ps) ou au moins la version 2.0.0 du [module MicrosoftTeams.](https://www.powershellgallery.com/packages/MicrosoftTeams)

Pour utiliser le `MicrosoftTeams` module recommandé :

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

Pour activer l’expérience d’affichage seul, vous pouvez utiliser l’extrait PowerShell suivant :

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Pour désactiver l’expérience d’affichage seul, vous pouvez également utiliser PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

À l’avenir, vous pourrez activer ou désactiver l’expérience d’affichage seul dans le Teams d’administration.

## <a name="impact-to-users"></a>Conséquences sur les utilisateurs

L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.

Une fois la capacité de la réunion principale atteinte, le participant ne peut pas prendre pas à la réunion si l’un de ces cas est avéré :

- Un administrateur a désactivé l’Teams en affichage seul pour l’organisateur ou pour l’ensemble du client.
- Le participant en affichage seul ne peut pas contourner la salle d’accueil. Par exemple, si l’organisateur d’une  réunion choisit d’éviter la salle d’accueil des seuls membres de mon organisation et qu’un participant extérieur à l’organisation tente de rejoindre la réunion en tant que participant en affichage seul, il ne pourra pas y participer.

Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que de nouveaux participants rejoindront en tant que participants en affichage seul.

  ![Le Teams message du client et de la bannière pour les organisateurs et les présentateurs.](media/chat-and-banner-message.png)

Une fois la capacité de la réunion principale atteinte, les participants sont informés à l’écran de participation préalable qu’ils prennent part en mode lecture seule.

  ![l Teams’écran de pré-participation et le message à l’écran des participants leur disant qu’ils seront rejoints en mode affichage seul.](media/view-only-pre-join-screen.png)

S’il y a de l’espace, l’utilisateur pourra toujours participer à la réunion principale. Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, il y aura encore de la place à la réunion principale. Les participants qui prennent part (ou qui participent à nouveau) à la réunion, participeront à la réunion principale jusqu’à la limite de sa capacité. Les participants à l’expérience en affichage seul ne sont pas automatiquement promus à la réunion principale et ne peuvent pas être promus manuellement à la réunion principale.

Si les rôles de présentateur et de participant ont été définies et qu’un présentateur tente de rejoindre une réunion une fois que la réunion principale a atteint sa capacité, il rejoint la réunion en tant que participant en affichage seul et présente les mêmes limitations que les autres participants en affichage seul. Support pour s’assurer que tous les présentateurs rejoignent la réunion principale sera mise en place ultérieurement. L’organisateur sera toujours garanti dans la réunion principale.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Impact sur les présentateurs et organisateurs de réunion

Les limitations qui s’appliquent aux présentateurs et aux organisateurs de réunion sont les suivantes :

- Vous n’avez aucune information sur le participant en lecture seule. La découverte électronique n’est pas prise en charge pour les participants en lecture seule.
- Les utilisateurs de la réunion principale ne peuvent pas voir les participants en affichage seul.
- Vous ne pouvez pas supprimer un participant en lecture seule de la réunion.

> [!Note]
> Le nombre de participants tient compte uniquement des participants à la réunion principale et non des personnes présentes dans la salle en affichage seul. Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact de personnes qui ont l’expérience lecture seule.

## <a name="experience-for-view-only-attendees"></a>Expérience des participants en lecture seule

L’expérience lecture seule de Teams permet aux participants de :

- Écouter les participants à la réunion principale Teams.
- Consulter le flux vidéo de l’intervenant actif (si l’intervenant  actif partage une vidéo).
- Affichez le contenu partagé à l’aide de la fonctionnalité partager le Bureau ou l’écran.

Le participant en lecture seule ne pourra pas utiliser ces options dans les réunions :

- Participer à la réunion si le participant n’est pas autorisé à contourner la salle d'attente en fonction des stratégies ou options de salle d'attente définies.
- Rejoindre la salle de lecture seule à l’aide de la conférence audio.
- Rejoignez la salle en affichage seul à l’Salles Microsoft Teams cloud ou à l’aide des services Cloud Video Interop (CVI).
- Partager leur contenu audio ou vidéo.
- Consulter ou participer à la conversation de réunion.
- Consulter le flux vidéo des participants à la réunion, sauf si le participant est l’intervenant actif.
- Consultez PowerPoint fichiers partagés à l’aide de la fonctionnalité PowerPoint Live ou des partages d’application individuels (autres que le partage de bureau ou d’écran).
- Le lever la main dans la réunion.
- Envoyer ou voir les réactions.
- Interagissez avec une application 3P intégrée à la réunion Teams, y compris sondages.

## <a name="view-only-feature-limitations"></a>Limitations de la fonctionnalité lecture seule

- Les participants en affichage seul pourront uniquement afficher les sous-titres en direct sur le Bureau et sur le Web. Seuls les sous-titres en anglais sont pris en charge pour l’instant.
- Les participants en affichage seul ne peuvent pas s’inscrire aux webinaires.
- Les participants en lecture seule sont pris en charge par la technologie de diffusion en continu.
- Les participants en lecture seule ne sont pas inclus dans le rapport de participation.
- Les participants en lecture seule ont une expérience vidéo unique. Ils peuvent voir l’intervenant actif ou le contenu partagé, mais pas les deux.
- Pour le moment, les dispositions de la **Galerie**, la **Grade galerie**, ou du **Mode Ensemble** ne sont pas prises en charge pour les participants en lecture seule.
- Les participants en affichage seul sont uniquement pris en charge par les stratégies de salle d’accueil suivantes : « Vous seul , « Personnes dans mon organisation et invités , « Personnes dans mon organisation et organisations de confiance, et invités » et « Tout le monde ». Si vous utilisez une politique de salle d’accueil qui ne prend pas en charge les participants en affichage seul, les participants en affichage seul seront rejetés de la réunion. 
- Les participants en lecture seule n’ont pas la même latence qu’un participant ordinaire. <sup>1</sup>

  <sup>1</sup> participants en lecture seule ont un retard audio et vidéo de 30 secondes pendant la réunion.  
