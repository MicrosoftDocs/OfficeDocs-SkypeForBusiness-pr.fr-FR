---
title: "Changer la langue par défaut pour des salutations et des e-mails"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="a065d-103">Changer la langue par défaut pour des salutations et des e-mails</span><span class="sxs-lookup"><span data-stu-id="a065d-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="a065d-104">Si vous êtes un [administrateur global d’Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), vous pouvez configurer Skype pour entreprise de lire sa messagerie vocale par défaut que de salutation dans une autre langue.</span><span class="sxs-lookup"><span data-stu-id="a065d-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="a065d-105">Le message d’accueil système par défaut est quelque chose comme, « veuillez laisser un message pour John Smith.</span><span class="sxs-lookup"><span data-stu-id="a065d-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="a065d-106">Après la tonalité, veuillez enregistrer votre message.</span><span class="sxs-lookup"><span data-stu-id="a065d-106">After the tone, please record your message.</span></span> <span data-ttu-id="a065d-107">Lorsque vous avez terminé l’enregistrement, raccrocher, ou appuyez sur la touche dièse pour plus d’options. »</span><span class="sxs-lookup"><span data-stu-id="a065d-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="a065d-108">**Tout d'abord, lisez cette information importante :**</span><span class="sxs-lookup"><span data-stu-id="a065d-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="a065d-109">**Les langues qui sont disponibles sont déterminées par l’emplacement de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="a065d-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="a065d-110">Par exemple, si votre organisation est située aux États-Unis, vous pouvez définir la langue par défaut pour l’anglais ou espagnol.</span><span class="sxs-lookup"><span data-stu-id="a065d-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="a065d-111">Si votre organisation est située au Canada, vous pouvez choisir entre l’anglais et le Français.</span><span class="sxs-lookup"><span data-stu-id="a065d-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="a065d-112">Pour une liste des langues prises en charge, consultez [langages de greetings de messagerie vocale et des messages Skype pour les entreprises](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a065d-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="a065d-p103">**Vous ne pouvez pas modifier la langue pour une seule personne de l'organisation.** Vous pouvez uniquement modifier la langue du message d'accueil pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a065d-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a065d-115">Les utilisateurs peuvent modifier leurs propres au moyen de leurs paramètres de salutation après leur connectent.</span><span class="sxs-lookup"><span data-stu-id="a065d-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="a065d-116">**Voulez-vous enregistrer le message sortant de la messagerie vocale ?**</span><span class="sxs-lookup"><span data-stu-id="a065d-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="a065d-117">Reportez-vous à la section [Skype de vérifier les options de la messagerie vocale d’entreprise](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="a065d-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="a065d-118">Modification de la langue pour l'ensemble des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="a065d-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="a065d-119">Connectez-vous avec votre compte [d’administrateur global d’Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) à[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="a065d-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="a065d-120">Dans le centre d’administration, cliquez sur **paramètres** > **profil d’organisation**.</span><span class="sxs-lookup"><span data-stu-id="a065d-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="a065d-122">Choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a065d-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="a065d-124">Sélectionnez une langue dans la liste **langue de favoris** dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a065d-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="a065d-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a065d-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="a065d-126">Articles connexes pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="a065d-126">Related articles for the admin</span></span>

- [<span data-ttu-id="a065d-127">Quels sont les Plans d’appel dans Office 365 ?</span><span class="sxs-lookup"><span data-stu-id="a065d-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="a065d-128">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="a065d-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="a065d-129">Système de téléphone plan dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server 2015 ou Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a065d-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="a065d-130">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a065d-130">Related topics</span></span>

- [<span data-ttu-id="a065d-131">Changer la langue d'affichage et le fuseau horaire dans Office 365 pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="a065d-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="a065d-132">[Ajouter une langue ou définir les préférences de langue dans Office 2010 et les versions ultérieures](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="a065d-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="a065d-133">Activer ou modifier une langue de disposition du clavier</span><span class="sxs-lookup"><span data-stu-id="a065d-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

