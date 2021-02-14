---
title: Réinitialiser l’ID de conférence d’un utilisateur dans Skype Entreprise Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur dans Skype Entreprise Online et obtenez des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164703"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="b2a95-103">Réinitialiser l’ID de conférence d’un utilisateur dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2a95-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="b2a95-104">Pour plus d’informations sur la réinitialisation de l’ID de conférence dans Microsoft Teams, voir Réinitialiser l’ID de conférence [d’un utilisateur dans Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="b2a95-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="b2a95-105">Un ID de conférence dynamique est inclus au bas des invitations aux réunions, ainsi que les numéros de téléphone à composer qui peuvent être utilisés par les appelants pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="b2a95-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="b2a95-106">Lorsque l’utilisateur compose le numéro de téléphone, le attendant automatique de la réunion demande à l’appelant d’entrer cet ID de conférence afin qu’il puisse participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b2a95-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a95-107">Si votre fournisseur de conférence est Microsoft, l’ID de conférence de vos utilisateurs est définie sur Dynamique uniquement.</span><span class="sxs-lookup"><span data-stu-id="b2a95-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="b2a95-108">Cette situation ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="b2a95-108">This cannot be changed.</span></span> <span data-ttu-id="b2a95-109">Les ID de conférence sont automatiquement définies pour les utilisateurs Skype Entreprise activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b2a95-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="b2a95-110">Réinitialisation de l’ID de conférence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b2a95-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="b2a95-111">Dans le **Centre d’administration Skype** Entreprise, cliquez sur Utilisateurs de l’audioconférence, sélectionnez un utilisateur, puis dans le volet Action sous   >   **ID** de conférence, cliquez sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="b2a95-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="b2a95-112">Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.**</span><span class="sxs-lookup"><span data-stu-id="b2a95-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="b2a95-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="b2a95-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="b2a95-114">Par défaut, les courriers électroniques sont envoyés aux utilisateurs, mais cette option peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="b2a95-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2a95-115">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2a95-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="b2a95-116">Ce courrier électronique sera envoyé à son adresse de messagerie principale, dans de nombreux cas, à sa boîte aux lettres Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="b2a95-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="b2a95-117">Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="b2a95-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="b2a95-118">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b2a95-118">What else should I know?</span></span>

- <span data-ttu-id="b2a95-119">Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique  qui inclut l’ID de conférence et les numéros de téléphone à composer en cliquant sur Envoyer les informations sur la conférence par courrier électronique à l’utilisateur dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="b2a95-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="b2a95-120">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="b2a95-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="b2a95-121">Un ID de conférence contient sept chiffres, et vous ne pouvez pas modifier sa longueur dans le Centre d’administration Skype Entreprise ou à l’aide Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2a95-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="b2a95-122">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="b2a95-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="b2a95-123">L’ID de conférence d’un utilisateur pour l’audioconférence est  consultable au bas du volet Action sous Audioconférence lorsque vous sélectionnez l’utilisateur dans la **page** Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b2a95-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="b2a95-124">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="b2a95-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b2a95-125">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="b2a95-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="b2a95-126">Les utilisateurs peuvent utiliser l’outil de réunion Skype Entreprise pour mettre à jour leurs réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="b2a95-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="b2a95-127">Pour savoir comment télécharger, installer et exécuter l’outil de mise à jour des réunions Skype Entreprise, consultez :</span><span class="sxs-lookup"><span data-stu-id="b2a95-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="b2a95-128">Skype Entreprise (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="b2a95-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="b2a95-129">Outil de migration de réunions Skype Entreprise Online (64 bits)</span><span class="sxs-lookup"><span data-stu-id="b2a95-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="b2a95-130">Outil de migration de réunions Skype Entreprise Online (32 bits)</span><span class="sxs-lookup"><span data-stu-id="b2a95-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b2a95-131">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="b2a95-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b2a95-132">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire.</span><span class="sxs-lookup"><span data-stu-id="b2a95-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b2a95-133">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="b2a95-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b2a95-134">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="b2a95-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b2a95-135">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2a95-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b2a95-136">Pourquoi utiliser Microsoft 365 ou PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="b2a95-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- <span data-ttu-id="b2a95-137">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="b2a95-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b2a95-138">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2a95-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b2a95-139">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2a95-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b2a95-140">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2a95-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b2a95-141">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2a95-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b2a95-142">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b2a95-142">Related topics</span></span>

[<span data-ttu-id="b2a95-143">Réinitialiser le code confidentiel d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="b2a95-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
