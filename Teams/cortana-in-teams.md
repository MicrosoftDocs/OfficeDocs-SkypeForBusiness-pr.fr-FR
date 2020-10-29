---
title: Aide vocale de Cortana dans Microsoft teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrir comment utiliser l’aide vocale de Cortana avec teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785388"
---
# <a name="cortana-voice-assistance-in-teams"></a>Aide vocale de Cortana dans teams

> [!Note]
> L’aide vocale de Cortana est prise en charge dans les applications mobiles iOS et Android de Microsoft Teams, et sur les écrans de Microsoft Teams, uniquement pour les utilisateurs aux États-Unis. Ce service n’est actuellement pas disponible pour les clients GCC et GCC-High, DoD, EDU. L’élargissement vers des langues et régions supplémentaires interviendront dans le cadre des versions ultérieures.

L’aide vocale de Cortana dans l’application mobile teams et sur les appareils d’affichage de Microsoft teams permet aux utilisateurs de Microsoft 365 entreprise de rationaliser les tâches liées aux communications, à la collaboration et aux réunions en langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du micro situé dans le coin supérieur droit de l’application mobile teams ou en disant &#8220;Cortana&#8221; dans l’affichage de Microsoft Teams. Pour communiquer rapidement avec son équipe mains libres et Pendant que vous êtes en ligne, les utilisateurs peuvent prononcer des requêtes telles que &#8220;appeler Megan&#8221; ou &#8220;envoyer un message à ma prochaine réunion&#8221;. Les utilisateurs peuvent également participer à des réunions en disant &#8220;participer à ma prochaine réunion&#8221; et utiliser l’aide vocale pour partager des fichiers, consulter leur calendrier, etc. Ces expériences d’assistance vocale sont distribuées à l’aide des [services Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) à l’échelle de l’entreprise qui respectent pleinement les engagements relatifs à la confidentialité, la sécurité et la conformité d’Office 365, tels qu’ils sont énoncés dans les [conditions de services en ligne (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

L’image montre l’envoi d’une discussion avec Cortana sur un appareil mobile.

![Image illustrant une séquence d’écrans mobiles montrant une session de conversation Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations d’administration

Le service d’aide vocale de Cortana dans teams est fourni à l’aide de services qui respectent pleinement les engagements en matière de confidentialité, de sécurité et de conformité d’Office 365 dans le cadre des conditions d’utilisation des services en ligne (OST). Par défaut, la fonctionnalité est activée pour les clients.

Les administrateurs de clients peuvent contrôler qui, au sein de leur client, peuvent utiliser l’aide vocale de Cortana dans teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie peut être définie au niveau du compte d’utilisateur ou du client. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode dans ce contrôle de stratégie pour déterminer si Cortana est désactivée, activée avec un appel de bouton de transmission uniquement, ou à l’aide de la fonctionnalité de mise en éveil de Word (en ce qui concerne les appareils qui la prennent en charge, tels que l’affichage de Microsoft Teams).

Les administrateurs peuvent utiliser les applets de commande PowerShell suivantes pour gérer cette stratégie (la stratégie n’est pas disponible actuellement dans le centre d’administration Microsoft Teams).

- [Nouveau-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie portant le nom &#8220;EmployeeCortanaPolicy&#8221; l’endroit où l’aide vocale Cortana dans Microsoft teams est désactivée.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple illustre la mise à jour d’une stratégie existante portant le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft teams avec l’appel de bouton de déplacement uniquement. Les utilisateurs peuvent appeler Cortana en sélectionnant le bouton micro de Cortana dans Teams. Mettre en éveil Word (&#8220;Hey Cortana&#8221; ou &#8220;l’appel de Cortana&#8221;) sera désactivé.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple illustre la mise à jour de la stratégie et l’activation de l’assistance vocale de Cortana avec les boutons bascule et l’appel de mise en éveil de Word.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> Au moment de la publication initiale pour les utilisateurs de Microsoft 365 entreprise aux États-Unis en anglais, l’application mobile Teams ne prend pas en charge l’activation en éveil de Word, mais elle sera prise en charge à l’avenir. La mise en éveil de Word est activée sur les appareils d’affichage de Microsoft teams à la version initiale.

## <a name="user-control"></a>Contrôle utilisateur

Les utilisateurs individuels peuvent essayer l’assistance vocale de Cortana dans l’application mobile teams en sélectionnant le bouton microphone. Pour tester l’aide vocale de Cortana sur les appareils Microsoft Teams, il suffit de savoir &#8220;Cortana. &#8221; ils peuvent également contrôler si Cortana est activée dans teams à l’aide d’un paramètre dans l’application mobile teams ou dans l’affichage Microsoft Teams.

1. Ouvrez l’application mobile teams ou accédez à l’écran ambiant (accueil) de l’affichage de Microsoft Teams.

2. Dans l’application mobile Teams, accédez à **paramètres** . Dans l’affichage de Microsoft Teams, sélectionnez l’avatar de l’utilisateur, puis sélectionnez Paramètres. Si Cortana est activée, par exemple, &#8220;Cortana, accédez à paramètres. &#8221;

3. Sélectionnez **Cortana** .

4. Positionnez le bouton bascule sur **activé** ou **désactivé** , selon que vous souhaitez ou non l’assistance vocale de Cortana sur l’appareil.
