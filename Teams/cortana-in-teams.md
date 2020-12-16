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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686440"
---
# <a name="cortana-voice-assistance-in-teams"></a>Aide vocale de Cortana dans teams

> [!Note]
> L’aide vocale de Cortana est prise en charge dans les applications mobiles iOS et Android de Microsoft Teams, les salles Microsoft teams sous Windows et sur les écrans de Microsoft Teams, uniquement pour les utilisateurs aux États-Unis. Ce service n’est actuellement pas disponible pour les clients GCC et GCC-High, DoD, EDU. L’élargissement vers des langues et régions supplémentaires interviendront dans le cadre des versions ultérieures.

> [!Note]
> L’assistance vocale de Cortana dans les salles de Microsoft teams est publiée sous aperçu. Dans sa version préliminaire, Cortana est uniquement prise en charge aux États-Unis avec une langue en-US sur les appareils dotés de micros bénéficient connectés.

L’assistance vocale de Cortana dans l’application mobile Teams, sur les salles de Microsoft teams sous Windows et sur les appareils d’affichage de Microsoft teams permet aux utilisateurs de Microsoft 365 entreprise de rationaliser les tâches de communication, de collaboration et de réunion en utilisant le langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du micro situé dans le coin supérieur droit de l’application mobile teams ou en disant &#8220;Cortana&#8221; dans la salle Microsoft teams ou lors de l’utilisation de Microsoft Teams. Pour communiquer rapidement avec son équipe mains libres et Pendant que vous êtes en ligne, les utilisateurs peuvent prononcer des requêtes telles que &#8220;appeler Megan&#8221; ou &#8220;envoyer un message à ma prochaine réunion&#8221;. Les utilisateurs peuvent également participer à des réunions en disant &#8220;participer à ma prochaine réunion&#8221; et utiliser l’aide vocale pour partager des fichiers, consulter leur calendrier, etc. Ces expériences d’assistance vocale sont distribuées à l’aide des [services Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) à l’échelle de l’entreprise qui respectent pleinement les engagements relatifs à la confidentialité, la sécurité et la conformité d’Office 365, tels qu’ils sont énoncés dans les [conditions de services en ligne (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

L’image montre l’envoi d’une discussion avec Cortana sur un appareil mobile.

![séquence d’écrans mobiles montrant une session de conversation Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations d’administration

Le service d’aide vocale de Cortana dans teams est fourni à l’aide de services qui respectent pleinement les engagements en matière de confidentialité, de sécurité et de conformité d’Office 365 dans le cadre des conditions d’utilisation des services en ligne (OST). Par défaut, la fonctionnalité est activée pour les clients.

Les administrateurs de clients peuvent contrôler qui, au sein de leur client, peuvent utiliser l’aide vocale de Cortana dans teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie peut être définie au niveau du compte d’utilisateur ou du client. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode dans ce contrôle de stratégie pour déterminer si Cortana est désactivée, activée avec un appel de bouton bascule uniquement, ou avec la mise en éveil par appel de Word (en ce qui concerne les appareils qui la prennent en charge, tels que l’affichage de Microsoft Teams).

Les administrateurs peuvent utiliser les applets de commande PowerShell suivantes pour gérer cette stratégie (la stratégie n’est pas disponible actuellement dans le centre d’administration Microsoft Teams).

- [Nouveau-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

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

À la fois, de la version initiale pour les utilisateurs de Microsoft 365 entreprise aux États-Unis en anglais, les fonctions suivantes sont disponibles :

- L’application mobile Teams ne prend pas en charge l’activation en sortie automatique de Word.  

- Les salles de Microsoft teams sur Windows et Microsoft teams Display sont prises en charge par l’activation en éveil.

## <a name="user-control"></a>Contrôle utilisateur

Les utilisateurs individuels peuvent utiliser l’aide vocale de Cortana sur différents appareils :

- Sélectionnez le bouton microphone dans l’application mobile Teams.

- Sélectionnez le bouton microphone ou prononcez « Cortana » dans les salles de Microsoft Teams.

- Dites « Cortana » sur les périphériques d’affichage de Microsoft Teams.

Vous pouvez contrôler l’activation de Cortana dans teams pour votre appareil en utilisant un paramètre de l’appareil.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Application mobile teams ou affichage de Microsoft teams

  1. Ouvrez l’application mobile Teams.

  2. Sélectionnez **paramètres**  >  **Cortana**.

  3. Activez **ou** **désactivez** le bouton bascule.

### <a name="microsoft-teams-display"></a>Affichage de Microsoft teams

  1. Accédez à l’écran ambiant (accueil) de l’affichage de Microsoft Teams.

  2. Sélectionnez l’avatar de l’utilisateur, puis sélectionnez **paramètres**. Si Cortana est activée, dites « Cortana, accédez aux paramètres ».

  3. Activez **ou** **désactivez** le bouton bascule.
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft teams sur Windows

L’apport de modifications au niveau de l’appareil est disponible si Cortana est activée au niveau du client. Cortana sera annulée par défaut.

Pour activer Cortana au niveau de l’appareil, les attributs XML suivants doivent être ajoutés dans le fichier XML SkypeSettings :

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Le fait de modifier le niveau de la réunion est disponible si Cortana est activé au niveau de l’appareil.

Pour activer l’aide vocale de Cortana **lors d’une** réunion, activez ou **désactivez** le bouton bascule. Une fois la réunion terminée, Cortana revient aux paramètres de niveau appareil définis.
