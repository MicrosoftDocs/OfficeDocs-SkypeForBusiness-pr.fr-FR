---
title: Définir l’invite les inclure sur des numéros de téléphone
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 59ebd95f5b7f7ee546ab272596adf353b2a7adbc
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="fc600-103">Définir l’invite les inclure sur des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="fc600-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="fc600-104">Conférence audio dans Office 365 permet aux utilisateurs de votre organisation de créer Skype pour les réunions d’entreprise et Teams de Microsoft, puis autorisez les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="fc600-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="fc600-105">Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio de Microsoft ou d’un pont de conférence audio de tiers qui est hébergé par un fournisseur agréé de conférence audio (ACP).</span><span class="sxs-lookup"><span data-stu-id="fc600-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc600-106">Il n'existe pas de ressource qui rassemble tous les numéros de connexion pour l'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="fc600-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="fc600-107">Si vous souhaitez pour voir s’il existe les numéros de téléphone disponibles dans votre région ou votre pays/région, utiliser le **Skype pour le centre d’administration Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter** puis **de nouveaux numéros de Service **.</span><span class="sxs-lookup"><span data-stu-id="fc600-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="fc600-108">Utilisez les listes de **Pays/région**, état/région de **** et **Ville** pour filtrer votre recherche. > en outre, si vous recherchez – numéros d’appel gratuit, sélectionnez **numéro gratuit** à partir de l’état/région **** liste.</span><span class="sxs-lookup"><span data-stu-id="fc600-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="fc600-109">Un pont de conférence vous offre un ensemble de numéros de téléphone d’accès à distance pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc600-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="fc600-110">Tous les peuvent servir à assister aux réunions créé un organisateur de réunion, mais vous pouvez sélectionner ceux qui est incluses dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="fc600-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc600-111">Il peut y avoir un maximum d’un numéro et un numéro d’appel gratuit sur l’invitation pour l’organisateur d’une réunion, mais il existe également un lien situé au bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour joindre une réunion.</span><span class="sxs-lookup"><span data-stu-id="fc600-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="fc600-112">Définir le numéro de téléphone par défaut pour l’organisateur d’une réunion</span><span class="sxs-lookup"><span data-stu-id="fc600-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="fc600-113">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="fc600-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="fc600-114">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="fc600-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="fc600-115">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="fc600-115">Choose **Users**.</span></span>
    
    ![Affiche la sélection des utilisateurs dans le Skype pour le centre d’administration de Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="fc600-117">Sélectionnez les utilisateurs que vous souhaitez modifier :</span><span class="sxs-lookup"><span data-stu-id="fc600-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="fc600-118">Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="fc600-119">Pour sélectionner tous les utilisateurs sur la page, sélectionnez la case en regard du **nom d’affichage** en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="fc600-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="fc600-120">Pour sélectionner plusieurs utilisateurs, sélectionnez la case en regard de chaque nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="fc600-121">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fc600-121">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="fc600-123">Choisissez **l’audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="fc600-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="fc600-124">Sur la page de **Propriétés** , dans la liste **nom du fournisseur** , sélectionnez le fournisseur pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-124">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="fc600-125">Selon le fournisseur, complétez les zones suivantes.</span><span class="sxs-lookup"><span data-stu-id="fc600-125">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="fc600-126">**Microsoft est le fournisseur**: utilisez le **numéro d’appel payant par défaut** et le **numéro d’appel gratuit par défaut** répertorie pour sélectionner les numéros par défaut pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc600-127">Au moins un numéro d’appel gratuit doit être affecté à votre pont de conférence avant elle peut être définie comme le numéro d’appel gratuit par défaut d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-127">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="fc600-128">Pour obtenir un numéro d’appel gratuit, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="fc600-128">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="fc600-129">**Une tierce partie est le fournisseur**: les champs **– numéro d’appel** et le **numéro d’appel gratuit** permet d’entrer les numéros de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="fc600-130">Réinitialiser les numéros de téléphone de conférence audio</span><span class="sxs-lookup"><span data-stu-id="fc600-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="fc600-131">Dans le **Skype pour le centre d’administration Business**, choisissez **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="fc600-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="fc600-132">En haut de la page, cliquez sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="fc600-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="fc600-133">Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis, dans le volet Actions, cliquez sur **Effacer**.</span><span class="sxs-lookup"><span data-stu-id="fc600-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="fc600-134">Par défaut, lorsque vous modifiez des paramètres de conférence d’un utilisateur, un e-mail est envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fc600-134">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="fc600-135">Pour modifier ce comportement, voir [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres d’audioconférence](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="fc600-135">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fc600-136">Lorsque vous modifiez des paramètres de conférence audio d’un utilisateur, périodique et futur Skype pour les réunions d’entreprise et Teams de Microsoft doit être mis à jour et envoyée aux participants.</span><span class="sxs-lookup"><span data-stu-id="fc600-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fc600-137">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="fc600-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fc600-138">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="fc600-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="fc600-139">Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fc600-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="fc600-140">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fc600-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="fc600-141">Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="fc600-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc600-142">Pour rechercher la BridgeID, utilisez le **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="fc600-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="fc600-143">Pour définir le numéro d’appel gratuit par défaut pour tous les utilisateurs sans une à +18005551234, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="fc600-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="fc600-144">Pour modifier le numéro d’appel gratuit par défaut de tous les utilisateurs qui ont +18005551234 comme leur numéro d’appel gratuit par défaut à +18005551239, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="fc600-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="fc600-145">Pour définir le numéro gratuit de la valeur par défaut de tous les utilisateurs situés aux Etats-Unis à +18005551234, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="fc600-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="fc600-146">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="fc600-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="fc600-p107">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="fc600-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fc600-150">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fc600-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="fc600-151">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc600-151">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="fc600-p108">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc600-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="fc600-154">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc600-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="fc600-155">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fc600-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fc600-156">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fc600-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="fc600-157">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fc600-157">Related topics</span></span>

[<span data-ttu-id="fc600-158">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="fc600-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
