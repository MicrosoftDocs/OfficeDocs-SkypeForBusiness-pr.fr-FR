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
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691150"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="92b24-103">Afficher et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92b24-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="92b24-104">Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et qu’il utilise Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="92b24-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="92b24-105">L'ID de conférence attribué est envoyé dans l'invitation à participer à la réunion lors de sa planification.</span><span class="sxs-lookup"><span data-stu-id="92b24-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="92b24-106">Chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="92b24-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="92b24-107">Bien qu'un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu'un utilisateur ne souhaite pas utiliser cet ID et préfère le définir sur un numéro spécifique, ou qu’il ne se rappelle pas de son ID de conférence ou l’ait perdu.</span><span class="sxs-lookup"><span data-stu-id="92b24-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="92b24-108">Vous pouvez utiliser le centre d'administration de Microsoft Teams ou Windows PowerShell pour afficher, modifier et réinitialiser son ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="92b24-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="92b24-109">Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="92b24-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="92b24-110">Pour [plus d’informations sur](reset-a-conference-id-for-a-user-in-teams.md) la réinitialisation du code confidentiel d’un organisateur de conférence, voir Réinitialiser l’ID de conférence d’un utilisateur dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="92b24-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="92b24-111">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="92b24-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="92b24-112">Pour afficher l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="92b24-112">To view the conference ID</span></span>

<span data-ttu-id="92b24-113">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="92b24-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="92b24-114">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="92b24-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="92b24-115">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="92b24-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="92b24-116">Sous **Audioconférence**, recherchez l’**ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="92b24-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="92b24-117">Vous pouvez envoyer toutes les informations sur la conférence à l'utilisateur dans un courrier électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur le lien **Envoyer les informations de la conférence dans un courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="92b24-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="92b24-118">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="92b24-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="92b24-119">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="92b24-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="92b24-120">Pour réinitialiser l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="92b24-120">To reset the conference ID</span></span>

<span data-ttu-id="92b24-121">Si un utilisateur a oublié son ID de conférence, par exemple, vous pouvez le réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="92b24-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="92b24-122">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="92b24-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="92b24-123">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="92b24-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="92b24-124">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="92b24-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="92b24-125">Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="92b24-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="92b24-126">Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="92b24-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="92b24-127">Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92b24-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="92b24-128">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="92b24-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="92b24-129">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="92b24-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="92b24-130">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="92b24-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="92b24-131">Une fois qu'un nouvel ID de conférence est créé ou réinitialisé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="92b24-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="92b24-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="92b24-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="92b24-133">L'ID de conférence doit respecter le nombre de chiffres défini dans le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="92b24-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="92b24-134">Les ID de conférence ne doivent comporter que des chiffres, jamais des caractères alphabétiques ou spéciaux.</span><span class="sxs-lookup"><span data-stu-id="92b24-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="92b24-135">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="92b24-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="92b24-136">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="92b24-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="92b24-137">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="92b24-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="92b24-138">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="92b24-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="92b24-139">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="92b24-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="92b24-140">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92b24-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="92b24-141">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="92b24-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="92b24-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="92b24-142">Related topics</span></span>

[<span data-ttu-id="92b24-143">Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="92b24-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
