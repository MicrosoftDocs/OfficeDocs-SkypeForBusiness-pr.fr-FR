---
title: Installer la messagerie vocale du Système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer la messagerie vocale du système téléphonique (Cloud PBX) pour vos utilisateurs Skype Entreprise. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252888"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="e221b-103">Installer la messagerie vocale du Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="e221b-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="e221b-104">Cet article est pour l' [administrateur Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) qui souhaite installer la fonction de messagerie vocale du Système téléphonique pour tous les membres de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e221b-104">This article is for the [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up Skype for Business Cloud PBX voicemail for everyone in their business.</span></span>

> [!NOTE]
> <span data-ttu-id="e221b-105">La messagerie vocale du Système téléphonique prend en charge le dépôt des messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend aucun système de messagerie électronique tiers en charge.</span><span class="sxs-lookup"><span data-stu-id="e221b-105">Cloud PBX voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="e221b-106">Comme solution de secours, la messagerie vocale du Système téléphonique peut renvoyer les messages à l'aide du protocole SMTP, en d'autres termes, les utilisateurs disposant d'une boîte aux lettres issue d'un système de messagerie électronique tiers recevront leurs messages vocaux sans garantie d'activité du service ou de toute autre fonction de messagerie vocale, telle que la modification de leur message d'accueil et d'autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="e221b-106">As a fallback mechanism, Cloud PBX Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings .</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="e221b-107">Environnements Cloud uniquement : installer la messagerie vocale du Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="e221b-107">Set up Phone System voicemail</span></span>

<span data-ttu-id="e221b-108">Pour les utilisateurs de Skype Entreprise Online et de Calling Plans, la messagerie vocale du Système téléphonique est automatiquement installée et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="e221b-108">For Skype for Business Online and PSTN Calling users, Cloud PBX voicemail is automatically set up and provisioned for users after you assign a Skype for Business Cloud PBX license and a phone number to them.</span></span>

1. <span data-ttu-id="e221b-109">Si la fonctionnalité Système téléphonique n’est pas incluse dans votre forfait, vous devrez peut-être acheter des licences supplémentaires **Système téléphonique**.</span><span class="sxs-lookup"><span data-stu-id="e221b-109">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="e221b-110">Vous devrez peut-être également acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e221b-110">You may also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="e221b-111">Voir[Licences complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e221b-111">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="e221b-112">[Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Attribuer des licences Skype Entreprise et Microsoft Team](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) et les licences Exchange Online aux personnes de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="e221b-112">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span> <span data-ttu-id="e221b-113">Après cela, ils pourront recevoir des messages vocaux !
</span><span class="sxs-lookup"><span data-stu-id="e221b-113">After you do that, they will be able to receive voicemail messages!</span></span>

3. <span data-ttu-id="e221b-114">Le support pour la transcription de messages vocaux est disponible depuis mars 2017 et est activé par défaut pour tous les clients et utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e221b-114">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="e221b-115">Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e221b-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="e221b-116">Système téléphonique avec environnements locaux</span><span class="sxs-lookup"><span data-stu-id="e221b-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="e221b-117">Les informations suivantes concernent la configuration de la messagerie vocale du Système téléphonique pour fonctionner avec les Forfaits d'appels locaux.</span><span class="sxs-lookup"><span data-stu-id="e221b-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>

1. <span data-ttu-id="e221b-118">Si la fonctionnalité Système téléphonique n’est pas incluse dans votre forfait, vous devrez peut-être acheter des licences supplémentaires **Système téléphonique**.</span><span class="sxs-lookup"><span data-stu-id="e221b-118">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="e221b-119">Vous devez également acheter une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e221b-119">You also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="e221b-120">Voir[Licences complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e221b-120">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="e221b-121">[Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Attribuer des licences Skype Entreprise et Microsoft Team](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) et les licences Exchange Online aux personnes de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="e221b-121">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span>

