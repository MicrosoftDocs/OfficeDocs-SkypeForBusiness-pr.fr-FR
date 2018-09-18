---
title: Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez la procédure de réinitialisation de l’ID de conférence d’un utilisateur et pour obtenir des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887851"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="7b7f1-103">Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b7f1-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="7b7f1-104">Un ID de conférence dynamique est inclus dans la partie inférieure des invitations aux réunions avec les numéros de téléphone qui peuvent être utilisés par les appelants pour accéder à une réunion.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-104">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="7b7f1-105">Lorsque l'utilisateur compose le numéro de téléphone, le standard automatique de la réunion lui demande de saisir cet ID de conférence pour pouvoir assister à la réunion.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b7f1-106">Si votre fournisseur de service de conférence est Microsoft, les ID de conférence de vos utilisateurs sont définis par défaut sur Dynamique uniquement.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="7b7f1-107">Il n’est malheureusement pas possible de définir des ID statiques, car cette option n’est pas prise en charge actuellement.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="7b7f1-108">Les ID de conférence sont définis automatiquement uniquement pour les utilisateurs de Microsoft Teams activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="7b7f1-109">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="7b7f1-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="7b7f1-110">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-110">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7b7f1-111">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-111">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="7b7f1-112">Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="7b7f1-113">Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="7b7f1-114">Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="7b7f1-115">Des courriers électroniques sont envoyés aux utilisateurs par défaut, mais cette option peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-115">By default, emails are sent to users, but it can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="7b7f1-116">Une fois l'ID de conférence réinitialisé, un courrier électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="7b7f1-117">Ce courrier électronique est envoyé à son adresse électronique principale, généralement sa boîte aux lettres Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="7b7f1-118">Le courrier électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions de mise à jour des réunions existantes.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-118">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="7b7f1-119">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7b7f1-119">What else should I know?</span></span>

- <span data-ttu-id="7b7f1-120">Vous pouvez envoyer toutes les informations sur les conférences à l'utilisateur dans un message électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** pour l’utilisateur dans la section **Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="7b7f1-121">Ce courrier ne contient pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="7b7f1-122">Un ID de conférence contient 7 chiffres, et vous ne pouvez pas modifier sa longueur.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="7b7f1-123">Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID sous **ID de conférence**.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="7b7f1-124">Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="7b7f1-125">Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7b7f1-126">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="7b7f1-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7b7f1-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b7f1-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7b7f1-130">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b7f1-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7b7f1-131">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b7f1-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7b7f1-132">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7b7f1-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7b7f1-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7b7f1-133">Related topics</span></span>

<span data-ttu-id="7b7f1-134">[Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7b7f1-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
