---
title: Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Microsoft teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
- seo-marvel-apr2020
description: L’administrateur peut en savoir plus sur la façon d’activer ou de désactiver les annonces d’entrée et de sortie dans une réunion Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372203"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="76ea1-103">Activer ou désactiver les annonces d'entrée et de sortie des réunions dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76ea1-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="76ea1-104">Lorsque vous configurez l’audioconférence dans Microsoft 365 ou Office 365, vous obtiendrez un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="76ea1-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="76ea1-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes utiliseront pour appeler une réunion Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76ea1-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="76ea1-106">Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="76ea1-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="76ea1-107">Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="76ea1-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="76ea1-108">Un code confidentiel est fourni à l’organisateur d’une réunion Microsoft Teams, qui lui permet de démarrer la réunion s’il n’a pas la possibilité de le faire en utilisant l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76ea1-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="76ea1-109">Vous pouvez cependant définir les options de telle sorte qu'un code confidentiel ne soit pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="76ea1-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="76ea1-110">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="76ea1-110">Setting meeting join options</span></span>

<span data-ttu-id="76ea1-111">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="76ea1-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="76ea1-112">Pour effectuer ces modifications, vous devez être un administrateur de service Teams.</span><span class="sxs-lookup"><span data-stu-id="76ea1-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="76ea1-113">Pour plus d’informations sur l’accès aux rôles d’administrateur et aux autorisations, voir [utiliser les rôles d’administrateur d’équipes pour gérer teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="76ea1-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="76ea1-114">Connectez-vous au centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="76ea1-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="76ea1-115">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="76ea1-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="76ea1-116">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="76ea1-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="76ea1-117">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="76ea1-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="76ea1-118">Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="76ea1-118">This is selected by default.</span></span> <span data-ttu-id="76ea1-119">Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l'arrivée ou du départ des autres participants.</span><span class="sxs-lookup"><span data-stu-id="76ea1-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="76ea1-120">Sous **Type d'annonce d’entrée/sortie**, sélectionnez **Noms ou numéros de téléphone** ou **Tonalités**.</span><span class="sxs-lookup"><span data-stu-id="76ea1-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="76ea1-121">Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants distants.</span><span class="sxs-lookup"><span data-stu-id="76ea1-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="76ea1-122">Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes).</span><span class="sxs-lookup"><span data-stu-id="76ea1-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="76ea1-123">Si vous sélectionnez l'option **Names or phone numbers** (Noms ou numéros de téléphone), activez ou désactivez l’option **Ask callers to record their name before joining the meeting** (Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion).</span><span class="sxs-lookup"><span data-stu-id="76ea1-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="76ea1-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="76ea1-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="76ea1-125">Vous voulez en savoir plus sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ea1-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="76ea1-126">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="76ea1-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="76ea1-127">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="76ea1-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="76ea1-128">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="76ea1-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="76ea1-129">Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ea1-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="76ea1-130">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ea1-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="76ea1-131">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="76ea1-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="76ea1-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="76ea1-132">Related topics</span></span>

[<span data-ttu-id="76ea1-133">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="76ea1-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
