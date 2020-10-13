---
title: Gérer les stratégies de commentaires dans Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs teams de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433037"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="3ba5f-103">Gérer les stratégies de commentaires dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="3ba5f-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3ba5f-104">Les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft pour nous faire savoir ce que nous faisons, directement à partir du bureau et des clients Web Teams.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="3ba5f-105">Nous cherchons constamment à améliorer l’expérience d’équipe et nous utilisons ces commentaires pour améliorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="3ba5f-106">Les stratégies de commentaires ne sont pas disponibles dans les déploiements de GCC, de GCC et de DOD.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="3ba5f-107">**Fonctionnalité envoyer des commentaires**</span><span class="sxs-lookup"><span data-stu-id="3ba5f-107">**The Give feedback feature**</span></span>

<span data-ttu-id="3ba5f-108">Les utilisateurs peuvent **vous**envoyer des commentaires et des suggestions aux équipes pour nous en accédant aux  >  **Commentaires** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="3ba5f-109">Les données envoyées par le biais de **Commentaires** sont considérées comme des « données de support » dans votre contrat Microsoft 365 ou Office 365, y compris des informations qui seraient considérées comme « données client » ou « données personnelles ».</span><span class="sxs-lookup"><span data-stu-id="3ba5f-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Capture d’écran de l’option envoyer des commentaires dans Microsoft teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="3ba5f-111">**Recherches**</span><span class="sxs-lookup"><span data-stu-id="3ba5f-111">**Surveys**</span></span>

<span data-ttu-id="3ba5f-112">Les utilisateurs peuvent également évaluer leur connaissance de Team et nous envoyer des informations sur leur évaluation.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="3ba5f-113">Cette enquête contextuelle s’affiche lorsque les utilisateurs sont en phase d’exécution dans Teams.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="3ba5f-114">Lorsqu’un utilisateur clique sur **Envoyer un commentaire** dans la notification, l’enquête s’affiche pour qu’il soit terminé.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Capture d’écran de la notification de l’enquête et du formulaire dans teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="3ba5f-116">Définir si les utilisateurs peuvent envoyer des commentaires sur teams à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ba5f-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="3ba5f-117">En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft par le biais de **Commentaires** et s’ils reçoivent l’enquête.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="3ba5f-118">Par défaut, tous les utilisateurs de votre organisation disposent automatiquement de la stratégie globale (par défaut de l’organisation par défaut), et la fonctionnalité d' **attribution de commentaires** est activée dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="3ba5f-119">L’exception est teams pour l’éducation, qui est activée pour les enseignants et désactivée pour les étudiants.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="3ba5f-120">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="3ba5f-121">Après avoir modifié la stratégie globale ou affecté une stratégie personnalisée, il est possible que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="3ba5f-122">Par exemple, supposons que vous souhaitiez permettre à tous les utilisateurs de votre organisation d’envoyer des commentaires par le biais de **Commentaires** et de recevoir des enquêtes à l’exception des nouvelles recrues dans la formation.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="3ba5f-123">Dans ce scénario, vous créez une stratégie personnalisée pour désactiver les deux fonctions et les attribuer aux nouvelles recrues.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="3ba5f-124">Tous les autres utilisateurs de votre organisation obtiennent la politique globale avec les fonctionnalités activées.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="3ba5f-125">Vous pouvez gérer les stratégies de commentaires à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="3ba5f-126">Utilisez l’applet **de nouvelle applet de nouveau-CsTeamsFeedbackPolicy** , *qui se [trouve ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, pour créer une stratégie personnalisée et l’applet de passe **Grant-CsTeamsFeedbackPolicy** pour l’attribuer à un ou plusieurs utilisateurs ou groupes d’utilisateurs, comme un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="3ba5f-127">Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3ba5f-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="3ba5f-128">**Envoyer des commentaires**: définissez le paramètre **userInitiatedMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée pour formuler des commentaires.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="3ba5f-129">Le fait de définir le paramètre sur **Disabled** désactive la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne peuvent pas envoyer de commentaires.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="3ba5f-130">**Enquêtes**: définissez le paramètre **receiveSurveysMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée à la réception de l’enquête.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="3ba5f-131">Pour que les utilisateurs reçoivent l’enquête et leur permettent de les refuser, définissez le paramètre sur **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="3ba5f-132">Dans Microsoft Teams, les utilisateurs peuvent accéder aux **paramètres**  >  de**confidentialité** et décider s’ils souhaitent participer aux enquêtes.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="3ba5f-133">La définition du paramètre sur **Disabled** entraîne la désactivation de la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne recevront pas l’enquête.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="3ba5f-134">Créer une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="3ba5f-134">Create a custom feedback policy</span></span>

<span data-ttu-id="3ba5f-135">Dans cet exemple, nous créons une stratégie de commentaires appelée nouvelle politique de commentaires sur les employés et nous désactivons la possibilité de faire part **de vos commentaires et de** l’enquête.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="3ba5f-136">Assigner une stratégie de commentaires personnalisée aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3ba5f-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="3ba5f-137">Dans cet exemple, nous affectons une stratégie personnalisée nommée nouvelle stratégie de commentaires d’embauche à un utilisateur nommé User1.</span><span class="sxs-lookup"><span data-stu-id="3ba5f-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="3ba5f-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="3ba5f-138">Related topics</span></span>

- [<span data-ttu-id="3ba5f-139">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ba5f-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="3ba5f-140">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="3ba5f-140">Assign policies to your users in Teams</span></span>](assign-policies.md)