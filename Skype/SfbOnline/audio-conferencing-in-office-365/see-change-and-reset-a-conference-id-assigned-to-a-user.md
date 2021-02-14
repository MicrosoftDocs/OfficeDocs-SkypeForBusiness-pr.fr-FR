---
title: Consulter, modifier et réinitialiser un ID de conférence attribué à un utilisateur dans Skype Entreprise Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment affecter un ID de conférence à un utilisateur dans Skype Entreprise Online et ce que doivent être les paramètres d’ID de conférence. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643604"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="dec3a-103">Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dec3a-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="dec3a-104">Pour plus d’informations sur les ID de conférence utilisateur dans Microsoft Teams, consultez et réinitialisez un ID de conférence attribué à un [utilisateur dans Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="dec3a-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="dec3a-p101">Un ID de conférence est automatiquement attribué à un utilisateur Skype Entreprise lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence attribué est envoyé dans l’invitation à la réunion lorsque la réunion est programmée. Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="dec3a-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="dec3a-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="dec3a-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="dec3a-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="dec3a-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="dec3a-112">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dec3a-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="dec3a-113">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dec3a-113">To view the conference ID</span></span>

<span data-ttu-id="dec3a-114">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="dec3a-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="dec3a-115">Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="dec3a-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="dec3a-116">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="dec3a-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="dec3a-117">Allez au Centre d'> **dans Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="dec3a-118">Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="dec3a-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="dec3a-119">Dans la page Action, affichez la section **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="dec3a-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="dec3a-120">Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message  électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur Envoyer les informations sur la conférence par courrier électronique après avoir sélectionné l’utilisateur dans la **page** Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="dec3a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="dec3a-121">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="dec3a-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="dec3a-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="dec3a-124">Pour en savoir plus sur l’cmdlet, voir [Get-CsOnlineDialInConferencingUser.](https://go.microsoft.com/fwlink/?LinkId=617693 )</span><span class="sxs-lookup"><span data-stu-id="dec3a-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="dec3a-125">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="dec3a-125">To reset the conference ID</span></span>

<span data-ttu-id="dec3a-126">Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.</span><span class="sxs-lookup"><span data-stu-id="dec3a-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="dec3a-127">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="dec3a-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="dec3a-128">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="dec3a-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="dec3a-129">Allez au Centre d'> **dans Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="dec3a-130">Dans le **Centre d’administration Skype** Entreprise Utilisateurs de l’audioconférence, dans le volet Action sous ID de >    >  conférence, cliquez sur  **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="dec3a-131">Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="dec3a-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="dec3a-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="dec3a-133">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="dec3a-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="dec3a-134">Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dec3a-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="dec3a-135">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="dec3a-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="dec3a-136">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dec3a-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="dec3a-137">Une fois qu’un nouvel ID de conférence est créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="dec3a-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="dec3a-138">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="dec3a-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="dec3a-139">Les utilisateurs peuvent utiliser l’outil de migration de réunions Skype Entreprise pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="dec3a-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="dec3a-140">Pour découvrir comment télécharger, installer et exécuter l’outil, consultez : Outil de mise à jour des réunions pour Skype Entreprise et [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Entreprise Online, Outil de migration de réunions [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et Skype Entreprise Online, Outil de migration de réunions [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="dec3a-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="dec3a-141">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="dec3a-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="dec3a-142">L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="dec3a-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="dec3a-143">Vous ne pouvez pas utiliser de caractères alphabéétiques ou spéciaux dans les ID de conférence. seuls des nombres peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="dec3a-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="dec3a-144">L’ID de conférence de tous vos utilisateurs d’audioconférence aura neuf chiffres par défaut et le nombre de chiffres ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="dec3a-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="dec3a-145">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="dec3a-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="dec3a-146">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire.</span><span class="sxs-lookup"><span data-stu-id="dec3a-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dec3a-147">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="dec3a-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="dec3a-148">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="dec3a-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="dec3a-149">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dec3a-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="dec3a-150">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="dec3a-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="dec3a-151">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="dec3a-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="dec3a-152">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="dec3a-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="dec3a-153">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dec3a-153">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="dec3a-154">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dec3a-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="dec3a-155">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="dec3a-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="dec3a-156">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="dec3a-156">Related topics</span></span>

[<span data-ttu-id="dec3a-157">Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="dec3a-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

