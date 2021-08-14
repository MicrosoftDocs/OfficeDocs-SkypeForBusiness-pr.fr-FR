---
title: Gérer les stratégies de messagerie vocale
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gérer les stratégies de messagerie vocale pour vos utilisateurs.
ms.openlocfilehash: 112a2ac98ee22c46cb78c579ead947f70a1d6d447ac81ace3aef224304a281dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342968"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos Skype Entreprise utilisateurs.

## <a name="voicemail-organization-defaults-for-all-users"></a>Paramètres par défaut de l’organisation de messagerie vocale pour tous les utilisateurs
- La transcription de messages vocaux est activée.
- Le masquage de la transcription de messages vocaux est désactivé.
- La durée maximale de l’enregistrement est définie sur cinq minutes.

Vous pouvez contrôler ces valeurs par défaut à l’aide des cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) et [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

Les messages vocaux reçus par des utilisateurs de votre organisation sont transcrits dans la région d’Microsoft 365 ou Office 365 de votre organisation. La région dans laquelle votre client est hébergé peut ne pas être la même que la région où se trouve l’utilisateur qui reçoit le message vocal. Pour afficher la région dans laquelle votre client est hébergé, allez sur la [page](https://go.microsoft.com/fwlink/p/?linkid=2067339) de profil de l’organisation, puis cliquez sur Afficher les **détails** en regard de **l’emplacement des données.**

> [!IMPORTANT]
> Vous ne pouvez pas créer une instance de stratégie pour la transcription ou la transcription avec une erreur de transcription à l’aide de l’cmdlet **New-CsOnlineVoiceMailPolicy,** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour voir toutes les stratégies de messagerie vocale disponibles, vous pouvez utiliser l’cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Étant donné que le paramètre par défaut pour la transcription est pour votre organisation, vous souhaitez peut-être le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Pour ce faire, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Pour ce faire, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>Modification de la durée d’enregistrement pour votre organisation

La durée maximale d’enregistrement est définie par défaut sur cinq minutes pour votre organisation. Si l’entreprise a besoin d’augmenter ou de diminuer la durée maximale d’enregistrement, vous pouvez le faire à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Par exemple, pour définir la durée maximale d’enregistrement à 60 secondes, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>Invites système en deux langues pour votre organisation

Par défaut, les invites du système de messagerie vocale sont présentées aux appelants dans la langue sélectionnée par l’utilisateur lors de la configuration de leur messagerie vocale. Si l’entreprise a besoin que les invites du système de messagerie vocale soient présentées dans deux langues, vous pouvez le faire à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Une langue principale et une langue secondaire doivent être définies et peuvent ne pas être identiques. Pour ce faire, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de messages vocaux est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)

Pour désactiver la transcription pour un utilisateur unique, exécutez :

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activer le masquage de transcription pour un utilisateur

Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).

Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>Modification de la durée d’enregistrement d’un utilisateur

Vous devez tout d’abord créer une stratégie de messagerie vocale personnalisée à l’aide de l’cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) La commande ci-dessous crée une stratégie de messagerie vocale en ligne par utilisateur avec MaximumRecordingLength définie sur 60 secondes et d’autres champs définies sur la valeur globale au niveau du client.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

Pour affecter cette stratégie personnalisée à un utilisateur, exécutez : 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>Invites système en deux langues pour un utilisateur

Vous devez tout d’abord créer une stratégie de messagerie vocale personnalisée à l’aide de l’cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) La commande ci-dessous crée une stratégie de messagerie vocale en ligne per-user enUS-esSP-VoicemailPolicy avec PrimarySystemPromptLanguage set to en-US (English - United States) et le SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

Pour affecter cette stratégie personnalisée à un utilisateur, exécutez : 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> La Get-CsOnlineVoicemailPolicy cmdlet ne retourne pas actuellement les valeurs de PrimarySystemPromptLanguage et SecondarySystemPromptLanguage. Pour que ces valeurs modifient la commande comme suit :
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> Remplacez **PolicyName** par le nom de la stratégie.


> [!IMPORTANT]
> Le service de messagerie vocale Microsoft 365 et Office 365 cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures. Ainsi, jusqu’à 6 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.
