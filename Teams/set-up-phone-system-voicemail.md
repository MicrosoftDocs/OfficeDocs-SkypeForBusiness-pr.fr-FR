---
title: Configurer la Messagerie vocale cloud
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
description: 'Découvrez comment configurer des Messagerie vocale infonuagique pour vos utilisateurs. '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117062"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="4e03e-103">Configurer la Messagerie vocale cloud</span><span class="sxs-lookup"><span data-stu-id="4e03e-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="4e03e-104">Cet article s’adresse aux administrateurs Microsoft 365 administrateur Office 365, comme décrit dans la page À propos des rôles d’administrateur qui souhaite configurer la fonctionnalité Messagerie vocale infonuagique pour tous les utilisateurs de l’entreprise. [](/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="4e03e-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="4e03e-105">Messagerie vocale infonuagique prend en charge le dépôt de messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.</span><span class="sxs-lookup"><span data-stu-id="4e03e-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e03e-106">Lorsqu’un délégué répond à un appel au nom d’un délégant, les notifications ne sont pas disponibles dans Messagerie vocale infonuagique.</span><span class="sxs-lookup"><span data-stu-id="4e03e-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="4e03e-107">Les utilisateurs peuvent recevoir des notifications pour les appels manqués.</span><span class="sxs-lookup"><span data-stu-id="4e03e-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="4e03e-108">Environnements cloud uniquement : configurer l’Messagerie vocale infonuagique pour les utilisateurs en ligne Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="4e03e-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="4e03e-109">Pour les utilisateurs Système téléphonique Online Messagerie vocale infonuagique est automatiquement installé et mis en service pour les utilisateurs après l’attribution d’une **licence Système téléphonique** aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4e03e-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e03e-110">Pour les Skype Entreprise Système téléphonique ligne avec des numéros de téléphone locaux, vous devrez peut-être activer la messagerie vocale hébergée avec [Set-CsUser -HostedVoicemail $True.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4e03e-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="4e03e-111">Configurer des utilisateurs Messagerie vocale infonuagique boîtes aux Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4e03e-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="4e03e-112">Les informations suivantes ont pour but de configurer des Messagerie vocale infonuagique de manière à ce qu’ils fonctionnent avec les utilisateurs qui utilisent une boîte aux lettres en ligne Système téléphonique dont la boîte aux lettres est Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="4e03e-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="4e03e-113">Les messages vocaux sont remis aux boîtes aux lettres des Exchange via SMTP acheminés via Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="4e03e-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="4e03e-114">Pour permettre la remise de ces messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et vos Exchange Online Protection ; [Utiliser des connecteurs pour configurer l’Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="4e03e-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="4e03e-115">Pour activer les fonctionnalités de messagerie vocale, telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans les clients Skype Entreprise, une connectivité de Microsoft 365 ou Office 365 à la boîte aux lettres de serveur Exchange via les services web Exchange est requise.</span><span class="sxs-lookup"><span data-stu-id="4e03e-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="4e03e-116">Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online, ou exécuter l’Assistant Exchange Hybride à partir d’Exchange 2013 CU5 ou version supérieure.</span><span class="sxs-lookup"><span data-stu-id="4e03e-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="4e03e-117">En outre, vous devez configurer l’intégration et Oauth entre Skype Entreprise Online et le serveur Exchange décrits dans Configurer l’intégration et [oAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Entreprise Online et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="4e03e-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="4e03e-118">Configurer des Messagerie vocale infonuagique pour Skype Entreprise Server utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4e03e-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="4e03e-119">Pour configurer les utilisateurs Skype Entreprise serveur pour Messagerie vocale infonuagique, consultez le service Messagerie vocale infonuagique pour les [utilisateurs locaux.](/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="4e03e-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="4e03e-120">Activation de la messagerie vocale protégée dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="4e03e-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="4e03e-121">Lorsqu’un utilisateur laisse un message vocal pour un utilisateur de votre organisation, ce dernier est remis dans sa boîte aux lettres sous la mesure où il est joint à un message électronique.</span><span class="sxs-lookup"><span data-stu-id="4e03e-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="4e03e-122">En utilisant des règles de flux de courrier pour appliquer le chiffrement des messages, vous pouvez empêcher le courrier d’être transmis à d’autres destinataires.</span><span class="sxs-lookup"><span data-stu-id="4e03e-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="4e03e-123">Lorsque vous activez des messages vocaux protégés, les utilisateurs peuvent écouter les messages vocaux protégés en appelant leur boîte aux lettres vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou dans Outlook pour Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="4e03e-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="4e03e-124">Les messages vocaux protégés ne peuvent pas être ouverts dans des Skype Entreprise ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4e03e-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="4e03e-125">Pour plus d’informations sur le chiffrement des messages, voir [Chiffrement des e-mails.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="4e03e-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="4e03e-126">Pour configurer une messagerie vocale protégée, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="4e03e-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="4e03e-127">Connectez-vous https://admin.microsoft.com à l’aide d’un compte avec des autorisations d’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="4e03e-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="4e03e-128">Sélectionnez **Afficher tout,** puis allez dans centres **d’administration**  >  **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="4e03e-129">Dans le Centre Exchange d’administration, sélectionnez **Règles de flux de**  >  **courrier.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="4e03e-130">Sélectionnez **+** **Ajouter,** puis sélectionnez Appliquer chiffrement de messages Office 365 protection des droits **et des droits aux messages.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="4e03e-131">Donnent un nom à la nouvelle règle de flux de courrier, puis sous Appliquer cette règle si **,** sélectionnez les propriétés du **message** Inclure le type de  >  **message**  >  **Messagerie vocale.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="4e03e-132">Sélectionnez **OK.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-132">Select **OK**.</span></span>
6. <span data-ttu-id="4e03e-133">Sous **Faire ce qui suit,** sélectionnez Appliquer chiffrement de messages Office 365 protection des droits et droits au **message,** puis **sélectionnez-en un.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="4e03e-134">Sous **Modèle RMS,** sélectionnez **Ne pas avancer.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="4e03e-135">Sélectionnez **OK,** puis **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4e03e-136">Si la **liste de modèles RMS** est vide, vous devez configurer le chiffrement des messages.</span><span class="sxs-lookup"><span data-stu-id="4e03e-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="4e03e-137">Pour plus d’informations sur la configuration du chiffrement des messages, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="4e03e-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="4e03e-138">Configurer de nouvelles fonctionnalités de chiffrement de messages</span><span class="sxs-lookup"><span data-stu-id="4e03e-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="4e03e-139">Configuration et gestion des modèles pour Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4e03e-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="4e03e-140">Option Ne pas forwarder pour les e-mails</span><span class="sxs-lookup"><span data-stu-id="4e03e-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="4e03e-141">Configuration des stratégies de messagerie vocale pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4e03e-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="4e03e-142">Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos Skype Entreprise utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4e03e-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="4e03e-143">La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) et [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4e03e-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="4e03e-144">Les messages vocaux reçus par des utilisateurs de votre organisation sont transcrits dans la région d’Microsoft 365 ou Office 365 de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4e03e-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="4e03e-145">La région dans laquelle votre client est hébergé peut ne pas être la même que la région où se trouve l’utilisateur qui reçoit le message vocal.</span><span class="sxs-lookup"><span data-stu-id="4e03e-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="4e03e-146">Pour afficher la région dans laquelle votre client est hébergé, allez sur la [page](https://go.microsoft.com/fwlink/p/?linkid=2067339) de profil de l’organisation, puis cliquez sur Afficher les **détails** en regard de **l’emplacement des données.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e03e-147">Vous ne pouvez pas créer une instance de stratégie pour la transcription ou la transcription avec une erreur de transcription à l’aide de l’cmdlet **New-CsOnlineVoiceMailPolicy,** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="4e03e-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="4e03e-148">Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux.</span><span class="sxs-lookup"><span data-stu-id="4e03e-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="4e03e-149">Pour voir toutes les stratégies de messagerie vocale disponibles, vous pouvez utiliser l’cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4e03e-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="4e03e-150">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4e03e-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="4e03e-151">Étant donné que le paramètre par défaut pour la transcription est pour votre organisation, vous souhaitez peut-être le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4e03e-151">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="4e03e-152">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4e03e-152">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="4e03e-153">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="4e03e-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="4e03e-154">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4e03e-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="4e03e-155">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4e03e-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="4e03e-156">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4e03e-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="4e03e-157">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4e03e-157">Turning off transcription for a user</span></span>

<span data-ttu-id="4e03e-158">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="4e03e-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="4e03e-159">Par exemple, si la transcription de messages vocaux est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="4e03e-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="4e03e-160">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4e03e-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="4e03e-161">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4e03e-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="4e03e-162">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="4e03e-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="4e03e-163">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4e03e-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="4e03e-164">Le service de messagerie vocale Microsoft 365 Office 365 cache les stratégies de messagerie vocale et met à jour le cache toutes les 4 heures.</span><span class="sxs-lookup"><span data-stu-id="4e03e-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="4e03e-165">Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="4e03e-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="4e03e-166">Aider vos utilisateurs à découvrir Teams fonctionnalités de messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="4e03e-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="4e03e-167">Nous vous avons accès aux informations suivantes pour vos utilisateurs sur la gestion de leurs paramètres de messagerie vocale ainsi que sur les autres fonctionnalités d’appel Teams :</span><span class="sxs-lookup"><span data-stu-id="4e03e-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="4e03e-168">[Gérez vos paramètres d’appel dans Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="4e03e-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="4e03e-169">Cet article explique comment gérer toutes les fonctionnalités d’appel Teams utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="4e03e-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="4e03e-170">Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4e03e-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="4e03e-171">Nous vous indions des informations de formation et des articles pour aider vos utilisateurs à se Skype Entreprise messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4e03e-171">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="4e03e-172">Orientez-les vers les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="4e03e-172">Point them to the following articles:</span></span>

- <span data-ttu-id="4e03e-173">Consultez Skype Entreprise messagerie vocale et vos [options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Cet article explique comment écouter vos messages vocaux dans Skype Entreprise, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à des vitesses différentes.</span><span class="sxs-lookup"><span data-stu-id="4e03e-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="4e03e-174">Formation Skype Entreprise 2016</span><span class="sxs-lookup"><span data-stu-id="4e03e-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="4e03e-175">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4e03e-175">Related topics</span></span>
[<span data-ttu-id="4e03e-176">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4e03e-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="4e03e-177">Les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="4e03e-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="4e03e-178">Planifier la migration pour Skype Entreprise Server et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4e03e-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)