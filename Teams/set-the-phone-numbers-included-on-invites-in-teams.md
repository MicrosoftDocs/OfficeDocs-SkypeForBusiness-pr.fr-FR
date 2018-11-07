---
title: Définir le téléphone numéros inclus sur invite dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir les étapes pour créer un numéro de téléphone par défaut pour les appelants à participer à une réunion Microsoft Teams. '
ms.openlocfilehash: 20dfd4255cd41e9f5aebf419f77307b30fe40042
ms.sourcegitcommit: 75e0c9e186dc167bad01f5b17ec9de8a682ee007
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2018
ms.locfileid: "26005520"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="0ae26-103">Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ae26-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="0ae26-104">Services d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="0ae26-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="0ae26-105">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ae26-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="0ae26-106">Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="0ae26-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ae26-107">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="0ae26-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="0ae26-108">Invite d’affectation initiale des numéros de téléphone qui sont inclus dans la réunion pour les nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0ae26-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="0ae26-109">Les numéros de téléphone incluses dans la réunion invite d’utilisateurs activés pour la conférence Audio sont définies par le numéro d’appel payant conférence par défaut et les paramètres de l’utilisateur par défaut conférence gratuit numéro.</span><span class="sxs-lookup"><span data-stu-id="0ae26-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="0ae26-110">Chaque paramètre spécifie le numéro payant et le numéro gratuit seront inclus dans l’invitation à la réunion d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="0ae26-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="0ae26-111">Comme mentionné ci-dessus, chaque invitation à la réunion contient un numéro, un seul numéro gratuit facultatif et un lien qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion donnée.</span><span class="sxs-lookup"><span data-stu-id="0ae26-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="0ae26-112">Pour un nouvel utilisateur, les numéros d’appel payant de conférence par défaut sont affectée en fonction du pays est défini dans le profil de l’utilisateur d’Office 365 lorsque l’utilisateur est activé pour le service de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="0ae26-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="0ae26-113">Si le pont de conférence qui correspond à celui de l’utilisateur est un numéro de téléphone payant, ce numéro est automatiquement attribué en tant que le numéro par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ae26-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="0ae26-114">Si vous n’en est pas, le nombre est défini comme le numéro par défaut du pont de conférence sera assignée comme le numéro par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ae26-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="0ae26-115">Une fois que l’utilisateur est activé pour le service de conférence Audio, le numéro payant par défaut et les numéros de téléphone de l’utilisateur peuvent être modifiés par l’administrateur de clients à partir de leurs valeurs initiales à tout moment.</span><span class="sxs-lookup"><span data-stu-id="0ae26-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="0ae26-116">Définir ou modifier le numéro de téléphone de conférence audio par défaut pour un utilisateur ou un organisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="0ae26-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="0ae26-118">À l’aide de Skype les équipes Microsoft Business centre d’administration</span><span class="sxs-lookup"><span data-stu-id="0ae26-118">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="0ae26-119">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="0ae26-119">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Indique de sélectionner des utilisateurs dans le Microsoft Teams et Skype entreprise centre d’administration](media/teamsselectusers.png)

2. <span data-ttu-id="0ae26-121">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0ae26-121">At the top of the page, click **Edit**.</span></span>

    ![Cliquez sur Modifier dans les équipes Microsoft Skype entreprise centre d’administration](media/teamsedituser.png)

3. <span data-ttu-id="0ae26-123">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0ae26-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Cliquez sur Modifier en regard de conférence Audio](media/teamseditaudioconf.png)

4. <span data-ttu-id="0ae26-125">Utilisez les champs de **numéro de téléphone payant** ou **numéro d’appel gratuit** pour entrer les numéros pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ae26-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0ae26-126">Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodiques et futures réunions Teams Microsoft doivent être mis à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="0ae26-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="0ae26-127">Vous souhaitez utiliser Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="0ae26-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="0ae26-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ae26-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0ae26-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ae26-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0ae26-132">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ae26-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0ae26-133">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0ae26-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="0ae26-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0ae26-134">Related topics</span></span>

[<span data-ttu-id="0ae26-135">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="0ae26-135">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
