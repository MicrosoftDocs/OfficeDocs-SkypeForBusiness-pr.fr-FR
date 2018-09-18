---
title: Afficher, modifier et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence dans Microsoft Teams et quels sont les paramètres d’ID de conférence obligatoires. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892032"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="307c4-103">Afficher et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="307c4-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

<span data-ttu-id="307c4-104">Un ID de conférence est attribué automatiquement à un utilisateur de Microsoft Teams lorsque l’audioconférence est activée pour lui dans Office 365 et qu'il utilise Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="307c4-104">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="307c4-105">L'ID de conférence attribué est envoyé dans l'invitation à participer à la réunion lors de sa planification.</span><span class="sxs-lookup"><span data-stu-id="307c4-105">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="307c4-106">Chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="307c4-106">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="307c4-107">Bien qu'un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu'un utilisateur ne souhaite pas utiliser cet ID et préfère le définir sur un numéro spécifique, ou qu’il ne se rappelle pas de son ID de conférence ou l’ait perdu.</span><span class="sxs-lookup"><span data-stu-id="307c4-107">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="307c4-108">Vous pouvez utiliser le centre d'administration de Microsoft Teams ou Windows PowerShell pour afficher, modifier et réinitialiser son ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="307c4-108">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="307c4-109">Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="307c4-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="307c4-110">Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="307c4-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="307c4-111">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="307c4-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="307c4-112">Pour afficher l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="307c4-112">To reset the meeting conference ID</span></span>

<span data-ttu-id="307c4-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="307c4-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="307c4-114">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="307c4-114">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="307c4-115">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="307c4-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="307c4-116">Sous **Audioconférence**, recherchez l’**ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="307c4-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="307c4-117">Vous pouvez envoyer toutes les informations sur la conférence à l'utilisateur dans un courrier électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur le lien **Envoyer les informations de la conférence dans un courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="307c4-117">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span>
  
<span data-ttu-id="307c4-118">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="307c4-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="307c4-119">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="307c4-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="307c4-120">Pour réinitialiser l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="307c4-120">To reset the meeting conference ID</span></span>

<span data-ttu-id="307c4-121">Si un utilisateur a oublié son ID de conférence, par exemple, vous pouvez le réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="307c4-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="307c4-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="307c4-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="307c4-123">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="307c4-123">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="307c4-124">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="307c4-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="307c4-125">Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="307c4-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="307c4-126">Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="307c4-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="307c4-127">Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="307c4-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="307c4-128">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="307c4-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="307c4-129">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="307c4-129">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="307c4-130">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="307c4-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="307c4-131">Une fois qu'un nouvel ID de conférence est créé ou réinitialisé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="307c4-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="307c4-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="307c4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="307c4-133">L'ID de conférence doit respecter le nombre de chiffres défini dans le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="307c4-133">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="307c4-134">Les ID de conférence ne doivent comporter que des chiffres, jamais des caractères alphabétiques ou spéciaux.</span><span class="sxs-lookup"><span data-stu-id="307c4-134">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>
    
- <span data-ttu-id="307c4-135">L'ID de conférence comporte 7 chiffres par défaut pour tous les utilisateurs d’audioconférence. Il n'est pas possible de modifier le nombre de chiffres.</span><span class="sxs-lookup"><span data-stu-id="307c4-135">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="307c4-136">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="307c4-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="307c4-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="307c4-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="307c4-140">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="307c4-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="307c4-141">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="307c4-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="307c4-142">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="307c4-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="307c4-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="307c4-143">Related topics</span></span>

[<span data-ttu-id="307c4-144">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="307c4-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