3. <span data-ttu-id="e221b-122">Suivez les instructions de la section**Activer les services vocaux du Système téléphonique et de messagerie vocale pour les utilisateurs** du guide[Configuration de Skype Entreprise, version Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-122">Next, follow the instructions in the **Enable users for Cloud PBX voice and voice mail services** section of the[Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="e221b-123">Le support pour la transcription de messages vocaux est disponible depuis mars 2017 et est activé par défaut pour tous les clients et utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e221b-123">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="e221b-124">Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e221b-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="e221b-125">Vous pouvez également consulter le [Support technique de la messagerie vocale Azure PBX pour Exchange Server](https://support.microsoft.com/en-us/kb/3195158) pour apprendre à configurer la distribution des messages vocaux Azure pour les utilisateurs du Système téléphonique ayant une boîte aux lettres locale.</span><span class="sxs-lookup"><span data-stu-id="e221b-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e221b-126">Paramétrage des stratégies de messagerie vocale dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="e221b-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="e221b-127">La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e221b-128">Vous ne pouvez pas créer de nouvelle stratégie pour la transcription et son masquage à l'aide de l'applet de commande **New-CsOnlineVoiceMailPolicy** et vous ne pouvez pas supprimer de stratégie à l'aide de l'applet de commande **Remove-CsOnlineVoiceMailPolicy**.</span><span class="sxs-lookup"><span data-stu-id="e221b-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e221b-129">Vous pouvez gérer les paramètres de transcription pour vos utilisateurs à l'aide des stratégies de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="e221b-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e221b-130">Pour afficher toutes les stratégies disponibles concernant les messages vocaux, vous pouvez utiliser l'applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-130">To see the all available voicemail policy instances, you can use the[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e221b-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e221b-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>

![Fenêtre Get-CsOnlineVoiceMailPolicy.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e221b-133">Désactivation de la transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="e221b-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="e221b-134">Puisque le paramètre par défaut pour la transcription est activée pour votre organisation, vous voudrez peut-être le désactiver au moyen de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-134">Because the default setting for transcription is on for your organization, you may want to disable it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="e221b-135">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e221b-135">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e221b-136">Activer le masquage de transcription pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="e221b-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e221b-137">Le masquage de la transcription est désactivé par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e221b-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e221b-138">S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="e221b-139">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e221b-139">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e221b-140">Désactivation de la transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e221b-140">Turning off transcription for a user</span></span>

<span data-ttu-id="e221b-141">Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="e221b-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e221b-142">Par exemple, si la transcription des messages vocaux est activée pour tous vos utilisateurs, vous pouvez attribuer une stratégie pour désactiver la transcription pour un utilisateur spécifique au moyen de l'applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-142">For example, if voicemail transcription is enabled for all of your users you can assign a policy to disable transcription for a specific user using [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e221b-143">Pour désactiver la transcription pour un utilisateur unique, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e221b-143">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e221b-144">Activer le masquage de transcription pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e221b-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e221b-145">Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="e221b-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e221b-146">Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e221b-146">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e221b-p111">Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="e221b-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e221b-149">Aidez vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e221b-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e221b-150">Nous disposons d'une grande quantité d'informations et d'articles de formation qui permettront à vos utilisateurs de se servir efficacement de la messagerie vocale Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e221b-150">We have a lot of training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="e221b-151">Orientez-les vers les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="e221b-151">Point them to the following articles:</span></span>

- <span data-ttu-id="e221b-152">[Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8) : Cet article explique comment écouter votre messagerie vocale dans Skype Entreprise, modifier votre message d'accueil vocal et écouter vos messages vocaux à différentes vitesses.</span><span class="sxs-lookup"><span data-stu-id="e221b-152">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e221b-153">Formation Skype Entreprise 2016</span><span class="sxs-lookup"><span data-stu-id="e221b-153">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e221b-154">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e221b-154">Related topics</span></span>
[<span data-ttu-id="e221b-155">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e221b-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="e221b-156">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="e221b-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


