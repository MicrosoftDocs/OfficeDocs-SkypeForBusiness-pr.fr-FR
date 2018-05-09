---
title: Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler les organisateurs utilisation numéros gratuits pour leurs réunions.
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="bbdbf-103">Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="bbdbf-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="bbdbf-104">Si votre organisation dispose de numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="bbdbf-105">Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="bbdbf-106">Si ce n’est pas le comportement souhaité pour certains utilisateurs au sein de votre organisation, vous pouvez empêcher des utilisateurs spécifiques d’à l’aide de ces numéros dans leurs réunions via un contrôle activation du numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="bbdbf-107">Lorsque les numéros gratuits sont désactivés pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="bbdbf-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="bbdbf-108">Un numéro gratuit sera n’est plus inclus dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="bbdbf-109">Numéros gratuits ne sont plus apparaît sur la page « Rechercher un numéro local » qui est référencée dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="bbdbf-110">Les participants ne puissent pas participer à la réunion de l’organisateur donné si elles composer un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="bbdbf-111">Replanifier automatiquement toutes les réunions de l’organisateur et le numéro gratuit sera supprimé à partir de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="bbdbf-112">Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="bbdbf-113">Les participants peuvent poursuivre la participation à des réunions de l’organisateur à l’aide des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="bbdbf-114">Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="bbdbf-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="bbdbf-115">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="bbdbf-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bbdbf-116">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="bbdbf-117">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bbdbf-118">Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="bbdbf-119">Dans le volet de **fournisseur de pont de conférence** , désactivez **Autoriser à l’aide des numéros gratuits dans le pont de conférence de votre organisation à participer à des réunions de cet utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="bbdbf-120">Cliquez sur **s’appliquent.**</span><span class="sxs-lookup"><span data-stu-id="bbdbf-120">Click **Apply.**</span></span> 

<span data-ttu-id="bbdbf-121">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="bbdbf-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="bbdbf-122">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="bbdbf-123">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="bbdbf-124">Désactivez **Autoriser à l’aide des numéros de téléphone gratuits pour participer à des réunions de cet utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="bbdbf-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="bbdbf-126">**À l’aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bbdbf-126">**Using PowerShell**</span></span>  

<span data-ttu-id="bbdbf-127">Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle.</span><span class="sxs-lookup"><span data-stu-id="bbdbf-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="bbdbf-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bbdbf-128">For example:</span></span> 

 - <span data-ttu-id="bbdbf-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="bbdbf-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
