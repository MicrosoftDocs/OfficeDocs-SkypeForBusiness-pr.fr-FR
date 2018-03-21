---
title: "Réinitialiser l'ID de conférence d'un utilisateur"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2a5ab1adf9335b2bc5c219975aff11c9e54292fa
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="7f1f7-103">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7f1f7-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="7f1f7-104">Lorsque votre organisation n’a pas été activé pour ID de conférence dynamique, un ID de conférence statique est automatiquement créé lorsqu’une Skype pour l’utilisateur professionnel ou Microsoft Teams est activé pour la conférence Audio à l’aide de Microsoft comme fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="7f1f7-105">Cet ID de conférence est inclus au bas des invitations à ainsi que les numéros de téléphone qui peuvent être utilisés par les appelants pour appeler à une réunion.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="7f1f7-106">Lorsque l’utilisateur compose le numéro de téléphone, la surveillance automatique pour la réunion demandera à l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f1f7-107">Si votre fournisseur de conférence est Microsoft, ID de conférence de vos utilisateurs sont définis uniquement dynamique par défaut.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="7f1f7-108">Malheureusement, vous ne pourrez pas le modifier dans le Skype pour Business Admin Center ou à l’aide de Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="7f1f7-109">Vous devrez contacter le support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="7f1f7-110">ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="7f1f7-111">Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="7f1f7-112">Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [Cliquez ici](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="7f1f7-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="7f1f7-113">ID de conférence sont définies uniquement automatiquement uniquement pour Skype pour les utilisateurs professionnels et Microsoft Teams activé pour les conférences Audio à l’aide de Microsoft comme leur fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="7f1f7-114">Si vous devez réinitialiser un ID de conférence pour un utilisateur qui utilise un fournisseur de conférence audio de tiers (ACP), vous devrez saisir un ID de la conférence sur la page de propriétés pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="7f1f7-115">Réinitialisation de l’ID de conférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7f1f7-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="7f1f7-116">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7f1f7-117">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7f1f7-118">Dans le **Skype pour Business admin center**, cliquez sur **les conférences Audio** > **les utilisateurs**, sélectionnez un utilisateur, puis cliquez sur **Réinitialiser**dans le volet Actions, sous **ID de conférence** .</span><span class="sxs-lookup"><span data-stu-id="7f1f7-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="7f1f7-119">Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="7f1f7-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="7f1f7-121">Par défaut, les e-mails sont envoyés aux utilisateurs, mais cela peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f1f7-p106">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="7f1f7-125">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7f1f7-125">What else should I know?</span></span>

- <span data-ttu-id="7f1f7-126">Vous pouvez envoyer toutes les informations de la conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence par courrier électronique** de l’utilisateur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="7f1f7-127">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="7f1f7-128">Un ID de conférence contient 7 chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype pour Business admin center ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="7f1f7-129">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="7f1f7-130">L’ID d’un utilisateur pour la conférence audio de conférence sont consultables en bas du volet Office sous **les conférences Audio** lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="7f1f7-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="7f1f7-131">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="7f1f7-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="7f1f7-133">Les utilisateurs peuvent utiliser Skype pour outil de travail réunion mise à jour de leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="7f1f7-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="7f1f7-134">Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, voir :</span><span class="sxs-lookup"><span data-stu-id="7f1f7-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="7f1f7-135">Skype Entreprise (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="7f1f7-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="7f1f7-136">Outil de migration de réunions Skype Entreprise Online (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7f1f7-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="7f1f7-137">Outil de migration de réunions Skype Entreprise Online (32 bits)</span><span class="sxs-lookup"><span data-stu-id="7f1f7-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7f1f7-138">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="7f1f7-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7f1f7-p109">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="7f1f7-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7f1f7-142">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7f1f7-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="7f1f7-143">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f1f7-143">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="7f1f7-p110">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f1f7-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7f1f7-146">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f1f7-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7f1f7-147">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7f1f7-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7f1f7-148">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7f1f7-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7f1f7-149">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7f1f7-149">Related topics</span></span>

[<span data-ttu-id="7f1f7-150">Réinitialiser le code confidentiel d'audioconférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7f1f7-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
