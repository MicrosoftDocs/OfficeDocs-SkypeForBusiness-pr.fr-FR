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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs teams de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.
ms.openlocfilehash: e43cc46e16a17ad4f059398e99736d14fdee62ee
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570632"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="67842-103">Gérer les stratégies de commentaires dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="67842-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="67842-104">Les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft pour nous faire savoir ce que nous faisons, directement à partir du bureau et des clients Web Teams.</span><span class="sxs-lookup"><span data-stu-id="67842-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="67842-105">Nous cherchons constamment à améliorer l’expérience d’équipe et nous utilisons ces commentaires pour améliorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="67842-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="67842-106">**Fonctionnalité envoyer des commentaires**</span><span class="sxs-lookup"><span data-stu-id="67842-106">**The Give feedback feature**</span></span>

<span data-ttu-id="67842-107">Les utilisateurs peuvent **vous** > envoyer des commentaires et des suggestions aux équipes pour nous en accédant aux**Commentaires** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="67842-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="67842-108">Les données envoyées par le biais de **Commentaires** sont considérées comme des « données de support » dans votre contrat 365 Office, y compris des informations qui seraient considérées comme « données client » ou « données personnelles ».</span><span class="sxs-lookup"><span data-stu-id="67842-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Capture d’écran de l’option envoyer des commentaires dans Microsoft teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="67842-110">**Recherches**</span><span class="sxs-lookup"><span data-stu-id="67842-110">**Surveys**</span></span>

<span data-ttu-id="67842-111">Les utilisateurs peuvent également évaluer leur connaissance de Team et nous envoyer des informations sur leur évaluation.</span><span class="sxs-lookup"><span data-stu-id="67842-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="67842-112">Cette enquête contextuelle s’affiche lorsque les utilisateurs sont en phase d’exécution dans Teams.</span><span class="sxs-lookup"><span data-stu-id="67842-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="67842-113">Lorsqu’un utilisateur clique sur **Envoyer un commentaire** dans la notification, l’enquête s’affiche pour qu’il soit terminé.</span><span class="sxs-lookup"><span data-stu-id="67842-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Capture d’écran de la notification de l’enquête et du formulaire dans teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="67842-115">Définir si les utilisateurs peuvent envoyer des commentaires sur teams à Microsoft</span><span class="sxs-lookup"><span data-stu-id="67842-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="67842-116">En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft par le biais de **Commentaires** et s’ils reçoivent l’enquête.</span><span class="sxs-lookup"><span data-stu-id="67842-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="67842-117">Par défaut, tous les utilisateurs de votre organisation disposent automatiquement de la stratégie globale (par défaut de l’organisation par défaut), et la fonctionnalité d' **attribution de commentaires** est activée dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="67842-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="67842-118">L’exception est teams pour l’éducation, qui est activée pour les enseignants et désactivée pour les étudiants.</span><span class="sxs-lookup"><span data-stu-id="67842-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="67842-119">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="67842-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="67842-120">Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="67842-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="67842-121">Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="67842-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="67842-122">Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="67842-122">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="67842-123">Par exemple, supposons que vous souhaitiez permettre à tous les utilisateurs de votre organisation d’envoyer des commentaires par le biais de **Commentaires** et de recevoir des enquêtes à l’exception des nouvelles recrues dans la formation.</span><span class="sxs-lookup"><span data-stu-id="67842-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="67842-124">Dans ce scénario, vous créez une stratégie personnalisée pour désactiver les deux fonctions et les attribuer aux nouvelles recrues.</span><span class="sxs-lookup"><span data-stu-id="67842-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="67842-125">Tous les autres utilisateurs de votre organisation obtiennent la politique globale avec les fonctionnalités activées.</span><span class="sxs-lookup"><span data-stu-id="67842-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="67842-126">Vous pouvez utiliser l’applet **de nouvelle applet de nouveau-CsTeamsFeedbackPolicy** , \* [disponible ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)\*, pour créer une stratégie personnalisée et l’applet de passe **Grant-CsTeamsFeedbackPolicy** pour l’attribuer à un ou plusieurs utilisateurs ou groupes d’utilisateurs, comme un groupe de sécurité ou Groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="67842-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="67842-127">Pour désactiver et activer les fonctionnalités, définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="67842-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="67842-128">**Envoyer des commentaires**: définissez le paramètre **userInitiatedMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée pour formuler des commentaires.</span><span class="sxs-lookup"><span data-stu-id="67842-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="67842-129">Le fait de définir le paramètre sur **Disabled** désactive la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne peuvent pas envoyer de commentaires.</span><span class="sxs-lookup"><span data-stu-id="67842-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="67842-130">**Enquêtes**: définissez le paramètre **receiveSurveysMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée à la réception de l’enquête.</span><span class="sxs-lookup"><span data-stu-id="67842-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="67842-131">Pour que les utilisateurs reçoivent l’enquête et leur permettent de les refuser, définissez le paramètre sur **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="67842-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="67842-132">Dans Microsoft Teams, les utilisateurs peuvent accéder aux **paramètres** > de**confidentialité** et décider s’ils souhaitent participer aux enquêtes.</span><span class="sxs-lookup"><span data-stu-id="67842-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="67842-133">La définition du paramètre sur **Disabled** entraîne la désactivation de la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne recevront pas l’enquête.</span><span class="sxs-lookup"><span data-stu-id="67842-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="67842-134">Créer une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="67842-134">Create a custom feedback policy</span></span>

<span data-ttu-id="67842-135">Dans cet exemple, nous créons une stratégie de commentaires appelée nouvelle politique de commentaires sur les employés et nous désactivons la possibilité de faire part **de vos commentaires et de** l’enquête.</span><span class="sxs-lookup"><span data-stu-id="67842-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="67842-136">Assigner une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="67842-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="67842-137">Assigner une stratégie de commentaires personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="67842-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="67842-138">Dans cet exemple, nous affectons une stratégie personnalisée nommée nouvelle stratégie de commentaires d’embauche à un utilisateur nommé User1.</span><span class="sxs-lookup"><span data-stu-id="67842-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="67842-139">Assigner une stratégie de commentaires personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="67842-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="67842-140">Vous pouvez assigner une stratégie de commentaires personnalisée à plusieurs utilisateurs que vous avez déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="67842-140">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="67842-141">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="67842-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="67842-142">Dans cet exemple, nous affectons un exemple de stratégie de commentaires personnalisé appelé nouvelle stratégie de commentaires d’embauche à tous les utilisateurs du groupe contoso New HiRes.</span><span class="sxs-lookup"><span data-stu-id="67842-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="67842-143">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="67842-143">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="67842-144">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="67842-144">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="67842-145">Attribuez à tous les utilisateurs du groupe une stratégie de commentaires particulière.</span><span class="sxs-lookup"><span data-stu-id="67842-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="67842-146">Dans cet exemple, il s’agit de la nouvelle politique de commentaires sur les employés.</span><span class="sxs-lookup"><span data-stu-id="67842-146">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="67842-147">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="67842-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67842-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67842-148">Related topics</span></span>

- [<span data-ttu-id="67842-149">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="67842-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)