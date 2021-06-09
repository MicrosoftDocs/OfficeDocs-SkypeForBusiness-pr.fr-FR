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
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796899"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos Skype Entreprise utilisateurs.

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) et [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).

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

> [!IMPORTANT]
> Le service de messagerie vocale Microsoft 365 et Office 365 cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures. Ainsi, jusqu’à 6 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.
