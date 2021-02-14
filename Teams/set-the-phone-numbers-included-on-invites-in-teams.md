---
title: Définir les numéros de téléphone inclus dans les invitations
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
- M365-voice
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
description: Suivez ces étapes pour créer un numéro de téléphone par défaut pour que les appelants participent à une réunion Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372183"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="011e5-103">Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="011e5-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="011e5-104">Dans Microsoft 365 et Office 365, l’audioconférence permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams et d’y composer le numéro à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="011e5-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="011e5-105">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="011e5-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="011e5-106">Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="011e5-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="011e5-107">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="011e5-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="011e5-108">Affectation initiale des numéros de téléphone inclus dans les invitations aux réunions pour les nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="011e5-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="011e5-109">Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour l’audioconférence sont définis par le numéro de téléphone gratuit de conférence par défaut et les paramètres d’utilisateur du numéro de téléphone gratuit de conférence par défaut.</span><span class="sxs-lookup"><span data-stu-id="011e5-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="011e5-110">Chaque paramètre spécifie le numéro gratuit et gratuit qui sera inclus dans l’invitation à la réunion d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="011e5-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="011e5-111">Comme indiqué ci-dessus, chaque invitation à une réunion contient un numéro gratuit, un numéro gratuit facultatif et un lien qui ouvre la liste complète de tous les numéros de téléphone à composer pour participer à une réunion donnée.</span><span class="sxs-lookup"><span data-stu-id="011e5-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="011e5-112">Pour un nouvel utilisateur, les numéros gratuits de conférence par défaut sont affectés en fonction de l’emplacement d’utilisation qui est définie dans le Centre d’administration Microsoft 365 de l’utilisateur lorsque l’utilisateur est activé pour le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="011e5-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="011e5-113">Si le pont de conférence compte un numéro de téléphone qui correspond au pays de l’utilisateur, ce numéro est automatiquement affecté comme numéro de téléphone par défaut à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="011e5-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="011e5-114">S’il n’y en a pas, le numéro défini comme numéro toll par défaut du pont de conférence sera affecté au numéro par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="011e5-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="011e5-115">Une fois le service d’audioconférence activé pour l’utilisateur, les numéros de téléphone gratuits et gratuits par défaut peuvent être modifiés à tout moment par l’administrateur client par rapport à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="011e5-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="011e5-116">Définir ou modifier le numéro de téléphone d’audioconférence par défaut pour un organisateur ou un utilisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="011e5-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="011e5-117">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="011e5-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="011e5-118">Vous devez être un administrateur du service Teams pour apporter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="011e5-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="011e5-119">Pour en [savoir plus sur l’obtention](https://docs.microsoft.com/microsoftteams/using-admin-roles) de rôles et d’autorisations d’administrateur, voir Utiliser les rôles d’administrateur Teams pour gérer Teams.</span><span class="sxs-lookup"><span data-stu-id="011e5-119">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="011e5-120">Connectez-vous au Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="011e5-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="011e5-121">Dans le groupe de navigation de gauche, cliquez sur **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="011e5-121">In the left navigation, click **Users**.</span></span>

    ![Sélection d’utilisateurs dans le Centre d’administration Microsoft Teams](media/Admin-users.png)

3. <span data-ttu-id="011e5-123">Cliquez sur le nom d’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="011e5-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="011e5-124">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="011e5-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Cliquez sur Modifier en cours d’audioconférence](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="011e5-126">Utilisez les **champs Numéro gratuit** ou Numéro **gratuit** pour entrer les numéros de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="011e5-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="011e5-127">Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions microsoft Teams périodiques et futures doivent être mises à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="011e5-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="011e5-128">Vous souhaitez utiliser Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="011e5-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="011e5-129">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="011e5-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="011e5-130">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="011e5-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="011e5-131">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="011e5-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="011e5-132">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="011e5-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="011e5-133">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="011e5-133">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="011e5-134">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="011e5-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="011e5-135">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="011e5-135">Related topics</span></span>

[<span data-ttu-id="011e5-136">Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="011e5-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="011e5-137">Modifier les numéros de téléphone de votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="011e5-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
