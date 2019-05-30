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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer Skype Entreprise afin d’utiliser une autre langue pour le message d’accueil vocal par défaut de votre organisation. '
ms.openlocfilehash: 5502bea261e3313bed2dae854ca23d6a27f4f8b8
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494569"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="6989a-103">Modifier la langue par défaut des messages d'accueil et des courriers électroniques</span><span class="sxs-lookup"><span data-stu-id="6989a-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="6989a-104">Si vous êtes un [administrateur général d'Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), vous pouvez configurer Skype Entreprise pour que l'application lise le message d'accueil de sa messagerie vocale dans une autre langue.</span><span class="sxs-lookup"><span data-stu-id="6989a-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="6989a-105">Le message d'accueil système par défaut ressemble à celui-ci : « Veuillez laisser un message pour John Smith.</span><span class="sxs-lookup"><span data-stu-id="6989a-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="6989a-106">Enregistrez votre message après le signal sonore.</span><span class="sxs-lookup"><span data-stu-id="6989a-106">After the tone, please record your message.</span></span> <span data-ttu-id="6989a-107">À la fin de l'enregistrement, raccrochez ou appuyez sur la touche dièse pour plus d'options. »</span><span class="sxs-lookup"><span data-stu-id="6989a-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="6989a-108">**Tout d'abord, lisez cette information importante :**</span><span class="sxs-lookup"><span data-stu-id="6989a-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="6989a-109">**Les langues disponibles sont déterminées par l'emplacement de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="6989a-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="6989a-110">Par exemple, si votre organisation est située aux États-Unis, vous pouvez configurer la langue par défaut sur l'anglais ou l'espagnol.</span><span class="sxs-lookup"><span data-stu-id="6989a-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="6989a-111">Si votre organisation est située au Canada, vous avez le choix entre l'anglais et le français.</span><span class="sxs-lookup"><span data-stu-id="6989a-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="6989a-112">Pour obtenir la liste des langues prises en charge, consultez la rubrique [Langues pour les messages et les messages d'accueil de la messagerie vocale de Skype Entreprise](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="6989a-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="6989a-p103">**Vous ne pouvez pas modifier la langue pour une seule personne de l'organisation.** Vous pouvez uniquement modifier la langue du message d'accueil pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6989a-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6989a-115">Les utilisateurs peuvent modifier leur propre langue du message d'accueil par le biais de leurs paramètres après s'être connectés.</span><span class="sxs-lookup"><span data-stu-id="6989a-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="6989a-116">**Vous voulez enregistrer un message d'accueil personnel ?**</span><span class="sxs-lookup"><span data-stu-id="6989a-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="6989a-117">Reportez-vous à la rubrique [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="6989a-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="6989a-118">**Voulez-vous modifier la langue de l’invite de la boîte vocale?**</span><span class="sxs-lookup"><span data-stu-id="6989a-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="6989a-119">Accédez à [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) la nouvelle langue et sélectionnez-la sous langue de l' **invite**.</span><span class="sxs-lookup"><span data-stu-id="6989a-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="6989a-120">Modifier la langue du système pour l'ensemble des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="6989a-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="6989a-121">Connectez-vous à l’aide de votre compte d'[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) [administrateur général Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="6989a-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="6989a-122">Dans le centre d’administration Microsoft 365, sélectionnez **paramètres** > de l'**organisation**.</span><span class="sxs-lookup"><span data-stu-id="6989a-122">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Capture d’écran montrant la sélection des paramètres, puis le profil de l’organisation.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="6989a-124">Choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6989a-124">Choose **Edit**.</span></span>
    
    ![Capture d’écran montrant l’option d’édition.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="6989a-126">Sélectionnez une langue dans la liste **Langue préférée** pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6989a-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="6989a-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6989a-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="6989a-128">Articles connexes pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="6989a-128">Related articles for the admin</span></span>

- [<span data-ttu-id="6989a-129">Système téléphonique et forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="6989a-129">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="6989a-130">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="6989a-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="6989a-131">Planifier le système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6989a-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="6989a-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6989a-132">Related topics</span></span>

- [<span data-ttu-id="6989a-133">Changer la langue d'affichage et le fuseau horaire dans Office 365 pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="6989a-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="6989a-134">[Ajouter une langue ou définir les préférences de langue dans Office 2010 et les versions ultérieures](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="6989a-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="6989a-135">Activer ou modifier la langue de disposition du clavier dans Office</span><span class="sxs-lookup"><span data-stu-id="6989a-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
