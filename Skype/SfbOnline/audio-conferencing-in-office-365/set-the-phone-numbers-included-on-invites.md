---
title: Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: c6a8c9c3b3d21a64ad54d84ed8bfab22044f9cf5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680371"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="f6684-103">Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f6684-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f6684-104">Pour plus d’informations sur comment faire des conférences avec des numéros de téléphone inclus sur invite dans Microsoft Teams, voir [Définir les numéros de téléphone inclus sur invite dans les Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f6684-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="f6684-p101">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span><span class="sxs-lookup"><span data-stu-id="f6684-p101">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6684-p102">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span><span class="sxs-lookup"><span data-stu-id="f6684-p102">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="f6684-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span><span class="sxs-lookup"><span data-stu-id="f6684-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6684-112">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="f6684-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="f6684-113">Définir le numéro de téléphone par défaut pour un organisateur de réunion</span><span class="sxs-lookup"><span data-stu-id="f6684-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="f6684-114">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="f6684-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f6684-115">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f6684-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f6684-116">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f6684-116">Choose **Users**.</span></span>
    
    ![Indique les utilisateurs au niveau du centre d’administration Skype Entreprise](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="f6684-118">Sélectionnez les utilisateurs que vous souhaitez modifier :</span><span class="sxs-lookup"><span data-stu-id="f6684-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="f6684-119">Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6684-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="f6684-120">Pour sélectionner tous les utilisateurs sur la page, cochez la case à côté de **Afficher le nom** en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="f6684-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="f6684-121">Pour sélectionner plusieurs utilisateurs, cochez la case en regard de chaque nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6684-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="f6684-122">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f6684-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="f6684-124">Choisissez **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="f6684-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="f6684-p104">On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.</span><span class="sxs-lookup"><span data-stu-id="f6684-p104">On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="f6684-127">**Microsoft est le fournisseur**: utilisez les listes de **numéro de téléphone payant par défaut** et de **numéro d’appel gratuit par défaut** pour sélectionner les numéros par défaut pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6684-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f6684-p105">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="f6684-p105">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="f6684-130">**Le fournisseur est un tiers** : utiliser les champs de **Numéro de téléphone payant** et de**Numéro d’appel gratuit** pour indiquer les numéros pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6684-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="f6684-131">Réinitialiser les numéros de téléphone des services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="f6684-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="f6684-132">Dans le **Centre d’administration de Skype entreprise**, sélectionnez **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="f6684-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="f6684-133">En haut de la page, choisissez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f6684-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="f6684-134">Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis dans le volet Actions, cliquez sur **Effacer**.</span><span class="sxs-lookup"><span data-stu-id="f6684-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="f6684-p106">By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="f6684-p106">By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6684-137">Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions Skype Entreprise périodiques et futures doivent être mises à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="f6684-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f6684-138">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="f6684-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f6684-139">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="f6684-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="f6684-140">Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f6684-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="f6684-141">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f6684-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="f6684-142">Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="f6684-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6684-143">Pour rechercher le BridgeID, utilisez l’applet **de passe Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="f6684-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="f6684-144">Pour définir le numéro gratuit par défaut pour tous les utilisateurs ne disposant pas de l’une de + 18005551234, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f6684-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="f6684-145">Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui disposent de + 18005551234 comme numéro gratuit par défaut de + 18005551239, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f6684-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="f6684-146">Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 18005551234, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f6684-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="f6684-147">Vous voulez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="f6684-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="f6684-p107">Windows PowerShell permet de gérer les utilisateurs et ce qu’ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="f6684-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f6684-151">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f6684-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f6684-152">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6684-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f6684-p108">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez les avantages suivants dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6684-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f6684-155">Meilleures méthodes de gestion d’Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6684-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f6684-156">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f6684-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f6684-157">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f6684-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f6684-158">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f6684-158">Related topics</span></span>

[<span data-ttu-id="f6684-159">Tester ou acheter l’audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="f6684-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
