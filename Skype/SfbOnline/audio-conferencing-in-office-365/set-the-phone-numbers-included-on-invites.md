---
title: Définir le téléphone numéros inclus sur invite dans Skype pour Business en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 7aa426a1ede348e29230b177ecf790d9d32d7fbd
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490474"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="d63e5-103">Définir le téléphone numéros inclus sur invite dans Skype pour Business en ligne</span><span class="sxs-lookup"><span data-stu-id="d63e5-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="d63e5-104">Pour plus d’informations sur la réunion inviter les numéros de téléphone dans Microsoft Teams, voir [définir le téléphone numéros inclus sur invite dans les équipes Microsoft](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="d63e5-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="d63e5-105">Services d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer Skype pour les réunions d’entreprise, puis autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="d63e5-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="d63e5-106">Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio Microsoft ou un pont de conférence audio tiers qui est hébergé par un fournisseur de services d’audioconférence approuvé (ACP).</span><span class="sxs-lookup"><span data-stu-id="d63e5-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d63e5-107">Il n'existe pas de ressource qui rassemble tous les numéros de connexion pour l'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d63e5-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="d63e5-108">Si vous souhaitez pour voir s’il existe des numéros de téléphone entrant dans votre région ou le pays/région, utilisez le **Skype pour le centre d’administration de Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter** puis **nouveaux numéros de Service **.</span><span class="sxs-lookup"><span data-stu-id="d63e5-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="d63e5-109">Utilisez les listes de **Pays/région**, département/région **** et **Ville** pour filtrer votre recherche. > en outre, si vous recherchez des – numéros d’appel gratuit, sélectionnez **numéro gratuit** à partir de **Dép./région** liste.</span><span class="sxs-lookup"><span data-stu-id="d63e5-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="d63e5-110">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d63e5-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="d63e5-111">Tous les peuvent servir à participer à des réunions créé un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être incluses dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="d63e5-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d63e5-112">Il peut y avoir un maximum d’un numéro et un numéro de téléphone gratuit sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à la réunion qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="d63e5-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="d63e5-113">Définir le numéro de téléphone par défaut pour un organisateur de réunion</span><span class="sxs-lookup"><span data-stu-id="d63e5-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="d63e5-114">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="d63e5-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d63e5-115">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d63e5-116">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-116">Choose **Users**.</span></span>
    
    ![Indique de sélectionner des utilisateurs dans le Skype entreprise centre d’administration](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="d63e5-118">Choisir les utilisateurs à modifier :</span><span class="sxs-lookup"><span data-stu-id="d63e5-118">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="d63e5-119">Pour sélectionner un seul utilisateur, sélectionnez le nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-119">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="d63e5-120">Pour sélectionner tous les utilisateurs sur la page, activez la case à côté du **nom d’affichage** en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="d63e5-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="d63e5-121">Pour sélectionner plusieurs utilisateurs, activez la case en regard de chaque nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="d63e5-122">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="d63e5-124">Choisissez **l’audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="d63e5-125">Dans la page **Propriétés** , dans la liste **nom du fournisseur** , sélectionnez le fournisseur pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="d63e5-126">Selon le fournisseur, complétez les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="d63e5-126">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="d63e5-127">**Microsoft est le fournisseur**: utiliser le **numéro de téléphone payant par défaut** et **numéro d’appel gratuit par défaut** des listes pour sélectionner les numéros par défaut pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d63e5-128">Au moins un numéro d’appel gratuit doit être affecté à votre pont de conférence avant qu’il peut être définie en tant que le numéro d’appel gratuit par défaut d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="d63e5-129">Pour obtenir un numéro gratuit, voir les [numéros de téléphone de service de mise en route pour Skype pour les entreprises](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="d63e5-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="d63e5-130">**Un tiers est le fournisseur**: les champs de **numéro de téléphone payant** et **gratuit nombre** permet d’entrer les numéros de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="d63e5-131">Réinitialiser les numéros de téléphone des services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="d63e5-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="d63e5-132">Dans la **Skype entreprise centre d’administration**, choisissez **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="d63e5-133">En haut de la page, choisissez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="d63e5-134">Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis dans le volet Actions, cliquez sur **Effacer**.</span><span class="sxs-lookup"><span data-stu-id="d63e5-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="d63e5-135">Par défaut, lorsque vous modifiez les paramètres de conférence d’un utilisateur, un message électronique est envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d63e5-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="d63e5-136">Pour modifier ce paramètre, voir [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="d63e5-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d63e5-137">Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodique et futur Skype pour les réunions d’entreprise doit être mis à jour et envoyée aux participants.</span><span class="sxs-lookup"><span data-stu-id="d63e5-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d63e5-138">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="d63e5-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d63e5-139">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="d63e5-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="d63e5-140">Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d63e5-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="d63e5-141">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d63e5-141">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="d63e5-142">Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="d63e5-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d63e5-143">Pour rechercher la BridgeID, utilisez l’applet de commande **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="d63e5-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="d63e5-144">Pour définir le numéro d’appel gratuit par défaut pour tous les utilisateurs sans un et +18005551234, exécutez :</span><span class="sxs-lookup"><span data-stu-id="d63e5-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="d63e5-145">Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui ont leur numéro gratuit par défaut à +18005551239 +18005551234, exécutez :</span><span class="sxs-lookup"><span data-stu-id="d63e5-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="d63e5-146">Pour définir le numéro gratuit par défaut de tous les utilisateurs situés à +18005551234 qu’aux États-Unis, exécutez :</span><span class="sxs-lookup"><span data-stu-id="d63e5-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="d63e5-147">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="d63e5-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="d63e5-p107">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="d63e5-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d63e5-151">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d63e5-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="d63e5-152">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d63e5-152">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="d63e5-p108">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d63e5-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d63e5-155">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d63e5-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d63e5-156">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d63e5-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d63e5-157">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d63e5-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d63e5-158">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d63e5-158">Related topics</span></span>

[<span data-ttu-id="d63e5-159">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="d63e5-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
