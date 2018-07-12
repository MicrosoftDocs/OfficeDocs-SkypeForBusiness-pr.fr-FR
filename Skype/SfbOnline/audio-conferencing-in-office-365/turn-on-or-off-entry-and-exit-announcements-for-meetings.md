---
title: Activer ou désactiver les annonces d'entrée et de sortie des réunions
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 9cd2c95d0dde2e61ca1f0378fe91a215bdfc2682
ms.sourcegitcommit: 57c8211047e6e6501cd1f9eefddfe4da36cb7d7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20302150"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="39ec0-103">Activer ou désactiver les annonces d'entrée et de sortie des réunions</span><span class="sxs-lookup"><span data-stu-id="39ec0-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="39ec0-104">Lorsque vous configurez les services d’audioconférence dans Office 365, vous obtenez un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="39ec0-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="39ec0-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui utiliseront des personnes à appeler un Skype de réunion Microsoft Teams ou de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="39ec0-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="39ec0-106">Le pont de conférence répond à un appel d’un utilisateur qui est qui se connectent à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="39ec0-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="39ec0-107">Le pont de conférence répond à l’appelant à invites vocales à partir d’un standard automatique de conférence et, en fonction de vos paramètres, peut diffuser les notifications, poser aux appelants à enregistrer leur nom et configurer la sécurité du code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="39ec0-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="39ec0-108">Un code confidentiel est attribué à un Skype pour l’organisateur de réunion Microsoft Teams ou de l’entreprise, et vous permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide d’un Skype pour l’application Microsoft Teams ou de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="39ec0-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="39ec0-109">Vous pouvez, toutefois, l’afin qu’un code confidentiel n’est pas nécessaire de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="39ec0-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="39ec0-110">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="39ec0-110">Setting meeting join options</span></span>

<span data-ttu-id="39ec0-111">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="39ec0-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="39ec0-112">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="39ec0-113">En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="39ec0-114">Dans le volet **paramètres du pont** , activez ou désactivez **Activer l’accès à la réunion et quitter notifications être activée**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="39ec0-115">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="39ec0-115">This is selected by default.</span></span> <span data-ttu-id="39ec0-116">Si vous la désactivez, les utilisateurs qui ont déjà joint la réunion ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="39ec0-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="39ec0-117">Sous **type d’entrée/sortie annonce**, sélectionnez les **noms ou les numéros de téléphone** ou des **tonalités**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="39ec0-118">Activer ou désactiver **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="39ec0-119">Une fois que vous apportez vos modifications, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="39ec0-120">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="39ec0-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="39ec0-121">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="39ec0-122">Sous **l’expérience de participation aux réunions**, activez ou désactivez **Activer l’accès à la réunion et quitter des notifications à être activée**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="39ec0-123">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="39ec0-123">This is selected by default.</span></span> <span data-ttu-id="39ec0-124">Si vous la désactivez, les utilisateurs qui ont déjà joint la réunion ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="39ec0-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="39ec0-125">Sous **type d’entrée/sortie annonce**, sélectionnez les **noms ou les numéros de téléphone** ou des **tonalités**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="39ec0-126">Activez ou désactivez **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="39ec0-127">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="39ec0-127">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="39ec0-128">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="39ec0-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="39ec0-129">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="39ec0-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="39ec0-p105">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39ec0-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="39ec0-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39ec0-133">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="39ec0-134">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="39ec0-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="39ec0-135">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="39ec0-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="39ec0-136">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39ec0-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="39ec0-137">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39ec0-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="39ec0-138">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39ec0-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="39ec0-139">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="39ec0-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="39ec0-p107">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="39ec0-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="39ec0-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="39ec0-142">Related topics</span></span>

[<span data-ttu-id="39ec0-143">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="39ec0-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
