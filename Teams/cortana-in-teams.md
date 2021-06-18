---
title: Assistance vocale Cortana dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrez comment utiliser l’assistance vocale Cortana avec Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118473"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistance vocale Cortana dans Teams

> [!Note]
> L’assistance vocale Cortana est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android, dans les salles Microsoft Teams sur Windows et dans les écrans de Microsoft Teams, uniquement pour les utilisateurs aux États-Unis. Elle n’est actuellement pas disponible pour les clients GCC, GCC-High, DoD, EDU. Une extension vers d’autres langues et régions sera mise en place dans le cadre des prochaines publication.

> [!Note]
> L’assistance vocale Cortana dans les salles Microsoft Teams est disponible sous Aperçu. Dans sa version d’aperçu, Cortana est prise en charge uniquement aux États-Unis avec la langue EN-US sur les appareils qui ont connecté des micros Microphones Microphones.

L’assistance vocale Cortana dans l’application mobile Teams, dans les salles Microsoft Teams sur Windows et sur les périphériques d’affichage de Microsoft Teams permet aux utilisateurs de Microsoft 365 Entreprise de simplifier la communication, la collaboration et les tâches liées aux réunions à l’aide d’un langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant &#8220;Cortana&#8221; dans la salle Microsoft Teams ou lors de l’utilisation d’un affichage de Microsoft Teams. Pour communiquer rapidement avec leur équipe en mains libres et en cours, les utilisateurs peuvent dire des requêtes telles que &#8220;appeler Megan&#8221; ou &#8220;envoyer un message à mon prochain&#8221;. Les utilisateurs peuvent également participer à des réunions en &#8220;participer à ma prochaine&#8221; réunion et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier et bien plus encore. Ces expériences d’assistance vocale sont tenues à l’aide de services de qualité professionnelle [de Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité d’Office 365, comme le reflètent les conditions des services en ligne [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

L’image illustre l’envoi d’une conversation à l’aide de Cortana sur un appareil mobile.

![Séquence d’écrans mobiles affichant une session de conversation Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations de l’administrateur

L’assistance vocale Cortana dans Teams est disponible à l’aide de services qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité au niveau d’Office 365, comme indiqué dans les conditions des services en ligne (OST). La fonctionnalité sera activée par défaut pour les locataires.

Les administrateurs des locataires peuvent contrôler qui dans leur client peut utiliser l’assistance vocale Cortana dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie peut être définie au niveau du compte d’utilisateur ou du client. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode dans ce contrôle de stratégie pour déterminer si Cortana est désactivée, activée avec l’appel du bouton d’appel uniquement ou avec l’appel du mot de sortie (applicable aux appareils qui le supportent, comme l’affichage de Microsoft Teams).

Les administrateurs peuvent utiliser les cmdlets PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans le Centre d’administration Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie avec le nom &#8220;EmployeeCortanaPolicy&#8221; où l’assistance vocale Cortana dans Microsoft Teams est désactivée.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple illustre la mise à jour d’une stratégie existante avec le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec appel du bouton d’appel uniquement. Les utilisateurs pourront appeler Cortana en sélectionnant le bouton du micro de Cortana dans Teams. Le mot de veille (&#8220;Hey Cortana&#8221; ou &#8220;Cortana&#8221;) est désactivé.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple illustre la mise à jour de la stratégie et l’activation de l’assistance vocale Cortana avec le bouton Push et l’appel de word de veille.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

À l’heure de la publication initiale pour les utilisateurs de Microsoft 365 Entreprise aux États-Unis en anglais, les fonctions suivantes sont disponibles :

- L’application mobile Teams ne prendra pas en charge l’activation de word de veille, mais elle sera prise en charge à l’avenir.  

- Les salles Microsoft Teams sur les appareils d’affichage Windows et Microsoft Teams 365 365 365 365 365 365 365 365 36

## <a name="user-control"></a>Contrôle de l’utilisateur

Les utilisateurs individuels peuvent essayer l’assistance vocale Cortana sur différents appareils :

- Sélectionnez le bouton microphone dans l’application mobile Teams.

- Sélectionnez le bouton du microphone ou dites « Cortana » dans les salles Microsoft Teams.

- Dites « Cortana » sur les appareils d’affichage de Microsoft Teams.

Vous pouvez déterminer si Cortana dans Teams est activée pour votre appareil à l’aide d’un paramètre de l’appareil.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Application mobile Teams ou affichage de Microsoft Teams

  1. Ouvrez l’application mobile Teams.

  2. Sélectionnez **Paramètres**  >  **Cortana.**

  3. Déplacez le **basculement sur Ou** **Hors.**

### <a name="microsoft-teams-display"></a>Affichage de Microsoft Teams

  1. Allez à l’écran ambiant (accueil) de l’affichage de Microsoft Teams.

  2. Sélectionnez l’avatar utilisateur, puis **Paramètres.** Si Cortana est activée, dites : « Cortana, accéder aux paramètres ».

  3. Déplacez le **basculement sur Ou** **Hors.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salles Microsoft Teams sur Windows

Les modifications au niveau de l’appareil sont disponibles si Cortana est activée au niveau du client. Cortana sera publiée par défaut.

Pour activer Cortana au niveau de l’appareil, ces attributs XML doivent être ajoutés au fichier XML SkypeSettings :

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Apporter des modifications au niveau de la réunion est disponible si Cortana est activée au niveau de l’appareil.

Pour activer l’assistance vocale Cortana pendant une réunion, activez ou désactivez **le** **paramètre.** Une fois la réunion terminée, Cortana revient au paramètre au niveau de l’appareil.