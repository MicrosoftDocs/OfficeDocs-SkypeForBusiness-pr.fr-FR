---
title: Désactivation des numéros verts pour des utilisateurs spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Les administrateurs peuvent contrôler comment les organisateurs peuvent utiliser des numéros de téléphone gratuits pour leurs réunions.
ms.openlocfilehash: d0b7703f4dd518caa5ffb339282c5a7bbac4daa3
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="4e027-103">Désactivation des numéros verts pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="4e027-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="4e027-104">Si votre organisation a des numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4e027-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="4e027-105">Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros de téléphone gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants pour joindre leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="4e027-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="4e027-106">S’il ne s’agit pas d’un comportement souhaitable pour certains utilisateurs de votre organisation, vous pouvez interdire aux utilisateurs spécifiques à l’aide de ces numéros dans leurs réunions via un contrôle d’activation numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="4e027-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="4e027-107">Lorsque les numéros verts sont désactivées pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="4e027-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="4e027-108">Un numéro d’appel gratuit sera n’est plus inclus dans son ou son invite.</span><span class="sxs-lookup"><span data-stu-id="4e027-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4e027-109">Numéros gratuits ne sont plus apparaît sur la page « Trouver un numéro local » qui est référencée dans son ou son invite.</span><span class="sxs-lookup"><span data-stu-id="4e027-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4e027-110">Les participants ne pourra pas participer à la conférence de l’organisateur donné si elles composer un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4e027-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="4e027-111">Toutes les réunions de l’organisateur seront automatiquement replanifiées, et le numéro d’appel gratuit sera supprimé à partir de ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="4e027-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="4e027-112">Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="4e027-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="4e027-113">Les participants peuvent continuer de participation à des réunions de la bibliothèque multimédia à l’aide des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="4e027-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="4e027-114">Désactivation des numéros verts pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="4e027-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="4e027-115">**À l’aide de Skype les équipes Microsoft pour Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="4e027-115">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4e027-116">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="4e027-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="4e027-117">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4e027-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4e027-118">Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4e027-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="4e027-119">Dans le volet de **fournisseur de pont de conférence** , désactivez **Autoriser à l’aide des numéros d’appel gratuits dans le pont de conférence de l’organisation à assister aux réunions de cet utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="4e027-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="4e027-120">Cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="4e027-120">Click **Apply.**</span></span> 

<span data-ttu-id="4e027-121">Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4e027-121">**Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4e027-122">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="4e027-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="4e027-123">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4e027-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="4e027-124">Désactivez **Autoriser à l’aide de numéros de téléphone gratuits pour assister aux réunions de cet utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="4e027-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="4e027-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4e027-125">Click **Save**.</span></span> 
 
<span data-ttu-id="4e027-126">**Utilisation de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4e027-126">**Using PowerShell**</span></span>  

<span data-ttu-id="4e027-127">Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle.</span><span class="sxs-lookup"><span data-stu-id="4e027-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="4e027-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4e027-128">For example:</span></span> 

 - <span data-ttu-id="4e027-129">User@contoso.com Set-CsOnlineDialInConferencingUser-AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="4e027-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
