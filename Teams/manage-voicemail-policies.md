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
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="4b16c-103">Configuration des stratégies de messagerie vocale pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4b16c-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="4b16c-104">Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos Skype Entreprise utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b16c-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="4b16c-105">La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) et [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4b16c-105">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="4b16c-106">Les messages vocaux reçus par des utilisateurs de votre organisation sont transcrits dans la région d’Microsoft 365 ou Office 365 de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b16c-106">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="4b16c-107">La région dans laquelle votre client est hébergé peut ne pas être la même que la région où se trouve l’utilisateur qui reçoit le message vocal.</span><span class="sxs-lookup"><span data-stu-id="4b16c-107">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="4b16c-108">Pour afficher la région dans laquelle votre client est hébergé, allez sur la [page](https://go.microsoft.com/fwlink/p/?linkid=2067339) de profil de l’organisation, puis cliquez sur Afficher les **détails** en regard de **l’emplacement des données.**</span><span class="sxs-lookup"><span data-stu-id="4b16c-108">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b16c-109">Vous ne pouvez pas créer une instance de stratégie pour la transcription ou la transcription avec une erreur de transcription à l’aide de l’cmdlet **New-CsOnlineVoiceMailPolicy,** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="4b16c-109">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="4b16c-110">Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="4b16c-110">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="4b16c-111">Pour voir toutes les stratégies de messagerie vocale disponibles, vous pouvez utiliser l’cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4b16c-111">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="4b16c-112">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4b16c-112">Turning off transcription for your organization</span></span>

<span data-ttu-id="4b16c-113">Étant donné que le paramètre par défaut pour la transcription est pour votre organisation, vous souhaitez peut-être le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4b16c-113">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="4b16c-114">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4b16c-114">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="4b16c-115">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4b16c-115">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="4b16c-116">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b16c-116">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="4b16c-117">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4b16c-117">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="4b16c-118">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4b16c-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="4b16c-119">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b16c-119">Turning off transcription for a user</span></span>

<span data-ttu-id="4b16c-120">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b16c-120">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="4b16c-121">Par exemple, si la transcription de messages vocaux est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4b16c-121">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="4b16c-122">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4b16c-122">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="4b16c-123">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b16c-123">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="4b16c-124">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4b16c-124">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="4b16c-125">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4b16c-125">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="4b16c-126">Le service de messagerie vocale Microsoft 365 et Office 365 cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures.</span><span class="sxs-lookup"><span data-stu-id="4b16c-126">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="4b16c-127">Ainsi, jusqu’à 6 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="4b16c-127">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
