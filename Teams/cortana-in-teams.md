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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428210"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="8fc04-103">Cortana’assistance vocale dans Teams</span><span class="sxs-lookup"><span data-stu-id="8fc04-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="8fc04-104">Cortana l’assistance vocale est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android et les écrans Microsoft Teams pour les utilisateurs aux États-Unis, au Royaume-Uni, au Canada, en Inde et en Australie.</span><span class="sxs-lookup"><span data-stu-id="8fc04-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="8fc04-105">Salles Microsoft Teams sur Windows est uniquement pris en charge pour les utilisateurs aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="8fc04-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="8fc04-106">Cortana’assistance vocale vocale n’est actuellement pas disponible pour les Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-Haut, DoD et les locataires EDU autres que les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="8fc04-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="8fc04-107">Cortana’assistance vocale dans l’Teams mobile est désormais disponible pour les clients EDU en France.</span><span class="sxs-lookup"><span data-stu-id="8fc04-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="8fc04-108">Une extension vers d’autres langues et régions sera mise en place dans le cadre des prochaines publication.</span><span class="sxs-lookup"><span data-stu-id="8fc04-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="8fc04-109">Cortana’assistance vocale dans Salles Microsoft Teams est publiée sous Aperçu.</span><span class="sxs-lookup"><span data-stu-id="8fc04-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="8fc04-110">Dans sa version d’Cortana, cette fonction est prise en charge uniquement aux États-Unis avec la langue EN-US sur les appareils qui ont des micros Microphones Microphones Connectés.</span><span class="sxs-lookup"><span data-stu-id="8fc04-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="8fc04-111">Cortana’assistance vocale dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur les périphériques d’affichage Microsoft Teams permet aux utilisateurs de Microsoft 365 Entreprise de simplifier les tâches de communication, de collaboration et de réunion en utilisant un langage naturel parlé.</span><span class="sxs-lookup"><span data-stu-id="8fc04-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="8fc04-112">Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton de microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant &#8220;Cortana&#8221; dans la salle Microsoft Teams ou lors de l’utilisation d’un écran Microsoft Teams'</span><span class="sxs-lookup"><span data-stu-id="8fc04-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="8fc04-113">Pour communiquer rapidement avec leur équipe en mains libres et en cours, les utilisateurs peuvent dire des requêtes telles que &#8220;appeler Megan&#8221; ou &#8220;envoyer un message à mon prochain&#8221;.</span><span class="sxs-lookup"><span data-stu-id="8fc04-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="8fc04-114">Les utilisateurs peuvent également participer à des réunions en &#8220;participer à ma prochaine&#8221; réunion et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="8fc04-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="8fc04-115">Ces expériences d’assistance vocale sont tenues à l’aide de [services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Cortana de niveau entreprise qui sont pleinement conformes aux promesses de confidentialité, de sécurité et de conformité d’Office 365, comme le reflètent les conditions des services en ligne [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="8fc04-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="8fc04-116">Contrôle et limitations de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="8fc04-116">Admin control and limitations</span></span>

