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
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910056"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="a855d-103">Configuration des stratégies de messagerie vocale pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a855d-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="a855d-104">Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos Skype Entreprise utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a855d-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="a855d-105">Paramètres par défaut de l’organisation de messagerie vocale pour tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a855d-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="a855d-106">La transcription de messages vocaux est activée.</span><span class="sxs-lookup"><span data-stu-id="a855d-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="a855d-107">Le masquage de la transcription de messages vocaux est désactivé.</span><span class="sxs-lookup"><span data-stu-id="a855d-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="a855d-108">La durée maximale de l’enregistrement est définie sur cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="a855d-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="a855d-109">Vous pouvez contrôler ces valeurs par défaut à l’aide des cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) et [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="a855d-110">Les messages vocaux reçus par des utilisateurs de votre organisation sont transcrits dans la région d’Microsoft 365 ou Office 365 de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a855d-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="a855d-111">La région dans laquelle votre client est hébergé peut ne pas être la même que la région où se trouve l’utilisateur qui reçoit le message vocal.</span><span class="sxs-lookup"><span data-stu-id="a855d-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="a855d-112">Pour afficher la région dans laquelle votre client est hébergé, allez sur la [page](https://go.microsoft.com/fwlink/p/?linkid=2067339) de profil de l’organisation, puis cliquez sur Afficher les **détails** en regard de **l’emplacement des données.**</span><span class="sxs-lookup"><span data-stu-id="a855d-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a855d-113">Vous ne pouvez pas créer une instance de stratégie pour la transcription ou la transcription avec une erreur de transcription à l’aide de l’cmdlet **New-CsOnlineVoiceMailPolicy,** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a855d-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="a855d-114">Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="a855d-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="a855d-115">Pour voir toutes les stratégies de messagerie vocale disponibles, vous pouvez utiliser l’cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="a855d-116">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a855d-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="a855d-117">Étant donné que le paramètre par défaut pour la transcription est pour votre organisation, vous souhaitez peut-être le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a855d-118">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="a855d-119">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a855d-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="a855d-120">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a855d-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="a855d-121">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="a855d-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a855d-122">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="a855d-123">Modification de la durée d’enregistrement pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a855d-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="a855d-124">La durée maximale d’enregistrement est définie par défaut sur cinq minutes pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a855d-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="a855d-125">Si l’entreprise a besoin d’augmenter ou de diminuer la durée maximale d’enregistrement, vous pouvez le faire à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a855d-126">Par exemple, pour définir la durée maximale d’enregistrement à 60 secondes, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="a855d-127">Invites système en deux langues pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a855d-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="a855d-128">Par défaut, les invites du système de messagerie vocale sont présentées aux appelants dans la langue sélectionnée par l’utilisateur lors de la configuration de leur messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="a855d-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="a855d-129">Si l’entreprise a besoin que les invites du système de messagerie vocale soient présentées dans deux langues, vous pouvez le faire à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="a855d-130">Une langue principale et une langue secondaire doivent être définies et peuvent ne pas être identiques.</span><span class="sxs-lookup"><span data-stu-id="a855d-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="a855d-131">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="a855d-132">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a855d-132">Turning off transcription for a user</span></span>

<span data-ttu-id="a855d-133">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="a855d-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="a855d-134">Par exemple, si la transcription de messages vocaux est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="a855d-135">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="a855d-136">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a855d-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="a855d-137">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="a855d-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="a855d-138">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="a855d-139">Modification de la durée d’enregistrement d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a855d-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="a855d-140">Vous devez tout d’abord créer une stratégie de messagerie vocale personnalisée à l’aide de l’cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="a855d-141">La commande ci-dessous crée une stratégie de messagerie vocale en ligne par utilisateur avec MaximumRecordingLength définie sur 60 secondes et d’autres champs définies sur la valeur globale au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="a855d-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="a855d-142">Pour affecter cette stratégie personnalisée à un utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="a855d-143">Invites système en deux langues pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a855d-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="a855d-144">Vous devez tout d’abord créer une stratégie de messagerie vocale personnalisée à l’aide de l’cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="a855d-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="a855d-145">La commande ci-dessous crée une stratégie de messagerie vocale en ligne per-user enUS-esSP-VoicemailPolicy avec PrimarySystemPromptLanguage set to en-US (English - United States) et le SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span><span class="sxs-lookup"><span data-stu-id="a855d-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="a855d-146">Pour affecter cette stratégie personnalisée à un utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a855d-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="a855d-147">La Get-CsOnlineVoicemailPolicy cmdlet ne retourne pas actuellement les valeurs de PrimarySystemPromptLanguage et SecondarySystemPromptLanguage.</span><span class="sxs-lookup"><span data-stu-id="a855d-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="a855d-148">Pour que ces valeurs modifient la commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="a855d-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="a855d-149">Remplacez **PolicyName** par le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a855d-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a855d-150">Le service de messagerie vocale Microsoft 365 et Office 365 cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures.</span><span class="sxs-lookup"><span data-stu-id="a855d-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="a855d-151">Ainsi, jusqu’à 6 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="a855d-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
