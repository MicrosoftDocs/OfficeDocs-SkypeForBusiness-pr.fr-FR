---
title: Modifier la langue par défaut des messages d'accueil et des courriers électroniques
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
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
description: 'Découvrez comment configurer Skype Entreprise afin d’utiliser une autre langue pour le message d’accueil vocal par défaut de votre organisation. '
ms.openlocfilehash: 6de73212df6be8a1f0d52cff8065536442085783
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198476"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="64cc8-103">Modifier la langue par défaut des messages d'accueil et des courriers électroniques</span><span class="sxs-lookup"><span data-stu-id="64cc8-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="64cc8-104">Si vous êtes un [administrateur général d'Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), vous pouvez configurer Skype Entreprise pour que l'application lise le message d'accueil de sa messagerie vocale dans une autre langue.</span><span class="sxs-lookup"><span data-stu-id="64cc8-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="64cc8-105">Le message d'accueil système par défaut ressemble à celui-ci : « Veuillez laisser un message pour John Smith.</span><span class="sxs-lookup"><span data-stu-id="64cc8-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="64cc8-106">Enregistrez votre message après le signal sonore.</span><span class="sxs-lookup"><span data-stu-id="64cc8-106">After the tone, please record your message.</span></span> <span data-ttu-id="64cc8-107">À la fin de l'enregistrement, raccrochez ou appuyez sur la touche dièse pour plus d'options. »</span><span class="sxs-lookup"><span data-stu-id="64cc8-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="64cc8-108">**Tout d'abord, lisez cette information importante :**</span><span class="sxs-lookup"><span data-stu-id="64cc8-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="64cc8-109">**Les langues disponibles sont déterminées par l'emplacement de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="64cc8-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="64cc8-110">Par exemple, si votre organisation est située aux États-Unis, vous pouvez configurer la langue par défaut sur l'anglais ou l'espagnol.</span><span class="sxs-lookup"><span data-stu-id="64cc8-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="64cc8-111">Si votre organisation est située au Canada, vous avez le choix entre l'anglais et le français.</span><span class="sxs-lookup"><span data-stu-id="64cc8-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="64cc8-112">Pour obtenir la liste des langues prises en charge, consultez la rubrique [Langues pour les messages et les messages d'accueil de la messagerie vocale de Skype Entreprise](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="64cc8-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="64cc8-p103">**Vous ne pouvez pas modifier la langue pour une seule personne de l'organisation.** Vous pouvez uniquement modifier la langue du message d'accueil pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="64cc8-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64cc8-115">Les utilisateurs peuvent modifier leur propre langue du message d'accueil par le biais de leurs paramètres après s'être connectés.</span><span class="sxs-lookup"><span data-stu-id="64cc8-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="64cc8-116">**Vous voulez enregistrer un message d'accueil personnel ?**</span><span class="sxs-lookup"><span data-stu-id="64cc8-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="64cc8-117">Reportez-vous à la rubrique [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="64cc8-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="64cc8-118">**Vous souhaitez modifier la langue d’invite de la messagerie vocale**</span><span class="sxs-lookup"><span data-stu-id="64cc8-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="64cc8-119">Accédez à [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) et choisir une nouvelle langue sous **Langue d’invite**.</span><span class="sxs-lookup"><span data-stu-id="64cc8-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="64cc8-120">Modifier la langue du système pour l'ensemble des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="64cc8-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="64cc8-121">Connectez-vous avec votre compte [d’administrateur général Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) à[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="64cc8-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="64cc8-122">Dans le centre d’administration Office 365, choisissez **paramètres** > **profil d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="64cc8-122">In the Office 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="64cc8-124">Choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="64cc8-124">Choose **Edit**.</span></span>
    
    ![Choisissez Modifier.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="64cc8-126">Sélectionnez une langue dans la liste **Langue préférée** pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="64cc8-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="64cc8-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64cc8-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="64cc8-128">Articles connexes pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="64cc8-128">Related articles for the admin</span></span>

- [<span data-ttu-id="64cc8-129">Système téléphonique et forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="64cc8-129">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="64cc8-130">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="64cc8-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="64cc8-131">Planifier Business Server système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype</span><span class="sxs-lookup"><span data-stu-id="64cc8-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="64cc8-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="64cc8-132">Related topics</span></span>

- [<span data-ttu-id="64cc8-133">Changer la langue d'affichage et le fuseau horaire dans Office 365 pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="64cc8-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="64cc8-134">[Ajouter une langue ou définir les préférences de langue dans Office 2010 et les versions ultérieures](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="64cc8-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="64cc8-135">Activer ou modifier la langue de disposition du clavier dans Office</span><span class="sxs-lookup"><span data-stu-id="64cc8-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
