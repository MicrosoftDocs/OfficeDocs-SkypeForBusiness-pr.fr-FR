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
description: Découvrez comment configurer les paramètres Microsoft Teams et Skype Entreprise utiliser une autre langue pour le message d’accueil vocal par défaut de votre organisation.
ms.openlocfilehash: f211a5e160ce05707a454e5100409840e4c781ac
ms.sourcegitcommit: eca3f5e83e4a07be197936db19f539cbfa2c2bd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52804521"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="413e7-103">Modifier la langue par défaut des messages d'accueil et des courriers électroniques</span><span class="sxs-lookup"><span data-stu-id="413e7-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="413e7-104">Si vous êtes un administrateur [général,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)vous pouvez configurer Skype Entreprise la lecture de son message d’accueil vocal par défaut dans une autre langue.</span><span class="sxs-lookup"><span data-stu-id="413e7-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="413e7-105">Le message d'accueil système par défaut ressemble à celui-ci : « Veuillez laisser un message pour John Smith.</span><span class="sxs-lookup"><span data-stu-id="413e7-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="413e7-106">Enregistrez votre message après le signal sonore.</span><span class="sxs-lookup"><span data-stu-id="413e7-106">After the tone, please record your message.</span></span> <span data-ttu-id="413e7-107">À la fin de l'enregistrement, raccrochez ou appuyez sur la touche dièse pour plus d'options. »</span><span class="sxs-lookup"><span data-stu-id="413e7-107">When you finish recording, hang up, or press the pound key for more options."</span></span>
  
 <span data-ttu-id="413e7-108">**Tout d'abord, lisez cette information importante :**</span><span class="sxs-lookup"><span data-stu-id="413e7-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="413e7-109">**Les langues disponibles sont déterminées par l'emplacement de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="413e7-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="413e7-110">Par exemple, si votre organisation est située aux États-Unis, vous pouvez configurer la langue par défaut sur l'anglais ou l'espagnol.</span><span class="sxs-lookup"><span data-stu-id="413e7-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="413e7-111">Si votre organisation est située au Canada, vous avez le choix entre l'anglais et le français.</span><span class="sxs-lookup"><span data-stu-id="413e7-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="413e7-112">Pour obtenir la liste des langues Teams et Skype Entreprise prise en charge, voir les suivantes :</span><span class="sxs-lookup"><span data-stu-id="413e7-112">For a list of supported languages in Teams and Skype for Business, see the following:</span></span>
  - [<span data-ttu-id="413e7-113">Microsoft Teams langues prise en charge</span><span class="sxs-lookup"><span data-stu-id="413e7-113">Microsoft Teams supported languages</span></span>](languages-for-voicemail-greetings-and-messages.md)
  - [<span data-ttu-id="413e7-114">Skype Entreprise langues prise en charge</span><span class="sxs-lookup"><span data-stu-id="413e7-114">Skype for Business supported languages</span></span>](/skypeforbusiness/what-is-phone-system-in-office-365/phone-system-voicemail/languages-for-voicemail-greetings-and-messages)

- <span data-ttu-id="413e7-115">**Modification des langues du message d’accueil de la messagerie vocale et des messages vocaux d’un utilisateur individuel.**</span><span class="sxs-lookup"><span data-stu-id="413e7-115">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="413e7-116">Vous pouvez modifier la langue préférée des utilisateurs, ce qui a pour effet de modifier la langue du message d’accueil de leur messagerie vocale et des messages vocaux envoyés à leur boîte Outlook messagerie.</span><span class="sxs-lookup"><span data-stu-id="413e7-116">You can change the preferred language for users, which will change the language of their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="413e7-117">Pour plus d’informations, [voir Comment définir les paramètres](/office365/troubleshoot/access-management/set-language-and-region)de langue et de région pour Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="413e7-117">For more information, see [How to set language and region settings for Microsoft 365 or Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

  > [!NOTE]
  > <span data-ttu-id="413e7-118">Les utilisateurs peuvent modifier leur propre langue du message d'accueil par le biais de leurs paramètres après s'être connectés.</span><span class="sxs-lookup"><span data-stu-id="413e7-118">Users can change their own greeting language through their settings after they sign in.</span></span> <span data-ttu-id="413e7-119">Pour plus d’informations, [voir Modifier la langue d’affichage et](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US) le fuseau horaire dans Microsoft 365 Entreprise</span><span class="sxs-lookup"><span data-stu-id="413e7-119">For more information, see [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="413e7-120">**Vous voulez enregistrer un message d'accueil personnel ?**</span><span class="sxs-lookup"><span data-stu-id="413e7-120">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="413e7-121">Reportez-vous à la rubrique [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="413e7-121">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="413e7-122">Par Microsoft Teams - Les utilisateurs peuvent modifier leurs paramètres de messagerie vocale à partir des [Teams du client de bureau](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="413e7-122">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="413e7-123">**Voulez-vous modifier la langue de l’invite de messagerie vocale ?**</span><span class="sxs-lookup"><span data-stu-id="413e7-123">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="413e7-124">Pour Skype Entreprise - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) et choisissez une nouvelle langue sous **Langue d’invite.**</span><span class="sxs-lookup"><span data-stu-id="413e7-124">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="413e7-125">Pour Microsoft Teams - Les utilisateurs peuvent modifier leur message d’accueil vocal à partir des [Teams du client de bureau](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="413e7-125">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="413e7-126">Modifier la langue du système pour l'ensemble des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="413e7-126">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="413e7-127">Connectez-vous à [l’auprès de votre compte d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) général sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="413e7-127">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="413e7-128">Dans le Microsoft 365 d’administration, **sélectionnez** Paramètres  >  **Paramètres**  >  **de votre organisation.**</span><span class="sxs-lookup"><span data-stu-id="413e7-128">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span>

     ![Capture d’écran montrant le choix Paramètres puis profil de l’organisation.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="413e7-130">Choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="413e7-130">Choose **Edit**.</span></span>

    ![Capture d’écran montrant l’option Modifier.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="413e7-132">Sélectionnez une langue dans la liste **Langue préférée** pour l'ensemble des utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="413e7-132">Select a language from the **Preferred language** list for everyone in your organization.</span></span>

5. <span data-ttu-id="413e7-133">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="413e7-133">Choose **Save**.</span></span>

## <a name="related-articles-for-the-admin"></a><span data-ttu-id="413e7-134">Articles connexes pour l'administrateur</span><span class="sxs-lookup"><span data-stu-id="413e7-134">Related articles for the admin</span></span>

- [<span data-ttu-id="413e7-135">Système téléphonique et forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="413e7-135">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="413e7-136">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="413e7-136">Set up Calling Plans</span></span>](set-up-calling-plans.md)

- [<span data-ttu-id="413e7-137">Planifiez Système téléphonique en Microsoft 365 ou Office 365 avec une connectivité PSTN Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="413e7-137">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

## <a name="related-topics"></a><span data-ttu-id="413e7-138">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="413e7-138">Related topics</span></span>

- [<span data-ttu-id="413e7-139">Changer la langue d’affichage et le fuseau horaire dans Microsoft 365 ou Office 365 entreprise</span><span class="sxs-lookup"><span data-stu-id="413e7-139">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)

- <span data-ttu-id="413e7-140">[Ajouter une langue ou définir les préférences de langue dans Office 2010 et les versions ultérieures](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="413e7-140">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>

- [<span data-ttu-id="413e7-141">Activer ou modifier la langue de disposition du clavier dans Office</span><span class="sxs-lookup"><span data-stu-id="413e7-141">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
