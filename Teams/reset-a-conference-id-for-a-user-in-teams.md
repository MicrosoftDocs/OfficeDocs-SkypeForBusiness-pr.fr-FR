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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662124"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="d391a-103">Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d391a-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="d391a-104">Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions avec les numéros de téléphone qui peuvent être utilisés par les appelants pour accéder à une réunion.</span><span class="sxs-lookup"><span data-stu-id="d391a-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="d391a-105">Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion lui demande de saisir cet ID de conférence pour pouvoir assister à la réunion.</span><span class="sxs-lookup"><span data-stu-id="d391a-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d391a-106">Les ID de conférence sont générés automatiquement, vont de 7-9 chiffres et sont définis lorsque vous activez l’audioconférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d391a-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="d391a-107">**Les ID de conférence statiques ne sont pas pris en charge.**</span><span class="sxs-lookup"><span data-stu-id="d391a-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="d391a-108">Réinitialisation de l’ID de conférence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d391a-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="d391a-109">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="d391a-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d391a-110">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="d391a-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d391a-111">Cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="d391a-111">Click **Edit**.</span></span>

3. <span data-ttu-id="d391a-112">Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="d391a-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="d391a-113">Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="d391a-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="d391a-114">Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d391a-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="d391a-115">Des courriers électroniques sont envoyés aux utilisateurs par défaut, mais cette option peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="d391a-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="d391a-116">Une fois l'ID de conférence réinitialisé, un courrier électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d391a-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="d391a-117">Ce message est envoyé à l’adresse de messagerie principale, dans de nombreux cas, la boîte aux lettres Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d391a-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="d391a-118">Le courrier électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions de mise à jour des réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="d391a-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="d391a-119">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d391a-119">What else should I know?</span></span>

- <span data-ttu-id="d391a-120">Vous pouvez envoyer toutes les informations sur les conférences à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** pour l’utilisateur dans la section **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="d391a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="d391a-121">Ce courrier ne contient pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="d391a-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="d391a-122">Un ID de conférence à 7-9 chiffres est créé par le service Teams.</span><span class="sxs-lookup"><span data-stu-id="d391a-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="d391a-123">Vous ne pouvez pas modifier sa longueur.</span><span class="sxs-lookup"><span data-stu-id="d391a-123">You can't change its length.</span></span>
    
- <span data-ttu-id="d391a-124">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="d391a-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="d391a-125">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="d391a-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d391a-126">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="d391a-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d391a-127">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="d391a-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d391a-128">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="d391a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d391a-129">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="d391a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d391a-130">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="d391a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d391a-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d391a-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d391a-132">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d391a-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d391a-133">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d391a-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d391a-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d391a-134">Related topics</span></span>

[<span data-ttu-id="d391a-135">Réinitialiser le code confidentiel d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="d391a-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
