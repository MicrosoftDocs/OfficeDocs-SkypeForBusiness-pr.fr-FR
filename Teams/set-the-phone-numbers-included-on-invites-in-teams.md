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
description: Pour créer un numéro de téléphone par défaut, les appelants pourront rejoindre une Microsoft Teams réunion.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117172"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="06b9b-103">Définir les numéros de téléphone inclus sur les invitations dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06b9b-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="06b9b-104">L’audioconférence dans Microsoft 365 et Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams et d’autoriser les utilisateurs à s’y rendre par téléphone.</span><span class="sxs-lookup"><span data-stu-id="06b9b-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="06b9b-105">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="06b9b-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="06b9b-106">Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="06b9b-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06b9b-107">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="06b9b-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="06b9b-108">Affectation initiale des numéros de téléphone inclus dans les invitations aux réunions pour les nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="06b9b-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="06b9b-109">Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour l’audioconférence sont définis par le numéro de téléphone gratuit de conférence par défaut et les paramètres d’utilisateur du numéro de téléphone gratuit de conférence par défaut.</span><span class="sxs-lookup"><span data-stu-id="06b9b-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="06b9b-110">Chaque paramètre spécifie le numéro gratuit et gratuit qui sera inclus dans l’invitation à la réunion d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="06b9b-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="06b9b-111">Comme indiqué ci-dessus, chaque invitation à une réunion contient un numéro gratuit, un numéro gratuit facultatif et un lien qui ouvre la liste complète de tous les numéros de téléphone à composer pour participer à une réunion donnée.</span><span class="sxs-lookup"><span data-stu-id="06b9b-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="06b9b-112">Pour un nouvel utilisateur, les numéros gratuits de conférence par défaut sont affectés en fonction de l’emplacement d’utilisation qui est définie dans le centre d’administration Microsoft 365 de l’utilisateur lorsque l’utilisateur est activé pour le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="06b9b-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="06b9b-113">Si le pont de conférence compte un numéro de téléphone qui correspond au pays de l’utilisateur, ce numéro est automatiquement affecté comme numéro de téléphone par défaut à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="06b9b-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="06b9b-114">S’il n’y en a pas, le numéro défini comme numéro toll par défaut du pont de conférence sera affecté au numéro de téléphone par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="06b9b-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="06b9b-115">Une fois le service d’audioconférence activé pour l’utilisateur, les numéros de téléphone gratuits et gratuits par défaut peuvent être modifiés par l’administrateur client par rapport à leurs valeurs initiales à tout moment.</span><span class="sxs-lookup"><span data-stu-id="06b9b-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="06b9b-116">Définir ou modifier le numéro de téléphone d’audioconférence par défaut d’un organisateur ou d’un utilisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="06b9b-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="06b9b-117">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="06b9b-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="06b9b-118">Vous devez être un administrateur du service Teams pour apporter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="06b9b-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="06b9b-119">Voir [Gérer Teams grâce aux rôles d’administrateur Teams](./using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="06b9b-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="06b9b-120">Connectez-vous au Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="06b9b-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="06b9b-121">Dans le groupe de navigation de gauche, cliquez sur **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="06b9b-121">In the left navigation, click **Users**.</span></span>

    ![Sélection d’utilisateurs dans le Centre Microsoft Teams’administration](media/Admin-users.png)

3. <span data-ttu-id="06b9b-123">Cliquez sur le nom d’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="06b9b-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="06b9b-124">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="06b9b-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Cliquez sur Modifier en cours d’audioconférence](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="06b9b-126">Utilisez les **champs Numéro gratuit** ou Numéro **gratuit** pour entrer les numéros de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="06b9b-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06b9b-127">Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions périodiques et futures Microsoft Teams doivent être mises à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="06b9b-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="06b9b-128">Vous souhaitez utiliser Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06b9b-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="06b9b-129">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="06b9b-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="06b9b-130">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="06b9b-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="06b9b-131">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="06b9b-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="06b9b-132">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="06b9b-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="06b9b-133">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="06b9b-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="06b9b-134">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="06b9b-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="06b9b-135">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="06b9b-135">Related topics</span></span>

[<span data-ttu-id="06b9b-136">Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="06b9b-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="06b9b-137">Modifier les numéros de téléphone de votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="06b9b-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)