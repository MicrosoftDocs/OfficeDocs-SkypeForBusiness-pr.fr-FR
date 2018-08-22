---
title: Afficher, modifier et réinitialiser un ID de conférence affecté à un utilisateur de Skype pour Business Online
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
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur de Skype pour Business en ligne et les paramètres d’ID de conférence doivent être. '
ms.openlocfilehash: 19a5af7a3a9a06e99556eda09f00566843551a34
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490634"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="8ee41-103">Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="8ee41-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="8ee41-104">Pour plus d’informations sur la conférence utilisateur ID dans Microsoft Teams, voir [Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8ee41-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="8ee41-105">Un ID de conférence est automatiquement attribué à un Skype pour utilisateur professionnel lorsqu’ils sont configurés pour les services d’audioconférence dans Office 365 et utilisent Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="8ee41-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="8ee41-106">L’ID de conférence affecté est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée.</span><span class="sxs-lookup"><span data-stu-id="8ee41-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="8ee41-107">Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="8ee41-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="8ee41-108">Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou lorsque les utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8ee41-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="8ee41-109">Vous pouvez utiliser **Skype entreprise centre d’administration** et de Windows PowerShell pour afficher, modifier et de réinitialiser leur ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="8ee41-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="8ee41-110">Un e-mail sera envoyé à l’utilisateur dont l’ID de conférence et les numéros de téléphone de conférence audio par défaut, ou si vous réinitialisez l’ID de conférence une autre adresse e-mail est envoyée qui inclut l’ID de conférence, mais pas d’un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="8ee41-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="8ee41-111">Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="8ee41-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="8ee41-112">Afficher et réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8ee41-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="8ee41-113">Pour afficher l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8ee41-113">To view the conference ID</span></span>

<span data-ttu-id="8ee41-114">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="8ee41-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="8ee41-115">Vous pouvez afficher leur ID de conférence et l’envoyer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8ee41-115">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="8ee41-116">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="8ee41-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8ee41-117">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8ee41-118">Dans la **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, sélectionnez l’utilisateur qui doit être ID de la conférence.</span><span class="sxs-lookup"><span data-stu-id="8ee41-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="8ee41-119">Dans la page Action, examinez les **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-119">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8ee41-120">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par courrier électronique** une fois que vous sélectionnez l’utilisateur dans la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="8ee41-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="8ee41-121">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="8ee41-122">Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8ee41-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="8ee41-123">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="8ee41-123">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="8ee41-124">Pour réinitialiser l’ID de conférence</span><span class="sxs-lookup"><span data-stu-id="8ee41-124">To reset the conference ID</span></span>

<span data-ttu-id="8ee41-125">Vous pouvez réinitialiser un ID de conférence pour un utilisateur si, par exemple, ils oublieraient.</span><span class="sxs-lookup"><span data-stu-id="8ee41-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>
 
<span data-ttu-id="8ee41-126">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="8ee41-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="8ee41-127">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="8ee41-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8ee41-128">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8ee41-129">Dans la **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="8ee41-130">Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="8ee41-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="8ee41-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
<span data-ttu-id="8ee41-132">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="8ee41-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="8ee41-133">Vous pouvez réinitialiser l’ID de conférence pour un utilisateur à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ee41-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="8ee41-134">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="8ee41-134">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="8ee41-135">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8ee41-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="8ee41-136">Une fois un nouvel ID de conférence est créé ou une est réinitialisée, l’ancien ID de conférence ne peut être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="8ee41-136">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="8ee41-137">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="8ee41-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="8ee41-138">Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="8ee41-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="8ee41-139">Pour savoir comment télécharger, installer et exécuter l’outil, voir : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="8ee41-139">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="8ee41-140">Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="8ee41-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="8ee41-141">L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="8ee41-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="8ee41-142">Vous ne pouvez pas utiliser des caractères alphabétiques ou spéciaux conférence ID ; Seuls les nombres peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="8ee41-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="8ee41-143">L’ID de conférence pour tous vos utilisateurs de conférence audio sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="8ee41-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8ee41-144">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="8ee41-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8ee41-p109">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="8ee41-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8ee41-148">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8ee41-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="8ee41-149">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ee41-149">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="8ee41-p110">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ee41-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8ee41-152">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ee41-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8ee41-153">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8ee41-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8ee41-154">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8ee41-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8ee41-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8ee41-155">Related topics</span></span>

[<span data-ttu-id="8ee41-156">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="8ee41-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

