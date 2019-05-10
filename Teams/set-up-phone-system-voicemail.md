---
title: Configuration Messagerie vocale Cloud
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
ms.openlocfilehash: a4d992ac4f42dca1bffe7a4c3d7ae01400b8e635
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865005"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="de73e-103">Configuration Messagerie vocale Cloud</span><span class="sxs-lookup"><span data-stu-id="de73e-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="de73e-104">Cet article est pour l' [administration d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) souhaite configurer la fonctionnalité de messagerie vocale dans le nuage pour tout le monde dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="de73e-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="de73e-105">Messagerie vocale dans le nuage prend en charge des messages vocaux déposer uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.</span><span class="sxs-lookup"><span data-stu-id="de73e-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="de73e-106">Environnements en nuage uniquement : configuration de la messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="de73e-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="de73e-107">Pour Skype pour les utilisateurs professionnels en ligne et des Plans de l’appel, la messagerie vocale dans le nuage est automatiquement configurée et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="de73e-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="de73e-108">Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez peut-être acheter des licences de module complémentaire **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="de73e-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="de73e-109">Vous devrez acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="de73e-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="de73e-110">Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="de73e-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="de73e-111">[Affecter ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md)et les licences Exchange Online pour les personnes figurant dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="de73e-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="de73e-112">Ceci fait, elles sont en mesure de recevoir des messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="de73e-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="de73e-113">Prise en charge de la transcription de la messagerie vocale a été ajouté à compter de mars 2017 et est activée par défaut pour toutes les organisations et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de73e-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="de73e-114">Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="de73e-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="de73e-115">Système téléphonique avec environnements locaux</span><span class="sxs-lookup"><span data-stu-id="de73e-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="de73e-116">Les informations suivantes sont sur la configuration de la messagerie vocale dans le nuage pour travailler avec les environnements de planifier l’appel local.</span><span class="sxs-lookup"><span data-stu-id="de73e-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="de73e-117">Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez peut-être acheter des licences de module complémentaire **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="de73e-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="de73e-118">Vous devez également acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="de73e-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="de73e-119">Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="de73e-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="de73e-120">[Affecter ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md)et les licences Exchange Online pour les personnes figurant dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="de73e-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="de73e-121">Suivez les instructions correspondant à PSTN local appelant solution déployée pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de73e-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="de73e-122">Pour le nuage connecteur Edition, suivez les instructions dans la section **Activer les utilisateurs pour les services de voix et de la messagerie vocale du système téléphonique** du [Configurer de Skype pour édition dans le nuage connecteur guide](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="de73e-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="de73e-123">Pour PSTN d’appel avec Skype pour Business Server, suivez [activez les utilisateurs pour Enterprise Voice sur site](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="de73e-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="de73e-124">Pour le routage Direct équipes, suivez la section **Activer enterprise voice et configurer le numéro de téléphone et messagerie vocale** de [Configurer le routage Direct](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="de73e-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="de73e-125">Prise en charge de la transcription de la messagerie vocale a été ajouté à compter de mars 2017 et est activée par défaut pour toutes les organisations et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de73e-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="de73e-126">Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="de73e-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="de73e-127">Messages de messagerie vocale sont remis à la boîte aux lettres d’utilisateurs Exchange via SMTP acheminé via Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="de73e-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="de73e-128">Pour activer une remise réussie de ces messages, n’oubliez pas que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et les Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="de73e-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="de73e-129">[Connecteurs utilisés pour configurer le flux de messagerie](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="de73e-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="de73e-130">Pour activer des fonctionnalités telles que la personnalisation des messages d’accueil et de la messagerie vocale visual dans Skype pour les clients d’entreprise de la messagerie vocale, la connectivité à partir d’Office 365 à la boîte aux lettres du serveur Exchange via les Services Web Exchange est requise.</span><span class="sxs-lookup"><span data-stu-id="de73e-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="de73e-131">Pour activer cette connectivité, vous devez configurer la nouvelle Oauth Exchange décrivent du protocole d’authentification [OAuth configurer](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) l’authentification entre des organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de73e-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="de73e-132">L’Assistant hybride d’Exchange exécutées à partir d’Exchange 2013 CU5 ou supérieures gère automatiquement la configuration requise dans les étapes 5 et 6.</span><span class="sxs-lookup"><span data-stu-id="de73e-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="de73e-133">Configuration des stratégies de messagerie vocale pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="de73e-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="de73e-134">Pour Skype pour les entreprises, la désactivation de la messagerie vocale via un Teams Microsoft appelant stratégie peut-être également désactiver le service de messagerie vocale pour votre Skype pour les utilisateurs professionnels.</span><span class="sxs-lookup"><span data-stu-id="de73e-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="de73e-135">La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="de73e-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de73e-136">Vous ne pouvez pas créer une nouvelle instance de stratégie pour la transcription et gratuites transcription masquage à l’aide de l’applet de commande **New-CsOnlineVoiceMailPolicy** , et vous ne pouvez pas supprimer une instance existante de stratégie à l’aide de l’applet de commande **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="de73e-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="de73e-137">Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="de73e-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="de73e-138">Pour afficher toutes les instances de stratégie de messagerie vocale disponibles, vous pouvez utiliser l’applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="de73e-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="de73e-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="de73e-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Fenêtre Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="de73e-141">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="de73e-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="de73e-142">Étant donné que le paramètre par défaut de la transcription est activé pour votre organisation, vous souhaiterez peut-être désactiver à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="de73e-142">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="de73e-143">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="de73e-143">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="de73e-144">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="de73e-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="de73e-145">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="de73e-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="de73e-146">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="de73e-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="de73e-147">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="de73e-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="de73e-148">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="de73e-148">Turning off transcription for a user</span></span>

<span data-ttu-id="de73e-149">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="de73e-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="de73e-150">Par exemple, si la transcription de la messagerie vocale est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="de73e-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="de73e-151">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="de73e-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="de73e-152">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="de73e-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="de73e-153">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="de73e-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="de73e-154">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="de73e-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="de73e-p113">Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="de73e-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="de73e-157">Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="de73e-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="de73e-158">Nous disposons d’informations sur la formation et des articles pour aider vos utilisateurs à vendre Skype pour la messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="de73e-158">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="de73e-159">Orientez-les vers les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="de73e-159">Point them to the following articles:</span></span>

- <span data-ttu-id="de73e-160">[Vérifier les Skype pour les options et de la messagerie vocale d’entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter vos messages vocaux dans Skype pour les entreprises, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à différentes vitesses.</span><span class="sxs-lookup"><span data-stu-id="de73e-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="de73e-161">Formation Skype Entreprise 2016</span><span class="sxs-lookup"><span data-stu-id="de73e-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="de73e-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de73e-162">Related topics</span></span>
[<span data-ttu-id="de73e-163">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="de73e-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="de73e-164">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="de73e-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="de73e-165">Planifier la migration pour Skype Entreprise Server et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="de73e-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


