---
title: Définir la longueur du code confidentiel pour les réunions de conférence Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 16b6a34e5de790964f5472cb2ef598eebf4f838f
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703817"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a><span data-ttu-id="2ad04-103">Définir la longueur du code confidentiel pour les réunions de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="2ad04-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="2ad04-104">Lorsque vous configurez des services d’audioconférence pour Skype pour Microsoft Teams ou de l’entreprise, vous obtiendrez un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="2ad04-104">When you are setting up audio conferencing for Skype for Business or Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="2ad04-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="2ad04-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="2ad04-106">Le numéro de téléphone que vous avez sera inclus dans les invitations de réunion Skype pour les applications métiers et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ad04-106">The phone number you set will be included on the meeting invites for Skype for Business and Microsoft Teams apps.</span></span>
  
<span data-ttu-id="2ad04-107">Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="2ad04-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="2ad04-108">Il répond à l’appelant à invites vocales à partir d’un standard automatique, puis, en fonction de vos paramètres, peut lire des notifications et poser aux appelants à enregistrer leur nom.</span><span class="sxs-lookup"><span data-stu-id="2ad04-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="2ad04-109">**Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et la réunion expérience de participation aux et définir la longueur des codes confidentiels qui sont utilisés par les organisateurs de réunion.</span><span class="sxs-lookup"><span data-stu-id="2ad04-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="2ad04-110">Organisateurs de réunion utilisent broches pour démarrer les réunions si elles ne peuvent pas participer à la réunion à l’aide de la Skype pour l’application Microsoft Teams ou de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2ad04-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business or Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="2ad04-111">Définir la longueur du code confidentiel</span><span class="sxs-lookup"><span data-stu-id="2ad04-111">Setting the PIN length</span></span>

<span data-ttu-id="2ad04-112">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="2ad04-112">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="2ad04-113">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="2ad04-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2ad04-114">En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="2ad04-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="2ad04-115">Dans le volet **paramètres du pont** , sous **longueur du code confidentiel**, sélectionnez le nombre de chiffres que vous voulez pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="2ad04-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="2ad04-116">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="2ad04-116">Click **Apply**.</span></span>

<span data-ttu-id="2ad04-117">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="2ad04-117">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2ad04-118">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="2ad04-118">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="2ad04-119">Sous **sécurité** > **longueur du code confidentiel**, sélectionnez le nombre de chiffres pour le code confidentiel, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2ad04-119">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ad04-p103">Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="2ad04-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="2ad04-124">Vous souhaitez en savoir plus sur les paramètres de code confidentiel ?</span><span class="sxs-lookup"><span data-stu-id="2ad04-124">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="2ad04-125">Codes confidentiels peuvent être de 4 à 12 chiffres ; la valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="2ad04-125">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="2ad04-126">Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="2ad04-126">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="2ad04-127">Les lettres et les caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="2ad04-127">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="2ad04-128">Un code confidentiel est uniquement requis pour l’organisateur lorsqu’une Skype pour utilisateur Teams Microsoft ou de l’entreprise n’a pas déjà démarré la réunion.</span><span class="sxs-lookup"><span data-stu-id="2ad04-128">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="2ad04-129">Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="2ad04-129">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="2ad04-p106">Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique.</span><span class="sxs-lookup"><span data-stu-id="2ad04-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2ad04-132">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="2ad04-132">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2ad04-133">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="2ad04-133">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="2ad04-134">Pour définir le nombre de chiffres du code confidentiel sur 8 :  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="2ad04-134">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="2ad04-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ad04-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="2ad04-138">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ad04-138">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="2ad04-139">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="2ad04-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2ad04-140">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="2ad04-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="2ad04-141">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ad04-141">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="2ad04-142">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2ad04-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2ad04-143">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2ad04-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="2ad04-144">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2ad04-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2ad04-145">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2ad04-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="2ad04-p109">[Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="2ad04-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ad04-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ad04-148">See also</span></span>

[<span data-ttu-id="2ad04-149">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="2ad04-149">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
