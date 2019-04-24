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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: f5926d838d61d38eb5b8e9f840cd9d7a4694253f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206585"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="96b87-103">Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96b87-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="96b87-104">Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions avec les numéros de téléphone qui peuvent être utilisés par les appelants pour accéder à une réunion.</span><span class="sxs-lookup"><span data-stu-id="96b87-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="96b87-105">Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion lui demande de saisir cet ID de conférence pour pouvoir assister à la réunion.</span><span class="sxs-lookup"><span data-stu-id="96b87-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96b87-106">Si votre fournisseur de service de conférence est Microsoft, les ID de conférence de vos utilisateurs sont définis par défaut sur Dynamique uniquement.</span><span class="sxs-lookup"><span data-stu-id="96b87-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="96b87-107">Il n’est malheureusement pas possible de définir des ID statiques, car cette option n’est pas prise en charge actuellement.</span><span class="sxs-lookup"><span data-stu-id="96b87-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="96b87-108">Les ID de conférence sont définis automatiquement uniquement pour les utilisateurs de Microsoft Teams activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="96b87-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="96b87-109">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="96b87-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="96b87-110">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="96b87-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="96b87-111">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="96b87-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="96b87-112">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="96b87-112">Click **Edit**.</span></span>

3. <span data-ttu-id="96b87-113">Sous **Conférence Audio** , cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="96b87-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="96b87-114">Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="96b87-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="96b87-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="96b87-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="96b87-116">Par défaut, les messages électroniques sont envoyés aux utilisateurs, mais cela peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="96b87-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="96b87-117">Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="96b87-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="96b87-118">Ce message électronique est envoyé à son adresse électronique principale, généralement la boîte aux lettres Office 365.</span><span class="sxs-lookup"><span data-stu-id="96b87-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="96b87-119">Le courrier électronique contient le nouvel ID de conférence, ou les numéros de téléphone par défaut et des instructions pour mettre à jour des réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="96b87-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="96b87-120">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="96b87-120">What else should I know?</span></span>

- <span data-ttu-id="96b87-121">Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone en cliquant sur **Envoyer les informations de conférence dans le message électronique** de l’utilisateur dans la section de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="96b87-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="96b87-122">Le code confidentiel n'est pas envoyé.</span><span class="sxs-lookup"><span data-stu-id="96b87-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="96b87-123">Contient un ID de conférence 7 chiffres, et vous ne pouvez pas modifier sa longueur.</span><span class="sxs-lookup"><span data-stu-id="96b87-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="96b87-124">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="96b87-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="96b87-125">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="96b87-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="96b87-126">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="96b87-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="96b87-127">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="96b87-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="96b87-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="96b87-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="96b87-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="96b87-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="96b87-132">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b87-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="96b87-133">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="96b87-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="96b87-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="96b87-134">Related topics</span></span>

[<span data-ttu-id="96b87-135">Réinitialiser le code confidentiel d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="96b87-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
