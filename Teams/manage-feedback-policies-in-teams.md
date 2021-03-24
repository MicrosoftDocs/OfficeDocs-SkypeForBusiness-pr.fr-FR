---
title: Gérer les stratégies de commentaires dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs de Teams dans votre organisation peuvent envoyer des commentaires sur Teams à Microsoft.
ms.openlocfilehash: bc925320959c55b2fa06c8480f1011aab81aae9c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094264"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="fcf42-103">Gérer les stratégies de commentaires dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcf42-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="fcf42-104">Les utilisateurs de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft pour nous faire part de nos interventions, directement à partir des clients de bureau et web Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf42-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="fcf42-105">Nous améliorons continuellement l’expérience Teams et nous utilisons ces commentaires pour améliorer Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf42-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="fcf42-106">Les stratégies de commentaires ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD.</span><span class="sxs-lookup"><span data-stu-id="fcf42-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="fcf42-107">**La fonctionnalité Donner des commentaires**</span><span class="sxs-lookup"><span data-stu-id="fcf42-107">**The Give feedback feature**</span></span>

<span data-ttu-id="fcf42-108">Les utilisateurs peuvent nous envoyer des commentaires et des suggestions concernant Teams en nous aident  >  **à envoyer des commentaires** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf42-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="fcf42-109">Les données  envoyées via l’envoi de commentaires sont considérées comme des « données de support » dans le cadre de votre contrat Microsoft 365 ou Office 365, y compris les informations qui seraient autrement considérées comme « Données client » ou « Données personnelles ».</span><span class="sxs-lookup"><span data-stu-id="fcf42-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Capture d’écran de l’option Donner des commentaires dans Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="fcf42-111">**Enquêtes**</span><span class="sxs-lookup"><span data-stu-id="fcf42-111">**Surveys**</span></span>

<span data-ttu-id="fcf42-112">Les utilisateurs peuvent également évaluer leur expérience avec Teams et nous envoyer des détails sur l’évaluation qu’ils donnent.</span><span class="sxs-lookup"><span data-stu-id="fcf42-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="fcf42-113">Cette enquête pop-up est affichée aux utilisateurs de temps à temps dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fcf42-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="fcf42-114">Lorsqu’un utilisateur clique sur **Fournir des commentaires** dans la notification, l’enquête est affichée pour lui.</span><span class="sxs-lookup"><span data-stu-id="fcf42-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Capture d’écran de la notification et du formulaire d’enquête dans Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="fcf42-116">Définir si les utilisateurs peuvent envoyer des commentaires sur Teams à Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcf42-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="fcf42-117">En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur Teams à Microsoft via l’envoi de commentaires et s’ils reçoivent l’enquête. </span><span class="sxs-lookup"><span data-stu-id="fcf42-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="fcf42-118">Par défaut, tous les utilisateurs de votre organisation se voit automatiquement  attribuer la stratégie globale (à l’échelle de l’organisation par défaut) et la fonctionnalité Donner des commentaires et l’enquête sont activées dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="fcf42-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="fcf42-119">Teams pour l’éducation fait exception, où les fonctionnalités sont activées pour les enseignants et désactivées pour les étudiants.</span><span class="sxs-lookup"><span data-stu-id="fcf42-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="fcf42-120">Vous pouvez modifier la stratégie globale ou créer et affecter une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fcf42-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="fcf42-121">Une fois que vous avez modifié la stratégie globale ou attribué une stratégie personnalisée, l’application des modifications peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="fcf42-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="fcf42-122">Par exemple, vous voulez autoriser tous les utilisateurs  de votre organisation à envoyer des commentaires via l’envoi de commentaires et la réception d’enquêtes à l’exception des nouvelles recrues en formation.</span><span class="sxs-lookup"><span data-stu-id="fcf42-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="fcf42-123">Dans ce scénario, vous créez une stratégie personnalisée pour désactiver à la fois les fonctionnalités et l’affecter à de nouvelles recrues.</span><span class="sxs-lookup"><span data-stu-id="fcf42-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="fcf42-124">Tous les autres utilisateurs de votre organisation obtiennent la stratégie globale avec les fonctionnalités désactivées.</span><span class="sxs-lookup"><span data-stu-id="fcf42-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="fcf42-125">Vous gérez les stratégies de commentaires à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcf42-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="fcf42-126">Utilisez l’cmdlet **New-CsTeamsFeedbackPolicy,** qui est possible *ici, [](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* pour créer une stratégie personnalisée et l’cmdlet **Grant-CsTeamsFeedbackPolicy** pour l’affecter à un ou plusieurs utilisateurs ou groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="fcf42-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="fcf42-127">Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fcf42-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="fcf42-128">**Donnez des** commentaires : Définissez le  **paramètre userInitiatedMode** pour permettre aux utilisateurs affectés à la stratégie de faire part de leurs commentaires.</span><span class="sxs-lookup"><span data-stu-id="fcf42-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="fcf42-129">La désactivation du paramètre **désactive** la fonctionnalité et les utilisateurs à qui la stratégie est attribuée n’ont pas la possibilité d’apporter des commentaires.</span><span class="sxs-lookup"><span data-stu-id="fcf42-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="fcf42-130">**Enquêtes**: définissez le **paramètre ReceiveSurveysMode** pour permettre aux utilisateurs affectés à la stratégie de recevoir l’enquête. </span><span class="sxs-lookup"><span data-stu-id="fcf42-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="fcf42-131">Pour que les utilisateurs reçoivent l’enquête et les autorisent à se désavertr, définissez le paramètre sur **enabledUserOverride.**</span><span class="sxs-lookup"><span data-stu-id="fcf42-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="fcf42-132">Dans Teams, les utilisateurs peuvent ensuite se rendre dans **Paramètres** de confidentialité et choisir  >   s’ils souhaitent participer à des enquêtes.</span><span class="sxs-lookup"><span data-stu-id="fcf42-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="fcf42-133">La désactivation du paramètre **désactive** la fonctionnalité et les utilisateurs à qui la stratégie est attribuée ne recevront pas l’enquête.</span><span class="sxs-lookup"><span data-stu-id="fcf42-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="fcf42-134">Créer une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="fcf42-134">Create a custom feedback policy</span></span>

<span data-ttu-id="fcf42-135">Dans cet exemple, nous créons une stratégie de commentaires appelée Stratégie de commentaires sur les nouvelles recrues et nous cessons la possibilité de donner des commentaires via l’envoi de **commentaires** et l’enquête.</span><span class="sxs-lookup"><span data-stu-id="fcf42-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="fcf42-136">Attribuer une stratégie de commentaires personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fcf42-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="fcf42-137">Dans cet exemple, nous affectons une stratégie personnalisée nommée Stratégie de commentaires sur les nouvelles recrues à un utilisateur nommé utilisateur1.</span><span class="sxs-lookup"><span data-stu-id="fcf42-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="fcf42-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fcf42-138">Related topics</span></span>

- [<span data-ttu-id="fcf42-139">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcf42-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="fcf42-140">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fcf42-140">Assign policies to your users in Teams</span></span>](assign-policies.md)