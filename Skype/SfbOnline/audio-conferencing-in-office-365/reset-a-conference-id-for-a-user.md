---
title: Réinitialiser l'ID de conférence d'un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: eb827cff5bdfbc86bf85aab63a8f29165a91f034
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="4669c-103">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4669c-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="4669c-104">Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions ainsi que les numéros de téléphone utilisable par les appelants à appeler dans une réunion.</span><span class="sxs-lookup"><span data-stu-id="4669c-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="4669c-105">Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion vous demande de l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="4669c-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4669c-106">Si votre fournisseur de conférence est Microsoft, ID de conférence des utilisateurs est définis sur dynamique uniquement par défaut.</span><span class="sxs-lookup"><span data-stu-id="4669c-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="4669c-107">Malheureusement, il n’existe aucune possibilité de le modifier dans le Skype pour le centre d’administration Business ou à l’aide de Windows Powershell pour devenir statique, comme cela est désormais non prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4669c-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span>
<span data-ttu-id="4669c-108">ID de conférence est définies uniquement automatiquement uniquement pour Skype pour les utilisateurs professionnels et Microsoft Teams activé pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="4669c-108">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing.</span></span> 
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="4669c-109">Réinitialisation de l’ID de conférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4669c-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="4669c-110">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="4669c-110">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4669c-111">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="4669c-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4669c-112">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4669c-112">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4669c-113">Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Réinitialiser l’id de conférence** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4669c-113">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="4669c-114">Dans la fenêtre **Réinitialiser l’id de conférence** , cliquez sur **Ok**.</span><span class="sxs-lookup"><span data-stu-id="4669c-114">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="4669c-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4669c-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4669c-116">Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="4669c-116">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="4669c-117">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="4669c-117">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="4669c-118">Dans la **Skype entreprise centre d’administration**, cliquez sur **conférence** > **les utilisateurs**, sélectionnez un utilisateur, puis, dans le volet Actions, sous **ID de conférence** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="4669c-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="4669c-119">Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4669c-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="4669c-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4669c-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4669c-121">Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="4669c-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4669c-p105">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="4669c-p105">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="4669c-125">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4669c-125">What else should I know?</span></span>

- <span data-ttu-id="4669c-126">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence par courrier électronique** pour l’utilisateur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="4669c-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="4669c-127">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="4669c-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="4669c-128">Contient un ID de conférence 7 chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype entreprise centre d’administration ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4669c-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="4669c-129">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="4669c-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="4669c-130">Lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** , l’ID de conférence pour un utilisateur pour la conférence audio peut être affiché en bas du volet Actions, sous **l’audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="4669c-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="4669c-131">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="4669c-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4669c-132">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="4669c-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4669c-133">Les utilisateurs peuvent utiliser Skype pour l’outil de réunion Business pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="4669c-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="4669c-134">Pour savoir comment télécharger, installer et exécuter la Skype pour l’outil de mise à jour de réunion Business, voir :</span><span class="sxs-lookup"><span data-stu-id="4669c-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="4669c-135">Skype Entreprise (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="4669c-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="4669c-136">Outil de migration de réunions Skype Entreprise Online (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4669c-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="4669c-137">Outil de migration de réunions Skype Entreprise Online (32 bits)</span><span class="sxs-lookup"><span data-stu-id="4669c-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4669c-138">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="4669c-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4669c-p108">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="4669c-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4669c-142">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4669c-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="4669c-143">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4669c-143">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="4669c-p109">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4669c-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4669c-146">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4669c-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4669c-147">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4669c-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4669c-148">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4669c-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4669c-149">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4669c-149">Related topics</span></span>

[<span data-ttu-id="4669c-150">Réinitialiser le code confidentiel de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="4669c-150">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
