---
title: Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019043"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="ebb11-103">Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ebb11-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="ebb11-104">Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions ainsi que les numéros de téléphone utilisable par les appelants à appeler dans une réunion.</span><span class="sxs-lookup"><span data-stu-id="ebb11-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="ebb11-105">Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion vous demande de l’appelant d’entrer cet ID de conférence afin qu’ils peuvent participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="ebb11-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ebb11-106">Si votre fournisseur de conférence est Microsoft, ID de conférence des utilisateurs est définis sur dynamique uniquement par défaut.</span><span class="sxs-lookup"><span data-stu-id="ebb11-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="ebb11-107">Malheureusement, il n’existe aucune possibilité de modifier celui-ci statique, comme cela est désormais non prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ebb11-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="ebb11-108">ID de conférence est uniquement automatiquement définie pour les utilisateurs Microsoft Teams activés pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="ebb11-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="ebb11-109">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="ebb11-109">Resetting the conference ID for a user</span></span>

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="ebb11-111">À l’aide de Skype les équipes Microsoft Business centre d’administration</span><span class="sxs-lookup"><span data-stu-id="ebb11-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="ebb11-112">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ebb11-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ebb11-113">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ebb11-113">Click **Edit**.</span></span>

3. <span data-ttu-id="ebb11-114">Sous **Conférence Audio** , cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="ebb11-114">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="ebb11-115">Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="ebb11-115">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="ebb11-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="ebb11-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="ebb11-117">Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="ebb11-117">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="ebb11-118">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebb11-118">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="ebb11-119">Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebb11-119">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="ebb11-120">Le courrier électronique contient le nouvel ID de conférence, ou les numéros de téléphone par défaut et des instructions pour mettre à jour des réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="ebb11-120">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="ebb11-121">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ebb11-121">What else should I know?</span></span>

- <span data-ttu-id="ebb11-122">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence dans le message électronique** de l’utilisateur dans la section de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="ebb11-122">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="ebb11-123">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="ebb11-123">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="ebb11-124">Contient un ID de conférence 7 chiffres, et vous ne pouvez pas modifier sa longueur.</span><span class="sxs-lookup"><span data-stu-id="ebb11-124">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="ebb11-125">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="ebb11-125">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="ebb11-126">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="ebb11-126">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="ebb11-127">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="ebb11-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ebb11-128">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="ebb11-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ebb11-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebb11-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ebb11-132">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebb11-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ebb11-133">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebb11-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ebb11-134">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ebb11-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ebb11-135">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ebb11-135">Related topics</span></span>

[<span data-ttu-id="ebb11-136">Réinitialiser le code confidentiel de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="ebb11-136">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
