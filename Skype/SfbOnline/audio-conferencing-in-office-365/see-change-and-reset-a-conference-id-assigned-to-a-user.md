---
title: Affichage, modification et réinitialisation d’un ID de conférence affecté à un utilisateur dans Skype entreprise Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur dans Skype entreprise Online et quels sont les paramètres d’ID de conférence. '
ms.openlocfilehash: 65a27315898ec0673d68842e7d5249cbad2d7298
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793003"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="42d7a-103">Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="42d7a-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="42d7a-104">Pour plus d’informations sur les ID de conférence des utilisateurs dans Microsoft Teams, voir [afficher et réinitialiser un ID de conférence affecté à un utilisateur dans Microsoft teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="42d7a-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="42d7a-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="42d7a-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="42d7a-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="42d7a-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="42d7a-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="42d7a-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="42d7a-112">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="42d7a-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="42d7a-113">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="42d7a-113">To view the conference ID</span></span>

<span data-ttu-id="42d7a-114">![Icône illustrant le logo](../images/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="42d7a-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="42d7a-115">Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="42d7a-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="42d7a-116">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="42d7a-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="42d7a-117">Accédez au centre d’administration > **Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="42d7a-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="42d7a-118">Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="42d7a-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="42d7a-119">Dans la page Action, affichez la section **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="42d7a-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="42d7a-120">Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur envoyer les informations sur la **Conférence par courrier électronique** après avoir sélectionné l’utilisateur dans la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="42d7a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="42d7a-121">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="42d7a-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="42d7a-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="42d7a-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="42d7a-124">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="42d7a-124">To reset the conference ID</span></span>

<span data-ttu-id="42d7a-125">Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.</span><span class="sxs-lookup"><span data-stu-id="42d7a-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="42d7a-126">![Icône illustrant le logo](../images/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="42d7a-126">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="42d7a-127">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="42d7a-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="42d7a-128">Accédez au centre d’administration > **Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="42d7a-128">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="42d7a-129">Dans les\*\*\*\* > **utilisateurs**du>  **Centre d’administration de Skype entreprise**, dans le volet action, sous **ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="42d7a-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="42d7a-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="42d7a-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="42d7a-132">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="42d7a-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="42d7a-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="42d7a-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="42d7a-135">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="42d7a-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="42d7a-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="42d7a-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="42d7a-140">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="42d7a-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="42d7a-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="42d7a-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="42d7a-143">L’ID de conférence de tous les utilisateurs de l’audioconférence sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="42d7a-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="42d7a-144">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="42d7a-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="42d7a-p109">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="42d7a-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="42d7a-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="42d7a-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="42d7a-149">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="42d7a-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="42d7a-150">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="42d7a-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="42d7a-151">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="42d7a-151">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="42d7a-152">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42d7a-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="42d7a-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="42d7a-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="42d7a-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="42d7a-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="42d7a-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42d7a-155">Related topics</span></span>

[<span data-ttu-id="42d7a-156">Tester ou acheter l’audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="42d7a-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

