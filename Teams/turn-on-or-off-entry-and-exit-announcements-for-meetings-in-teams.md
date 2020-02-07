---
title: Activer ou désactiver les annonces d'entrée et de sortie des réunions dans Microsoft Teams
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
description: 'Découvrez comment activer et désactiver les annonces d’entrée et de sortie dans une réunion Microsoft Teams. '
ms.openlocfilehash: 8deb53145c95f9a370e894083de8e998b50fa9ae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832604"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="9bf33-103">Activer ou désactiver les annonces d'entrée et de sortie des réunions dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9bf33-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="9bf33-104">Lorsque vous configurez l’audioconférence dans Office 365, vous obtenez un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="9bf33-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="9bf33-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes utiliseront pour appeler une réunion Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9bf33-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="9bf33-106">Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="9bf33-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="9bf33-107">Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="9bf33-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="9bf33-108">Un code confidentiel est fourni à l’organisateur d’une réunion Microsoft Teams, qui lui permet de démarrer la réunion s’il n’a pas la possibilité de le faire en utilisant l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9bf33-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="9bf33-109">Vous pouvez cependant définir les options de telle sorte qu'un code confidentiel ne soit pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="9bf33-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="9bf33-110">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="9bf33-110">Setting meeting join options</span></span>

<span data-ttu-id="9bf33-111">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="9bf33-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9bf33-112">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="9bf33-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9bf33-113">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="9bf33-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="9bf33-114">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="9bf33-114">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="9bf33-115">Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="9bf33-115">This is selected by default.</span></span> <span data-ttu-id="9bf33-116">Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l'arrivée ou du départ des autres participants.</span><span class="sxs-lookup"><span data-stu-id="9bf33-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="9bf33-117">Sous **Type d’annonces entrée-sortie**, sélectionnez **Names or phone numbers** (Noms et numéros de téléphone) ou **Tones** (Tonalités).</span><span class="sxs-lookup"><span data-stu-id="9bf33-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="9bf33-118">Si vous sélectionnez l'option **Names or phone numbers** (Noms ou numéros de téléphone), activez ou désactivez l’option **Ask callers to record their name before joining the meeting** (Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion).</span><span class="sxs-lookup"><span data-stu-id="9bf33-118">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="9bf33-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9bf33-119">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9bf33-120">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="9bf33-120">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9bf33-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bf33-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9bf33-124">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bf33-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9bf33-125">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bf33-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9bf33-126">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9bf33-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9bf33-127">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9bf33-127">Related topics</span></span>

[<span data-ttu-id="9bf33-128">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="9bf33-128">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
