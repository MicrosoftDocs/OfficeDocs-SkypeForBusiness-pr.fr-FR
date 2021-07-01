---
title: Cortana’assistance vocale dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrez comment utiliser Cortana’assistance vocale avec Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219141"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="a8d4f-103">Cortana’assistance vocale dans Teams</span><span class="sxs-lookup"><span data-stu-id="a8d4f-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="a8d4f-104">Cortana l’assistance vocale est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android et les écrans Microsoft Teams pour les utilisateurs aux États-Unis, au Royaume-Uni, au Canada, en Inde et en Australie.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="a8d4f-105">Salles Microsoft Teams sur Windows est uniquement pris en charge pour les utilisateurs aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="a8d4f-106">Cortana’assistance vocale vocale n’est actuellement pas disponible pour les Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-Haut, DoD et les locataires EDU autres que les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="a8d4f-107">Cortana’assistance vocale dans l’Teams mobile est désormais disponible pour les clients EDU en France.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="a8d4f-108">Une extension vers d’autres langues et régions sera mise en place dans le cadre des prochaines publication.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="a8d4f-109">Cortana’assistance vocale dans Salles Microsoft Teams est publiée sous Aperçu.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="a8d4f-110">Dans sa version d’Cortana, cette fonction est prise en charge uniquement aux États-Unis avec la langue EN-US sur les appareils qui ont des micros Microphones Microphones Connectés.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="a8d4f-111">Cortana’assistance vocale dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur les périphériques d’affichage Microsoft Teams permet aux utilisateurs de Microsoft 365 Entreprise de rationaliser les tâches de communication, de collaboration et de réunion en utilisant le langage naturel parlé.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="a8d4f-112">Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton de microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant &#8220;Cortana&#8221; dans la salle Microsoft Teams ou lors de l’utilisation d’un écran Microsoft Teams'</span><span class="sxs-lookup"><span data-stu-id="a8d4f-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="a8d4f-113">Pour communiquer rapidement avec leur équipe en mains libres et en cours, les utilisateurs peuvent répondre à des requêtes telles que &#8220;appeler&#8221; ou &#8220;envoyer un message à mon prochain&#8221;.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="a8d4f-114">Les utilisateurs peuvent également participer à des réunions en &#8220;participer à ma prochaine&#8221; réunion et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="a8d4f-115">Ces expériences d’assistance vocale sont tenues à l’aide de [services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Cortana de niveau entreprise qui sont pleinement conformes aux promesses de confidentialité, de sécurité et de conformité d’Office 365, comme le reflètent les conditions des services en ligne [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="a8d4f-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="a8d4f-116">L’image illustre l’envoi d’une conversation Cortana sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-116">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Séquence d’écrans mobiles montrant une session Cortana conversation instantanée](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="a8d4f-118">Contrôle et limitations de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="a8d4f-118">Admin control and limitations</span></span>

