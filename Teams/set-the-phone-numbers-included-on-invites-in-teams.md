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
description: Suivez ces étapes pour créer un numéro de téléphone par défaut permettant aux appelants de participer à une réunion Microsoft Teams.
ms.openlocfilehash: 22950bed0b09caf96e9fc26060f466eb6c00ff30
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905596"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="bb40b-103">Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb40b-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="bb40b-104">L’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis de permettre aux utilisateurs de se connecter à ces réunions à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="bb40b-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="bb40b-105">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bb40b-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="bb40b-106">Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="bb40b-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb40b-107">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="bb40b-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="bb40b-108">Attribution initiale des numéros de téléphone inclus dans les invitations aux réunions pour les nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="bb40b-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="bb40b-109">Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour les conférences audio sont définis par le numéro de téléphone payant par défaut et les paramètres de l’utilisateur numéro de téléphone gratuit pour la Conférence par défaut.</span><span class="sxs-lookup"><span data-stu-id="bb40b-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="bb40b-110">Chacun d’eux spécifie le numéro payant et le numéro gratuit inclus dans l’invitation à la réunion d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="bb40b-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="bb40b-111">Comme indiqué plus haut, chaque invitation à une réunion contient un numéro payant, un numéro gratuit facultatif et un lien permettant d’ouvrir la liste complète de tous les numéros de téléphone rendez-vous qui peuvent être utilisés pour participer à une réunion donnée.</span><span class="sxs-lookup"><span data-stu-id="bb40b-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="bb40b-112">Pour un nouvel utilisateur, les numéros payants de la Conférence par défaut sont attribués en fonction de l’emplacement d’utilisation défini dans le centre d’administration Office 365 de l’utilisateur lorsque l’utilisateur est activé pour le service de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="bb40b-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Office 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="bb40b-113">S’il existe un numéro payant dans le pont de conférence qui correspond au pays de l’utilisateur, ce numéro sera automatiquement attribué en tant que numéro payant par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb40b-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="bb40b-114">Si ce n’est pas le cas, le numéro défini en tant que numéro payant par défaut du pont de conférence sera affecté en tant que numéro payant par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb40b-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="bb40b-115">Lorsque l’utilisateur est activé pour le service d’audioconférence, les numéros de téléphone gratuits et payants par défaut de l’utilisateur peuvent être modifiés à tout moment par l’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="bb40b-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="bb40b-116">Définir ou changer le numéro de téléphone de l’audioconférence par défaut pour un utilisateur ou un organisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="bb40b-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="bb40b-117">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="bb40b-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bb40b-118">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="bb40b-118">In the left navigation, click **Users**.</span></span>

    ![Sélection des utilisateurs dans le centre d’administration Microsoft teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="bb40b-120">Cliquez sur le nom d’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="bb40b-120">Click the user name from the list of available users.</span></span>

3. <span data-ttu-id="bb40b-121">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bb40b-121">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Cliquez sur modifier en regard de audioconférence](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="bb40b-123">Utilisez les champs **numéro payant** ou **numéro gratuit** pour entrer les numéros de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb40b-123">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="bb40b-124">Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions périodiques et périodiques de Microsoft teams doivent être mises à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="bb40b-124">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="bb40b-125">Vous souhaitez utiliser Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="bb40b-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="bb40b-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb40b-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb40b-129">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb40b-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bb40b-130">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb40b-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bb40b-131">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="bb40b-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="bb40b-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="bb40b-132">Related topics</span></span>

[<span data-ttu-id="bb40b-133">Tester ou acheter l’audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="bb40b-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="bb40b-134">Modifier les numéros de téléphone de votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="bb40b-134">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
