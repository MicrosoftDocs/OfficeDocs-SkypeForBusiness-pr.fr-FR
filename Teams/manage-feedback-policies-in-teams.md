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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les stratégies de commentaires pour contrôler si les utilisateurs teams de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540952"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="0d038-103">Gérer les stratégies de commentaires dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0d038-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0d038-104">Les utilisateurs peuvent envoyer des commentaires et des suggestions concernant teams à \*\*\*\* > \*\*\*\* Microsoft en accédant à des commentaires dans les clients Teams.</span><span class="sxs-lookup"><span data-stu-id="0d038-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="0d038-105">Nous cherchons constamment à améliorer l’expérience d’équipe et nous utilisons ces commentaires pour améliorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="0d038-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Capture d’écran de l’option envoyer des commentaires dans Microsoft teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="0d038-107">Les données envoyées par le biais de **Commentaires** sont considérées comme des «données de support» dans votre contrat 365 Office, y compris des informations qui seraient considérées comme «données client» ou «données personnelles».</span><span class="sxs-lookup"><span data-stu-id="0d038-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="0d038-108">Définir si les utilisateurs peuvent envoyer des commentaires sur teams à Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d038-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="0d038-109">En tant qu’administrateur, vous pouvez contrôler si les utilisateurs de votre organisation peuvent envoyer des commentaires sur teams à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d038-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="0d038-110">Par défaut, tous les utilisateurs de votre organisation reçoivent automatiquement la stratégie globale par défaut de l’organisation et la fonctionnalité est activée dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0d038-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="0d038-111">L’exception est teams pour l’éducation, où la fonctionnalité est activée pour les enseignants et désactivée pour les étudiants.</span><span class="sxs-lookup"><span data-stu-id="0d038-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="0d038-112">Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0d038-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="0d038-113">Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d038-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="0d038-114">Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d038-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="0d038-115">Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="0d038-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="0d038-116">Par exemple, supposons que vous souhaitiez permettre à tous les utilisateurs de votre organisation d’envoyer des commentaires à l’exception des nouvelles recrues dans la formation.</span><span class="sxs-lookup"><span data-stu-id="0d038-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="0d038-117">Dans ce scénario, vous créez une stratégie personnalisée pour désactiver cette fonctionnalité et l’affecter aux nouvelles recrues.</span><span class="sxs-lookup"><span data-stu-id="0d038-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="0d038-118">Tous les autres utilisateurs de votre organisation obtiennent la politique globale avec la fonction activée.</span><span class="sxs-lookup"><span data-stu-id="0d038-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="0d038-119">Vous pouvez utiliser l’applet de nouvelle applet de **nouveau-CsTeamsFeedbackPolicy** pour créer une stratégie personnalisée et l’applet de passe **Grant-CsTeamsFeedbackPolicy** pour l’attribuer à un ou plusieurs utilisateurs ou groupes d’utilisateurs, par exemple un groupe de sécurité ou un groupe de distribution.</span><span class="sxs-lookup"><span data-stu-id="0d038-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="0d038-120">Définissez le paramètre **userInitiatedMode** sur **Enabled** pour autoriser les utilisateurs auxquels une stratégie est affectée pour formuler des commentaires.</span><span class="sxs-lookup"><span data-stu-id="0d038-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="0d038-121">Le fait de définir \*\*\*\* le paramètre sur Disabled désactive la fonctionnalité et les utilisateurs qui ont reçu la stratégie ne peuvent pas envoyer de commentaires.</span><span class="sxs-lookup"><span data-stu-id="0d038-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="0d038-122">Créer une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="0d038-122">Create a custom feedback policy</span></span>

<span data-ttu-id="0d038-123">Dans cet exemple, nous créons une stratégie de commentaires appelée nouvelle politique de commentaires sur les employés et nous désactivons la possibilité d’envoyer des commentaires.</span><span class="sxs-lookup"><span data-stu-id="0d038-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="0d038-124">Assigner une stratégie de commentaires personnalisée</span><span class="sxs-lookup"><span data-stu-id="0d038-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="0d038-125">Assigner une stratégie de commentaires personnalisée à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d038-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="0d038-126">Dans cet exemple, nous affectons une stratégie personnalisée nommée nouvelle stratégie de commentaires d’embauche à un utilisateur nommé User1.</span><span class="sxs-lookup"><span data-stu-id="0d038-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="0d038-127">Assigner une stratégie de commentaires personnalisée aux utilisateurs d’un groupe</span><span class="sxs-lookup"><span data-stu-id="0d038-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="0d038-128">Vous pouvez assigner une stratégie de commentaires personnalisée à plusieurs utilisateurs que vous avez déjà identifiés.</span><span class="sxs-lookup"><span data-stu-id="0d038-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="0d038-129">Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d038-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="0d038-130">Dans cet exemple, nous affectons un exemple de stratégie de commentaires personnalisé appelé nouvelle stratégie de commentaires d’embauche à tous les utilisateurs du groupe contoso New HiRes.</span><span class="sxs-lookup"><span data-stu-id="0d038-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="0d038-131">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="0d038-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="0d038-132">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="0d038-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0d038-133">Attribuez à tous les utilisateurs du groupe une stratégie de commentaires particulière.</span><span class="sxs-lookup"><span data-stu-id="0d038-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="0d038-134">Dans cet exemple, il s’agit de la nouvelle politique de commentaires sur les employés.</span><span class="sxs-lookup"><span data-stu-id="0d038-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="0d038-135">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="0d038-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d038-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d038-136">Related topics</span></span>

- [<span data-ttu-id="0d038-137">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d038-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)