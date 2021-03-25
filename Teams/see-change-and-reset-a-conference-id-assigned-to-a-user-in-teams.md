---
title: Consulter, modifier et réinitialiser l’ID de conférence d’un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment affecter un ID de conférence à un utilisateur dans Microsoft Teams et ce que doivent être les paramètres d’ID de conférence.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117207"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="dcbef-103">Afficher et réinitialiser un ID de conférence attribué à un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dcbef-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="dcbef-104">Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et qu’il utilise Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="dcbef-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="dcbef-105">L’ID de conférence attribué est envoyé dans l’invitation à la réunion lorsque la réunion est programmée.</span><span class="sxs-lookup"><span data-stu-id="dcbef-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="dcbef-106">Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="dcbef-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="dcbef-107">Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il peut arrive qu’un utilisateur ne souhaite pas utiliser celui-ci et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne se souvenent pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcbef-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="dcbef-108">Vous pouvez utiliser le Centre d’administration de Microsoft Teams ou Windows PowerShell pour afficher, modifier et réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="dcbef-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="dcbef-109">Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="dcbef-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="dcbef-110">Pour [plus d’informations sur](reset-a-conference-id-for-a-user-in-teams.md) la réinitialisation du code confidentiel d’un organisateur de conférence, voir Réinitialiser l’ID de conférence d’un utilisateur dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dcbef-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="dcbef-111">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dcbef-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="dcbef-112">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dcbef-112">To view the conference ID</span></span>

<span data-ttu-id="dcbef-113">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="dcbef-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="dcbef-114">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="dcbef-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dcbef-115">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="dcbef-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="dcbef-116">Sous **Audioconférence,** regardez sous **ID de conférence.**</span><span class="sxs-lookup"><span data-stu-id="dcbef-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="dcbef-117">Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message  électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur Envoyer les informations sur la conférence dans un lien électronique.</span><span class="sxs-lookup"><span data-stu-id="dcbef-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="dcbef-118">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="dcbef-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="dcbef-119">Pour plus [d’informations,](/powershell/module/teams/?view=teams-ps) consultez la référence Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcbef-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="dcbef-120">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dcbef-120">To reset the conference ID</span></span>

<span data-ttu-id="dcbef-121">Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.</span><span class="sxs-lookup"><span data-stu-id="dcbef-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="dcbef-122">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="dcbef-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="dcbef-123">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="dcbef-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dcbef-124">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="dcbef-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="dcbef-125">Sous **Audioconférence,** cliquez sur **Réinitialiser l’ID de conférence.**</span><span class="sxs-lookup"><span data-stu-id="dcbef-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="dcbef-126">Dans la fenêtre **Réinitialiser l’ID de conférence,** cliquez sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="dcbef-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="dcbef-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="dcbef-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="dcbef-128">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="dcbef-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="dcbef-129">Pour plus [d’informations,](/powershell/module/teams/?view=teams-ps) consultez la référence Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcbef-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="dcbef-130">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dcbef-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="dcbef-131">Une fois qu’un nouvel ID de conférence est créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="dcbef-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="dcbef-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="dcbef-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="dcbef-133">L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="dcbef-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="dcbef-134">Vous ne pouvez pas utiliser de caractères alphabéétiques ou spéciaux dans les ID de conférence. seuls des nombres peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="dcbef-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dcbef-135">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="dcbef-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="dcbef-136">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="dcbef-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dcbef-137">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="dcbef-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="dcbef-138">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="dcbef-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dcbef-139">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="dcbef-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="dcbef-140">[Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="dcbef-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="dcbef-141">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="dcbef-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="dcbef-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="dcbef-142">Related topics</span></span>

[<span data-ttu-id="dcbef-143">Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="dcbef-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)