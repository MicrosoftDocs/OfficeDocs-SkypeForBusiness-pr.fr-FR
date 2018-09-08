---
title: Afficher, modifier et réinitialiser un ID de conférence affecté à un utilisateur de Microsoft Teams
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
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur de Microsoft Teams et quels la conférence ID paramètres doivent être. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892032"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="b48e2-103">Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b48e2-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="b48e2-104">Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’ils sont configurés pour les services d’audioconférence dans Office 365 et utilisent Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b48e2-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b48e2-105">L’ID de conférence affecté est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée.</span><span class="sxs-lookup"><span data-stu-id="b48e2-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="b48e2-106">Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="b48e2-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="b48e2-107">Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou lorsque les utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="b48e2-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="b48e2-108">Vous pouvez utiliser le centre d’administration de Microsoft Teams ou de Windows PowerShell pour afficher, modifier et de réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="b48e2-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="b48e2-109">Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="b48e2-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="b48e2-110">Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b48e2-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="b48e2-111">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="b48e2-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="b48e2-112">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="b48e2-112">To view the conference ID</span></span>

<span data-ttu-id="b48e2-113">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="b48e2-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="b48e2-114">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b48e2-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b48e2-115">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b48e2-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b48e2-116">Sous l' **Audioconférence**, examinez les **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="b48e2-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="b48e2-117">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence dans le message électronique** .</span><span class="sxs-lookup"><span data-stu-id="b48e2-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="b48e2-118">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b48e2-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b48e2-119">Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b48e2-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="b48e2-120">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="b48e2-120">To reset the conference ID</span></span>

<span data-ttu-id="b48e2-121">Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.</span><span class="sxs-lookup"><span data-stu-id="b48e2-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="b48e2-122">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="b48e2-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="b48e2-123">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b48e2-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b48e2-124">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b48e2-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b48e2-125">Sous **Conférence Audio**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="b48e2-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="b48e2-126">Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="b48e2-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="b48e2-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="b48e2-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="b48e2-128">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b48e2-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b48e2-129">Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b48e2-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="b48e2-130">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b48e2-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="b48e2-131">Une fois un nouvel ID de conférence est créé ou une est réinitialisée, l’ancien ID de conférence ne peut être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="b48e2-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b48e2-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="b48e2-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="b48e2-133">L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b48e2-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="b48e2-134">Vous ne pouvez pas utiliser des caractères alphabétiques ou spéciaux conférence ID ; Seuls les nombres peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="b48e2-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="b48e2-135">L’ID de conférence pour tous vos utilisateurs de conférence audio sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="b48e2-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b48e2-136">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="b48e2-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b48e2-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b48e2-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b48e2-140">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b48e2-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b48e2-141">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="b48e2-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b48e2-142">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b48e2-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b48e2-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b48e2-143">Related topics</span></span>

[<span data-ttu-id="b48e2-144">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="b48e2-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

