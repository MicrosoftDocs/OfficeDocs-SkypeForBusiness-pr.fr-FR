---
title: Afficher, modifier et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur de Skype Entreprise Online et les paramètres nécessaires des ID de conférence. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252307"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="ec1ad-103">Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ec1ad-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="ec1ad-104">Pour plus d’informations sur les ID de conférence affectés aux utilisateurs dans Microsoft Teams, consulter [Afficher et réinitialiser un ID de conférence affecté à un utilisateur dans Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="ec1ad-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="ec1ad-105">Un ID de conférence est automatiquement attribué à un utilisateur Skype Entreprise lorsque l'utilisateur configure les services d’audioconférence dans Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="ec1ad-106">L’ID de conférence affecté est envoyé dans l’invitation à la réunion lors de sa planification.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="ec1ad-107">Chaque réunion qu'un utilisateur planifie se verra affecter un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="ec1ad-108">Bien qu’un ID de conférence soit automatiquement créé et affecté à un utilisateur, il peut y avoir des cas où un utilisateur ne souhaite pas l'utiliser et où vous voudrez le définir à un certain nombre, ou dans lesquels vos utilisateurs ne pourront pas se souvenir ou auront perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="ec1ad-109">Vous pouvez utiliser le centre d’administration **Skype Entreprise** et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="ec1ad-110">Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="ec1ad-111">Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ec1ad-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="ec1ad-112">Afficher et réinitialiser les ID de conférence</span><span class="sxs-lookup"><span data-stu-id="ec1ad-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="ec1ad-113">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="ec1ad-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="ec1ad-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d'administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="ec1ad-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="ec1ad-115">Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="ec1ad-116">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ec1ad-117">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="ec1ad-118">Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="ec1ad-119">Dans la page Action, affichez la section **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ec1ad-120">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un email comprennant l'ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par email** une fois l’utilisateur sélectionné sur la page **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="ec1ad-121">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ec1ad-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ec1ad-122">Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="ec1ad-123">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ec1ad-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="ec1ad-124">Pour réinitialiser l'ID de conférence</span><span class="sxs-lookup"><span data-stu-id="ec1ad-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="ec1ad-125">Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="ec1ad-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d'administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="ec1ad-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="ec1ad-127">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ec1ad-128">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="ec1ad-129">Dans la page **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="ec1ad-130">Dans la fenêtre **Réinitialiser l’ID de conférence ?**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-130">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="ec1ad-131">Un ID de conférence sera créé automatiquement et un email sera envoyé à l'utilisateur avec le nouvel ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="ec1ad-132">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ec1ad-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ec1ad-133">Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="ec1ad-134">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ec1ad-134">To do this run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="ec1ad-135">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ec1ad-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="ec1ad-136">Une fois qu'un nouvel ID de conférence est créé ou qu'un ID de conférence est réinitialisé, l'ancien ID de conférence ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="ec1ad-137">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="ec1ad-138">Les utilisateurs peuvent utiliser l'Outil de migration de réunions de Skype Entreprise pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="ec1ad-139">Pour savoir comment télécharger, installer et exécuter l'outil, voir : [Outil de migration de réunions de Skype Entreprise et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype Entreprise Online, Outil de migration de réunions (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et [Skype Entreprise Online, Outil de migration de réunions (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="ec1ad-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="ec1ad-140">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="ec1ad-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="ec1ad-141">L'ID de conférence doit respecter le nombre de chiffres défini sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-141">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="ec1ad-142">Les ID de conférence ne doivent comporter que des chiffres, jamais de caractères alphabétiques ou spéciaux.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-142">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>

- <span data-ttu-id="ec1ad-143">L'ID de conférence comporte sept chiffres par défaut pour tous les utilisateurs de l'audioconférence . Il n'est pas possible de modifier le nombre de chiffres.</span><span class="sxs-lookup"><span data-stu-id="ec1ad-143">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ec1ad-144">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="ec1ad-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ec1ad-p109">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="ec1ad-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ec1ad-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ec1ad-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="ec1ad-149">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ec1ad-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="ec1ad-p110">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ec1ad-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="ec1ad-152">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec1ad-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="ec1ad-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ec1ad-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="ec1ad-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ec1ad-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="ec1ad-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ec1ad-155">Related topics</span></span>

[<span data-ttu-id="ec1ad-156">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="ec1ad-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

