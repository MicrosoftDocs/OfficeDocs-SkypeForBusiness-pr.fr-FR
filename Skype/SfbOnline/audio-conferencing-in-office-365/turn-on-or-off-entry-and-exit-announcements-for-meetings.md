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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: a9c3788db6b5742b4f2b41961c3843b4939c315b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="4075d-103">Activer ou désactiver les annonces d'entrée et de sortie des réunions</span><span class="sxs-lookup"><span data-stu-id="4075d-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="4075d-104">Lorsque vous configurez une conférence Audio dans Office 365, vous obtiendrez un pont de téléconférence audio.</span><span class="sxs-lookup"><span data-stu-id="4075d-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="4075d-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui sera véritablement utilisée pour appeler un Skype pour une réunion commerciale ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4075d-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="4075d-106">Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="4075d-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="4075d-107">Le pont de conférence répond à l’appelant avec des invites vocales à partir d’une surveillance automatique de conférence et ensuite, en fonction de vos paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN.</span><span class="sxs-lookup"><span data-stu-id="4075d-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="4075d-108">Un code confidentiel est attribué un Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft, et il permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide d’un Skype pour application métier ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4075d-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="4075d-109">Vous pouvez, toutefois, définir afin qu’un code PIN n’est pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="4075d-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="4075d-110">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="4075d-110">Setting meeting join options</span></span>

<span data-ttu-id="4075d-111">**À l’aide de Skype les équipes Microsoft pour Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="4075d-111">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4075d-112">Dans la navigation de gauche, accédez à des **réunions** > **Les ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="4075d-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4075d-113">En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="4075d-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="4075d-114">Dans le volet **paramètres du pont** , activer ou désactiver **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="4075d-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="4075d-115">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4075d-115">This is selected by default.</span></span> <span data-ttu-id="4075d-116">Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="4075d-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="4075d-117">Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.</span><span class="sxs-lookup"><span data-stu-id="4075d-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="4075d-118">Activer ou désactiver des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.</span><span class="sxs-lookup"><span data-stu-id="4075d-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="4075d-119">Après avoir apporté vos modifications, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="4075d-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="4075d-120">Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4075d-120">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="4075d-121">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4075d-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="4075d-122">Sous **l’expérience de jointure de la réunion**, activez ou désactivez **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="4075d-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="4075d-123">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4075d-123">This is selected by default.</span></span> <span data-ttu-id="4075d-124">Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="4075d-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="4075d-125">Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.</span><span class="sxs-lookup"><span data-stu-id="4075d-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="4075d-126">Activez ou désactivez des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.</span><span class="sxs-lookup"><span data-stu-id="4075d-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="4075d-127">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4075d-127">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4075d-128">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="4075d-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4075d-129">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).</span><span class="sxs-lookup"><span data-stu-id="4075d-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="4075d-p105">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4075d-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="4075d-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4075d-133">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="4075d-134">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="4075d-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4075d-135">Windows PowerShell a de nombreux avantages de vitesse, de simplicité et de productivité qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="4075d-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="4075d-136">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4075d-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4075d-137">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4075d-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4075d-138">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4075d-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4075d-139">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4075d-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4075d-p107">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="4075d-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4075d-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4075d-142">Related topics</span></span>

[<span data-ttu-id="4075d-143">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="4075d-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
