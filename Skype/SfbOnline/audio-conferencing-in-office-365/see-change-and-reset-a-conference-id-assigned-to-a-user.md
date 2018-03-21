---
title: "Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to assign a conference ID to a user in Skype for Business and what the conference ID''s parameters should be. '
ms.openlocfilehash: b542e764d0b8b1587c34e78a54612410cd72a3bd
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="8baa0-103">Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="8baa0-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="8baa0-104">Un ID de conférence est automatiquement affecté à un Skype pour l’utilisateur professionnel ou Teams de Microsoft lorsqu’ils sont configurés pour les conférences Audio dans Office 365 et utilisent Microsoft comme fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="8baa0-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="8baa0-105">L’ID de conférence affecté peut être statique ou dynamique et est envoyé dans l’invitation à une réunion lorsque la réunion est planifiée.</span><span class="sxs-lookup"><span data-stu-id="8baa0-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="8baa0-106">ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser.</span><span class="sxs-lookup"><span data-stu-id="8baa0-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="8baa0-107">Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="8baa0-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="8baa0-108">Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [Cliquez ici](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="8baa0-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="8baa0-109">Bien qu’un ID de conférence statique sera automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous souhaitez la définir pour un certain nombre, ou lorsque vos utilisateurs ne vous souvenez plus ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8baa0-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="8baa0-110">Vous pouvez utiliser le **Skype pour Business admin center** et de Windows PowerShell pour afficher, de modifier et de réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8baa0-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="8baa0-111">Un e-mail sera envoyé à l’utilisateur avec l’ID de conférence et les numéros de téléphone de conférence audio par défaut, ou si vous réinitialisez l’ID de conférence une autre adresse e-mail sera envoyée qui inclut l’ID de conférence, mais pas d’un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="8baa0-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="8baa0-112">Permet d’afficher et de modifier l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8baa0-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="8baa0-113">Permet d’afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8baa0-113">To view the conference ID</span></span>

<span data-ttu-id="8baa0-114">Vous pouvez afficher leur ID de conférence et l’envoyer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8baa0-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="8baa0-115">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="8baa0-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8baa0-116">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="8baa0-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8baa0-117">Dans le **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, sélectionnez l’utilisateur qui a besoin de code de la conférence</span><span class="sxs-lookup"><span data-stu-id="8baa0-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="8baa0-118">Dans la page Action, regardez sous **l’ID de la conférence**.</span><span class="sxs-lookup"><span data-stu-id="8baa0-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8baa0-119">Vous pouvez envoyer toutes les informations de la conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par courrier électronique** une fois que vous sélectionnez l’utilisateur dans la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="8baa0-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="8baa0-120">Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8baa0-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="8baa0-121">Pour ce faire, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="8baa0-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="8baa0-122">Reportez-vous à la section [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) pour en savoir plus sur l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="8baa0-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="8baa0-123">Pour affecter ou modifier l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8baa0-123">To assign or change the conference ID</span></span>

<span data-ttu-id="8baa0-124">Vous pouvez affecter ou modifier un ID de conférence d’un utilisateur si, par exemple, un utilisateur souhaite un ID de conférence qui est facile à mémoriser.</span><span class="sxs-lookup"><span data-stu-id="8baa0-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8baa0-125">Le Skype pour le centre d’administration commerciale ne permet pas de modifier un ID de conférence qui a été créé automatiquement, mais vous pouvez utiliser Windows PowerShell pour les modifier ou changer un ID de conférence que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="8baa0-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="8baa0-126">Pour modifier ou changer l’ID de conférence pour un utilisateur, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="8baa0-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="8baa0-127">Pour définir l'ID de conférence d'un utilisateur, exécutez :</span><span class="sxs-lookup"><span data-stu-id="8baa0-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="8baa0-128">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8baa0-128">To reset the conference ID</span></span>

<span data-ttu-id="8baa0-129">Vous pouvez réinitialiser un ID de conférence d’un utilisateur si, par exemple, si elles l’oublier.</span><span class="sxs-lookup"><span data-stu-id="8baa0-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="8baa0-130">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="8baa0-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8baa0-131">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="8baa0-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8baa0-132">Dans le **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="8baa0-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="8baa0-133">Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8baa0-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="8baa0-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="8baa0-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="8baa0-135">Vous pouvez réinitialiser l’ID de conférence pour un utilisateur à l’aide de la de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8baa0-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="8baa0-136">Pour ce faire, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="8baa0-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="8baa0-137">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8baa0-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="8baa0-138">Après la création d’un nouvel ID de conférence ou une réinitialisation, l’ancien ID de conférence ne peut pas être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="8baa0-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="8baa0-139">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="8baa0-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="8baa0-140">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="8baa0-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="8baa0-141">Pour savoir comment télécharger, installer et exécuter l’outil, reportez-vous à la section : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, l’outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, l’outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="8baa0-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="8baa0-142">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="8baa0-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="8baa0-143">L’ID de conférence doit respecter la longueur en chiffres sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="8baa0-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="8baa0-144">Vous ne pouvez pas utiliser les caractères alphabétiques ou spéciales conférence ID ; Seuls des numéros peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="8baa0-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="8baa0-145">L’ID de conférence pour tous vos utilisateurs de conférence audio sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="8baa0-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="8baa0-146">Si l’utilisateur est déplacé à partir de Microsoft en tant que le fournisseur de conférence audio à un fournisseur de conférence audio de tiers ou le fournisseur de conférence audio est défini sur **Aucun**, l’ID de conférence ne fonctionneront plus.</span><span class="sxs-lookup"><span data-stu-id="8baa0-146">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work.</span></span> <span data-ttu-id="8baa0-147">Reportez-vous à la section [affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md) ou le [déplacement de fournisseur de conférence audio d’un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8baa0-147">See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8baa0-148">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="8baa0-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8baa0-p110">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="8baa0-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8baa0-152">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8baa0-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="8baa0-153">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8baa0-153">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="8baa0-p111">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8baa0-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8baa0-156">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8baa0-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8baa0-157">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8baa0-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8baa0-158">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8baa0-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8baa0-159">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8baa0-159">Related topics</span></span>

[<span data-ttu-id="8baa0-160">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="8baa0-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