<span data-ttu-id="a8d4f-119">Cortana’assistance vocale dans Teams est l’application de services qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité au niveau Office 365 au niveau de l’entreprise, comme indiqué dans les conditions des services en ligne (OST).</span><span class="sxs-lookup"><span data-stu-id="a8d4f-119">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="a8d4f-120">La fonctionnalité sera activée par défaut pour les locataires.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-120">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="a8d4f-121">Les administrateurs des locataires peuvent contrôler qui dans leur client peut utiliser Cortana’assistance vocale dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="a8d4f-121">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="a8d4f-122">Cette stratégie est définie au niveau du compte d’utilisateur ou du client.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-122">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="a8d4f-123">Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode au sein de ce contrôle de stratégie pour déterminer si Cortana est désactivé, activé avec l’appel du bouton d’appel uniquement ou avec l’appel de mot de sortie (applicable aux appareils qui le supportent, comme l’affichage Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="a8d4f-123">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="a8d4f-124">Les administrateurs peuvent utiliser les cmdlets PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans Microsoft Teams centre d’administration).</span><span class="sxs-lookup"><span data-stu-id="a8d4f-124">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="a8d4f-125">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a8d4f-125">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a8d4f-126">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a8d4f-126">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a8d4f-127">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a8d4f-127">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a8d4f-128">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a8d4f-128">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a8d4f-129">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a8d4f-129">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="a8d4f-130">Par exemple, la commande ci-dessous crée une stratégie avec le nom &#8220;EmployeeCortanaPolicy&#8221; où l’assistance vocale Cortana dans Microsoft Teams est désactivée.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-130">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="a8d4f-131">Cet exemple illustre la mise à jour d’une stratégie existante avec le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec des boutons d’appel uniquement.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-131">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="a8d4f-132">Les utilisateurs pourront appeler Cortana en sélectionnant le bouton Cortana micro dans Teams.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-132">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="a8d4f-133">Le mot de veille (&#8220;Hey Cortana&#8221; ou &#8220;Cortana&#8221;) appel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-133">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="a8d4f-134">Cet exemple illustre la mise à jour de la stratégie et l’activation Cortana’assistance vocale avec le bouton Push et l’appel de word de veille.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-134">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="a8d4f-135">À l’heure de la publication initiale Microsoft 365 Entreprise utilisateurs aux États-Unis en anglais, les fonctions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="a8d4f-135">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="a8d4f-136">L Teams’application mobile ne prendra pas en charge l’activation de word de veille, mais elle sera prise en charge à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-136">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="a8d4f-137">Salles Microsoft Teams sur les Windows’affichage Microsoft Teams’écran de veille 365 365 365 365 365 365 365 365 365 367 567</span><span class="sxs-lookup"><span data-stu-id="a8d4f-137">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="a8d4f-138">Contrôle de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a8d4f-138">User control</span></span>

<span data-ttu-id="a8d4f-139">Les utilisateurs individuels peuvent essayer Cortana’assistance vocale sur différents appareils :</span><span class="sxs-lookup"><span data-stu-id="a8d4f-139">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="a8d4f-140">Sélectionnez le bouton microphone dans l’Teams’application mobile.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-140">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="a8d4f-141">Sélectionnez le bouton du microphone ou dites « Cortana » dans Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-141">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="a8d4f-142">Dites « Cortana » sur Microsoft Teams affiche les appareils.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-142">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="a8d4f-143">Vous pouvez contrôler si le Cortana dans Teams est activé pour votre appareil à l’aide d’un paramètre de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-143">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="a8d4f-144">Teams’application mobile ou l’écran Microsoft Teams’écran</span><span class="sxs-lookup"><span data-stu-id="a8d4f-144">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="a8d4f-145">Ouvrez l Teams’application mobile.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-145">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="a8d4f-146">Sélectionnez **Paramètres**  >  **Cortana.**</span><span class="sxs-lookup"><span data-stu-id="a8d4f-146">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="a8d4f-147">Déplacez le **basculement sur Ou** **Hors.**</span><span class="sxs-lookup"><span data-stu-id="a8d4f-147">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="a8d4f-148">Microsoft Teams’affichage</span><span class="sxs-lookup"><span data-stu-id="a8d4f-148">Microsoft Teams display</span></span>

  1. <span data-ttu-id="a8d4f-149">Allez à l’écran ambiant (accueil) de l Microsoft Teams’affichage.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-149">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="a8d4f-150">Sélectionnez l’avatar utilisateur, puis sélectionnez **Paramètres.**</span><span class="sxs-lookup"><span data-stu-id="a8d4f-150">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="a8d4f-151">Si Cortana est activé, dites Cortana, Paramètres ».</span><span class="sxs-lookup"><span data-stu-id="a8d4f-151">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="a8d4f-152">Déplacez le **basculement sur Ou** **Hors.**</span><span class="sxs-lookup"><span data-stu-id="a8d4f-152">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="a8d4f-153">Salles Microsoft Teams sur Windows</span><span class="sxs-lookup"><span data-stu-id="a8d4f-153">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="a8d4f-154">Apporter des modifications au niveau de l’appareil est disponible si Cortana est activé au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-154">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="a8d4f-155">Cortana sont publiées par défaut.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-155">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="a8d4f-156">Pour activer Cortana au niveau de l’appareil, ces attributs XML doivent être ajoutés au fichier XML SkypeSettings :</span><span class="sxs-lookup"><span data-stu-id="a8d4f-156">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="a8d4f-157">Apporter des modifications au niveau de la réunion est disponible si Cortana est activé au niveau de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-157">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="a8d4f-158">Pour activer Cortana’assistance vocale pendant une réunion, déplacez le **basculement activé** ou **non.**</span><span class="sxs-lookup"><span data-stu-id="a8d4f-158">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="a8d4f-159">Une fois la réunion terminée, Cortana à la définition des paramètres au niveau de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a8d4f-159">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
