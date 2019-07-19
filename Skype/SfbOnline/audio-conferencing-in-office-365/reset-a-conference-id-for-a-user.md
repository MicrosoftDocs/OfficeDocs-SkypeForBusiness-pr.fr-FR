---
title: Réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Découvrez les étapes de réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online et obtenez des liens vers des outils de mise à jour et de migration de réunions. '
ms.openlocfilehash: 0e214444b80f6562c733526acbb6f87c66e46922
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792104"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="64ba7-103">Réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="64ba7-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="64ba7-104">Pour plus d’informations sur la réinitialisation de l’ID de conférence dans Microsoft Teams, voir [Réinitialiser un ID de conférence pour un utilisateur dans Microsoft teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="64ba7-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="64ba7-105">Un ID de conférence dynamique est inclus en bas de l’invitation à la réunion, ainsi que les numéros de téléphone à composer qui peuvent être utilisés par les appelants pour appeler une réunion.</span><span class="sxs-lookup"><span data-stu-id="64ba7-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="64ba7-106">Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion demande à l’appelant d’entrer cet ID de conférence pour pouvoir participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="64ba7-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64ba7-107">S’il s’agit de votre fournisseur de services de conférence Microsoft, les ID de conférence de vos utilisateurs sont définis sur dynamique uniquement.</span><span class="sxs-lookup"><span data-stu-id="64ba7-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="64ba7-108">Cette opération ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="64ba7-108">This cannot be changed.</span></span> <span data-ttu-id="64ba7-109">Les ID de conférence sont automatiquement définis uniquement pour les utilisateurs Skype entreprise activés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="64ba7-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="64ba7-110">Réinitialisation de l’ID de conférence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="64ba7-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="64ba7-111">Dans le **Centre d’administration Skype entreprise**, cliquez sur**utilisateurs**de l' **audioconférence** > , sélectionnez un utilisateur, puis, dans le volet action, sous **ID de conférence** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="64ba7-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="64ba7-112">Dans la fenêtre de réinitialisation de l' **ID de conférence?** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="64ba7-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="64ba7-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="64ba7-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="64ba7-114">Par défaut, les courriers électroniques sont envoyés aux utilisateurs, mais ils peuvent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="64ba7-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="64ba7-p104">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="64ba7-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="64ba7-118">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="64ba7-118">What else should I know?</span></span>

- <span data-ttu-id="64ba7-119">Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations sur la Conférence par courrier électronique** pour l’utilisateur dans le volet action.</span><span class="sxs-lookup"><span data-stu-id="64ba7-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="64ba7-120">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="64ba7-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="64ba7-121">Un ID de conférence contient sept chiffres, et vous ne pouvez pas modifier sa longueur dans le centre d’administration Skype entreprise ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64ba7-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="64ba7-122">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="64ba7-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="64ba7-123">L’ID de conférence d’un utilisateur pour les conférences audio peut être affiché en bas du volet action sous **audioconférence** lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="64ba7-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="64ba7-124">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="64ba7-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="64ba7-125">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="64ba7-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="64ba7-126">Les utilisateurs peuvent utiliser l’outil de réunion Skype entreprise pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="64ba7-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="64ba7-127">Pour découvrir comment télécharger, installer et exécuter l’outil de mise à jour de réunion Skype entreprise, reportez-vous aux ressources suivantes:</span><span class="sxs-lookup"><span data-stu-id="64ba7-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="64ba7-128">Skype Entreprise (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="64ba7-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="64ba7-129">Outil de migration de réunions Skype Entreprise Online (64 bits)</span><span class="sxs-lookup"><span data-stu-id="64ba7-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="64ba7-130">Outil de migration de réunions Skype Entreprise Online (32 bits)</span><span class="sxs-lookup"><span data-stu-id="64ba7-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="64ba7-131">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="64ba7-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="64ba7-p107">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="64ba7-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="64ba7-135">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="64ba7-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="64ba7-136">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="64ba7-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="64ba7-137">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="64ba7-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="64ba7-138">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="64ba7-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="64ba7-139">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ba7-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="64ba7-140">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="64ba7-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="64ba7-141">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="64ba7-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="64ba7-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64ba7-142">Related topics</span></span>

[<span data-ttu-id="64ba7-143">Réinitialiser le code confidentiel d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="64ba7-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