<span data-ttu-id="8fc04-117">Cortana’assistance vocale dans Teams est l’application de services qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité au niveau Office 365 au niveau de l’entreprise, comme indiqué dans les conditions des services en ligne (OST).</span><span class="sxs-lookup"><span data-stu-id="8fc04-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="8fc04-118">La fonctionnalité sera activée par défaut pour les locataires.</span><span class="sxs-lookup"><span data-stu-id="8fc04-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="8fc04-119">Les administrateurs des locataires peuvent contrôler qui dans leur client peut utiliser Cortana assistance vocale dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="8fc04-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="8fc04-120">Cette stratégie est définie au niveau du compte d’utilisateur ou du client.</span><span class="sxs-lookup"><span data-stu-id="8fc04-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="8fc04-121">Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode au sein de ce contrôle de stratégie pour déterminer si Cortana est désactivé, activé avec l’appel du bouton d’appel uniquement ou avec l’appel de mot de sortie (applicable aux appareils qui le supportent, comme l’affichage Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="8fc04-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="8fc04-122">Les administrateurs peuvent utiliser les cmdlets PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans Microsoft Teams centre d’administration).</span><span class="sxs-lookup"><span data-stu-id="8fc04-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="8fc04-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fc04-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="8fc04-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fc04-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="8fc04-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fc04-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="8fc04-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fc04-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="8fc04-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="8fc04-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="8fc04-128">Par exemple, la commande ci-dessous crée une stratégie avec le nom &#8220;EmployeeCortanaPolicy&#8221; où l’assistance vocale Cortana dans Microsoft Teams est désactivée.</span><span class="sxs-lookup"><span data-stu-id="8fc04-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="8fc04-129">Cet exemple illustre la mise à jour d’une stratégie existante avec le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec appel push-button uniquement.</span><span class="sxs-lookup"><span data-stu-id="8fc04-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="8fc04-130">Les utilisateurs pourront appeler Cortana en sélectionnant le bouton Cortana micro dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8fc04-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="8fc04-131">Le mot de veille (&#8220;Hey Cortana&#8221; ou &#8220;Cortana&#8221;) appel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="8fc04-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="8fc04-132">Cet exemple illustre la mise à jour de la stratégie et l’activation Cortana’assistance vocale avec le bouton Push et l’appel de word de veille.</span><span class="sxs-lookup"><span data-stu-id="8fc04-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="8fc04-133">À l’heure de la publication initiale pour Microsoft 365 Entreprise utilisateurs aux États-Unis en anglais, les fonctions suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="8fc04-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="8fc04-134">L Teams’application mobile ne prendra pas en charge l’activation de word de veille, mais elle sera prise en charge à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="8fc04-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="8fc04-135">Salles Microsoft Teams sur les Windows’affichage Microsoft Teams’écran de veille 365 365 665 365 365 365 365 365 365 367 567</span><span class="sxs-lookup"><span data-stu-id="8fc04-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="8fc04-136">Contrôle de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="8fc04-136">User control</span></span>

<span data-ttu-id="8fc04-137">Les utilisateurs individuels peuvent essayer Cortana’assistance vocale sur différents appareils :</span><span class="sxs-lookup"><span data-stu-id="8fc04-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="8fc04-138">Sélectionnez le bouton microphone dans l’Teams’application mobile.</span><span class="sxs-lookup"><span data-stu-id="8fc04-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="8fc04-139">Sélectionnez le bouton du microphone ou dites « Cortana » dans Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fc04-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="8fc04-140">Dites « Cortana » sur Microsoft Teams affiche les appareils.</span><span class="sxs-lookup"><span data-stu-id="8fc04-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="8fc04-141">Vous pouvez contrôler si le Cortana dans Teams est activé pour votre appareil à l’aide d’un paramètre de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8fc04-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="8fc04-142">Salles Microsoft Teams sur Windows</span><span class="sxs-lookup"><span data-stu-id="8fc04-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="8fc04-143">Les modifications apportées au niveau de l’appareil sont disponibles si Cortana est activé au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="8fc04-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="8fc04-144">Cortana sont publiées par défaut.</span><span class="sxs-lookup"><span data-stu-id="8fc04-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="8fc04-145">Pour activer Cortana au niveau de l’appareil, ces attributs XML doivent être ajoutés au fichier XML SkypeSettings :</span><span class="sxs-lookup"><span data-stu-id="8fc04-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="8fc04-146">Apporter des modifications au niveau de la réunion est disponible si Cortana est activé au niveau de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8fc04-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="8fc04-147">Pour activer Cortana’assistance vocale pendant une réunion, déplacez le **basculement activé** ou **non.**</span><span class="sxs-lookup"><span data-stu-id="8fc04-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="8fc04-148">Une fois la réunion terminée, Cortana à la définition des paramètres au niveau de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8fc04-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
