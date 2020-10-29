---
title: Aide vocale de Cortana dans Microsoft teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrir comment utiliser l’aide vocale de Cortana avec teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785388"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="64a05-103">Aide vocale de Cortana dans teams</span><span class="sxs-lookup"><span data-stu-id="64a05-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="64a05-104">L’aide vocale de Cortana est prise en charge dans les applications mobiles iOS et Android de Microsoft Teams, et sur les écrans de Microsoft Teams, uniquement pour les utilisateurs aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="64a05-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="64a05-105">Ce service n’est actuellement pas disponible pour les clients GCC et GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="64a05-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="64a05-106">L’élargissement vers des langues et régions supplémentaires interviendront dans le cadre des versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="64a05-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="64a05-107">L’aide vocale de Cortana dans l’application mobile teams et sur les appareils d’affichage de Microsoft teams permet aux utilisateurs de Microsoft 365 entreprise de rationaliser les tâches liées aux communications, à la collaboration et aux réunions en langage naturel parlé.</span><span class="sxs-lookup"><span data-stu-id="64a05-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="64a05-108">Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du micro situé dans le coin supérieur droit de l’application mobile teams ou en disant &#8220;Cortana&#8221; dans l’affichage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64a05-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="64a05-109">Pour communiquer rapidement avec son équipe mains libres et Pendant que vous êtes en ligne, les utilisateurs peuvent prononcer des requêtes telles que &#8220;appeler Megan&#8221; ou &#8220;envoyer un message à ma prochaine réunion&#8221;.</span><span class="sxs-lookup"><span data-stu-id="64a05-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="64a05-110">Les utilisateurs peuvent également participer à des réunions en disant &#8220;participer à ma prochaine réunion&#8221; et utiliser l’aide vocale pour partager des fichiers, consulter leur calendrier, etc.</span><span class="sxs-lookup"><span data-stu-id="64a05-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="64a05-111">Ces expériences d’assistance vocale sont distribuées à l’aide des [services Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) à l’échelle de l’entreprise qui respectent pleinement les engagements relatifs à la confidentialité, la sécurité et la conformité d’Office 365, tels qu’ils sont énoncés dans les [conditions de services en ligne (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="64a05-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="64a05-112">L’image montre l’envoi d’une discussion avec Cortana sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="64a05-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Image illustrant une séquence d’écrans mobiles montrant une session de conversation Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="64a05-114">Contrôle et limitations d’administration</span><span class="sxs-lookup"><span data-stu-id="64a05-114">Admin control and limitations</span></span>

<span data-ttu-id="64a05-115">Le service d’aide vocale de Cortana dans teams est fourni à l’aide de services qui respectent pleinement les engagements en matière de confidentialité, de sécurité et de conformité d’Office 365 dans le cadre des conditions d’utilisation des services en ligne (OST).</span><span class="sxs-lookup"><span data-stu-id="64a05-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="64a05-116">Par défaut, la fonctionnalité est activée pour les clients.</span><span class="sxs-lookup"><span data-stu-id="64a05-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="64a05-117">Les administrateurs de clients peuvent contrôler qui, au sein de leur client, peuvent utiliser l’aide vocale de Cortana dans teams à l’aide d’une stratégie (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="64a05-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="64a05-118">Cette stratégie peut être définie au niveau du compte d’utilisateur ou du client.</span><span class="sxs-lookup"><span data-stu-id="64a05-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="64a05-119">Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode dans ce contrôle de stratégie pour déterminer si Cortana est désactivée, activée avec un appel de bouton de transmission uniquement, ou à l’aide de la fonctionnalité de mise en éveil de Word (en ce qui concerne les appareils qui la prennent en charge, tels que l’affichage de Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="64a05-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="64a05-120">Les administrateurs peuvent utiliser les applets de commande PowerShell suivantes pour gérer cette stratégie (la stratégie n’est pas disponible actuellement dans le centre d’administration Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="64a05-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="64a05-121">Nouveau-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="64a05-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="64a05-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="64a05-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="64a05-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="64a05-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="64a05-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="64a05-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="64a05-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="64a05-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="64a05-126">Par exemple, la commande ci-dessous crée une stratégie portant le nom &#8220;EmployeeCortanaPolicy&#8221; l’endroit où l’aide vocale Cortana dans Microsoft teams est désactivée.</span><span class="sxs-lookup"><span data-stu-id="64a05-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="64a05-127">Cet exemple illustre la mise à jour d’une stratégie existante portant le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft teams avec l’appel de bouton de déplacement uniquement.</span><span class="sxs-lookup"><span data-stu-id="64a05-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="64a05-128">Les utilisateurs peuvent appeler Cortana en sélectionnant le bouton micro de Cortana dans Teams.</span><span class="sxs-lookup"><span data-stu-id="64a05-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="64a05-129">Mettre en éveil Word (&#8220;Hey Cortana&#8221; ou &#8220;l’appel de Cortana&#8221;) sera désactivé.</span><span class="sxs-lookup"><span data-stu-id="64a05-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="64a05-130">Cet exemple illustre la mise à jour de la stratégie et l’activation de l’assistance vocale de Cortana avec les boutons bascule et l’appel de mise en éveil de Word.</span><span class="sxs-lookup"><span data-stu-id="64a05-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="64a05-131">Au moment de la publication initiale pour les utilisateurs de Microsoft 365 entreprise aux États-Unis en anglais, l’application mobile Teams ne prend pas en charge l’activation en éveil de Word, mais elle sera prise en charge à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="64a05-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="64a05-132">La mise en éveil de Word est activée sur les appareils d’affichage de Microsoft teams à la version initiale.</span><span class="sxs-lookup"><span data-stu-id="64a05-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="64a05-133">Contrôle utilisateur</span><span class="sxs-lookup"><span data-stu-id="64a05-133">User control</span></span>

<span data-ttu-id="64a05-134">Les utilisateurs individuels peuvent essayer l’assistance vocale de Cortana dans l’application mobile teams en sélectionnant le bouton microphone.</span><span class="sxs-lookup"><span data-stu-id="64a05-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="64a05-135">Pour tester l’aide vocale de Cortana sur les appareils Microsoft Teams, il suffit de savoir &#8220;Cortana. &#8221; ils peuvent également contrôler si Cortana est activée dans teams à l’aide d’un paramètre dans l’application mobile teams ou dans l’affichage Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64a05-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="64a05-136">Ouvrez l’application mobile teams ou accédez à l’écran ambiant (accueil) de l’affichage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64a05-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="64a05-137">Dans l’application mobile Teams, accédez à **paramètres** .</span><span class="sxs-lookup"><span data-stu-id="64a05-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="64a05-138">Dans l’affichage de Microsoft Teams, sélectionnez l’avatar de l’utilisateur, puis sélectionnez Paramètres.</span><span class="sxs-lookup"><span data-stu-id="64a05-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="64a05-139">Si Cortana est activée, par exemple, &#8220;Cortana, accédez à paramètres. &#8221;</span><span class="sxs-lookup"><span data-stu-id="64a05-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="64a05-140">Sélectionnez **Cortana** .</span><span class="sxs-lookup"><span data-stu-id="64a05-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="64a05-141">Positionnez le bouton bascule sur **activé** ou **désactivé** , selon que vous souhaitez ou non l’assistance vocale de Cortana sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="64a05-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
