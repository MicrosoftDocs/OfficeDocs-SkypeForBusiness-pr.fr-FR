---
title: Configurer la messagerie vocale dans le nuage
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer la messagerie vocale dans le nuage pour vos utilisateurs. '
ms.openlocfilehash: 8219934b8e95962f0e9ea81f4965ad9e5c55fb34
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934771"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="269e8-103">Configurer la messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="269e8-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="269e8-104">Cet article est pour l' [administration d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) souhaite configurer la fonctionnalité de messagerie vocale dans le nuage pour tout le monde dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="269e8-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="269e8-105">Messagerie vocale dans le nuage prend en charge des messages vocaux déposer uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.</span><span class="sxs-lookup"><span data-stu-id="269e8-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="269e8-106">Comme un mécanisme de secours, la messagerie vocale dans le nuage permet de renvoyer des messages à l’aide de SMTP, ce qui signifie que les utilisateurs avec une boîte aux lettres sur un système de messagerie tiers recevront leurs messages vocaux avec aucun temps de fonctionnement du service garanti ou d’autres fonctionnalités de messagerie vocale, telle que la modification leur le message d’accueil et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="269e8-106">As a fallback mechanism, Cloud Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="269e8-107">Environnements en nuage uniquement : configuration de la messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="269e8-107">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="269e8-108">Pour Skype pour les utilisateurs professionnels en ligne et des Plans de l’appel, la messagerie vocale dans le nuage est automatiquement configurée et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="269e8-108">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="269e8-109">Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez peut-être acheter des licences de module complémentaire **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="269e8-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="269e8-110">Vous devrez acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="269e8-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="269e8-111">Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="269e8-111">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="269e8-112">[Affecter ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md)et les licences Exchange Online pour les personnes figurant dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="269e8-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="269e8-113">Ceci fait, elles sont en mesure de recevoir des messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="269e8-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="269e8-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="269e8-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="269e8-116">Système téléphonique avec environnements locaux</span><span class="sxs-lookup"><span data-stu-id="269e8-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="269e8-117">Les informations suivantes sont sur la configuration de la messagerie vocale dans le nuage pour travailler avec les environnements de planifier l’appel local.</span><span class="sxs-lookup"><span data-stu-id="269e8-117">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="269e8-118">Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez peut-être acheter des licences de module complémentaire **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="269e8-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="269e8-119">Vous devez également acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="269e8-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="269e8-120">Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="269e8-120">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="269e8-121">[Affecter ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md)et les licences Exchange Online pour les personnes figurant dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="269e8-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="269e8-122">Suivez les instructions indiquées dans la section **Activer les utilisateurs pour les services de voix et de la messagerie vocale du système téléphonique** du [Configurer de Skype pour édition dans le nuage connecteur guide](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="269e8-122">Follow the instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="269e8-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="269e8-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="269e8-125">Vous pouvez également consulter le [Support technique de la messagerie vocale Azure PBX pour Exchange Server](https://support.microsoft.com/kb/3195158) pour apprendre à configurer la distribution des messages vocaux Azure pour les utilisateurs du Système téléphonique ayant une boîte aux lettres locale.</span><span class="sxs-lookup"><span data-stu-id="269e8-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="269e8-126">Veuillez également lire et suivre les étapes décrites dans le document suivant : [Assistant Configuration hybride](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="269e8-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="269e8-127">Configuration des stratégies de messagerie vocale pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="269e8-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="269e8-128">La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="269e8-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="269e8-129">Vous ne pouvez pas créer une nouvelle instance de stratégie pour la transcription et gratuites transcription masquage à l’aide de l’applet de commande **New-CsOnlineVoiceMailPolicy** , et vous ne pouvez pas supprimer une instance existante de stratégie à l’aide de l’applet de commande **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="269e8-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="269e8-130">Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="269e8-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="269e8-131">Pour afficher toutes les instances de stratégie de messagerie vocale disponibles, vous pouvez utiliser l’applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="269e8-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="269e8-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="269e8-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Fenêtre Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="269e8-134">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="269e8-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="269e8-135">Étant donné que le paramètre par défaut de la transcription est activé pour votre organisation, vous souhaiterez peut-être désactiver à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="269e8-135">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="269e8-136">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="269e8-136">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="269e8-137">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="269e8-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="269e8-138">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="269e8-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="269e8-139">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="269e8-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="269e8-140">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="269e8-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="269e8-141">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="269e8-141">Turning off transcription for a user</span></span>

<span data-ttu-id="269e8-142">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="269e8-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="269e8-143">Par exemple, si la transcription de la messagerie vocale est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="269e8-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="269e8-144">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="269e8-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="269e8-145">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="269e8-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="269e8-146">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="269e8-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="269e8-147">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="269e8-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="269e8-p111">Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="269e8-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="269e8-150">Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="269e8-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="269e8-151">Nous disposons d’informations sur la formation et des articles pour aider vos utilisateurs à vendre Skype pour la messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="269e8-151">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="269e8-152">Orientez-les vers les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="269e8-152">Point them to the following articles:</span></span>

- <span data-ttu-id="269e8-153">[Vérifier les Skype pour les options et de la messagerie vocale d’entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter vos messages vocaux dans Skype pour les entreprises, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à différentes vitesses.</span><span class="sxs-lookup"><span data-stu-id="269e8-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="269e8-154">Formation Skype Entreprise 2016</span><span class="sxs-lookup"><span data-stu-id="269e8-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="269e8-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="269e8-155">Related topics</span></span>
[<span data-ttu-id="269e8-156">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="269e8-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="269e8-157">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="269e8-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


