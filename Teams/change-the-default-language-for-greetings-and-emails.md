---
title: Modifier la langue par défaut des messages d'accueil et des courriers électroniques
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Découvrez comment configurer Skype Entreprise pour utiliser une autre langue pour le message d’accueil vocal par défaut de votre organisation.
ms.openlocfilehash: f6fb890d52e052afffccbfe753ab5b3b8a1bb338
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102670"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="0cfba-103">Modifier la langue par défaut des messages d'accueil et des courriers électroniques</span><span class="sxs-lookup"><span data-stu-id="0cfba-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="0cfba-104">Si vous êtes un administrateur [général,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)vous pouvez configurer Skype Entreprise de façon à lire son message d’accueil vocal par défaut dans une autre langue.</span><span class="sxs-lookup"><span data-stu-id="0cfba-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="0cfba-105">Le message d'accueil système par défaut ressemble à celui-ci : « Veuillez laisser un message pour John Smith.</span><span class="sxs-lookup"><span data-stu-id="0cfba-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="0cfba-106">Enregistrez votre message après le signal sonore.</span><span class="sxs-lookup"><span data-stu-id="0cfba-106">After the tone, please record your message.</span></span> <span data-ttu-id="0cfba-107">À la fin de l'enregistrement, raccrochez ou appuyez sur la touche dièse pour plus d'options. »</span><span class="sxs-lookup"><span data-stu-id="0cfba-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="0cfba-108">**Tout d'abord, lisez cette information importante :**</span><span class="sxs-lookup"><span data-stu-id="0cfba-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="0cfba-109">**Les langues disponibles sont déterminées par l'emplacement de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="0cfba-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="0cfba-110">Par exemple, si votre organisation est située aux États-Unis, vous pouvez configurer la langue par défaut sur l'anglais ou l'espagnol.</span><span class="sxs-lookup"><span data-stu-id="0cfba-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="0cfba-111">Si votre organisation est située au Canada, vous avez le choix entre l'anglais et le français.</span><span class="sxs-lookup"><span data-stu-id="0cfba-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="0cfba-112">Pour obtenir la liste des langues prises en charge, consultez la rubrique [Langues pour les messages et les messages d'accueil de la messagerie vocale de Skype Entreprise](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0cfba-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="0cfba-113">**Modification des langues du message d’accueil de la messagerie vocale et des messages vocaux d’un utilisateur individuel.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-113">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="0cfba-114">Vous pouvez modifier la langue préférée des utilisateurs, ce qui modifiera la langue du message d’accueil de leur messagerie vocale et des messages vocaux envoyés à leur boîte aux lettres Outlook.</span><span class="sxs-lookup"><span data-stu-id="0cfba-114">You can change the preferred lanaguage for users, which will change the language of the their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="0cfba-115">Pour obtenir des instructions, voir [Comment définir les paramètres de langue et de région pour Microsoft 365 ou Office 365] ( https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region) .</span><span class="sxs-lookup"><span data-stu-id="0cfba-115">For instruction please see [How to set language and region settings for Microsoft 365 or Office 365] (https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0cfba-116">Les utilisateurs peuvent modifier leur propre langue du message d’accueil à l’aide de leurs paramètres après s’être connectés en suivant les instructions trouvées dans Modifier la langue d’affichage et le fuseau horaire dans [Microsoft 365 pour les entreprises](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="0cfba-116">Users can change their own greeting language through their settings after they sign in by following instructions found in [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="0cfba-117">**Vous voulez enregistrer un message d'accueil personnel ?**</span><span class="sxs-lookup"><span data-stu-id="0cfba-117">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="0cfba-118">Reportez-vous à la rubrique [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="0cfba-118">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="0cfba-119">Pour Microsoft Teams : les utilisateurs peuvent modifier leurs paramètres de messagerie vocale à partir des [paramètres](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) du client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="0cfba-119">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="0cfba-120">**Voulez-vous modifier la langue de l’invite de messagerie vocale ?**</span><span class="sxs-lookup"><span data-stu-id="0cfba-120">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="0cfba-121">Pour Skype Entreprise - et choisissez une nouvelle langue sous [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) **Langue d’invite.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-121">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="0cfba-122">Pour Microsoft Teams : les utilisateurs peuvent modifier leur message d’accueil vocal à partir des [paramètres](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) du client de bureau Teams</span><span class="sxs-lookup"><span data-stu-id="0cfba-122">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="0cfba-123">Modifier la langue du système pour l'ensemble des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="0cfba-123">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="0cfba-124">Connectez-vous à [l’auprès de votre compte d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) général sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="0cfba-124">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="0cfba-125">Dans le Centre d’administration Microsoft 365, sélectionnez **Paramètres** du profil de  >    >  **l’organisation.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-125">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![Capture d’écran montrant le choix des paramètres, puis du profil de l’organisation.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="0cfba-127">Choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0cfba-127">Choose **Edit**.</span></span>
    
    ![Capture d’écran montrant l’option Modifier.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="0cfba-129">Sélectionnez une langue dans la liste **Langue préférée** pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0cfba-129">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="0cfba-130">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0cfba-130">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="0cfba-131">Articles connexes pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="0cfba-131">Related articles for the admin</span></span>

- [<span data-ttu-id="0cfba-132">Système téléphonique et forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="0cfba-132">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="0cfba-133">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="0cfba-133">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="0cfba-134">Planifier le système téléphonique dans Microsoft 365 ou Office 365 avec la connectivité PSTN sur site dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0cfba-134">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
    
## <a name="related-topics"></a><span data-ttu-id="0cfba-135">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0cfba-135">Related topics</span></span>

- [<span data-ttu-id="0cfba-136">Modifier la langue d’affichage et le fuseau horaire dans Microsoft 365 ou Office 365 pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="0cfba-136">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="0cfba-137">[Ajouter une langue ou définir les préférences de langue dans Office 2010 et les versions ultérieures](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="0cfba-137">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="0cfba-138">Activer ou modifier la langue de disposition du clavier dans Office</span><span class="sxs-lookup"><span data-stu-id="0cfba-138">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
