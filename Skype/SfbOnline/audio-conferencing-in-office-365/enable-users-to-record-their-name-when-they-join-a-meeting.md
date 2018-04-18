---
title: Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: a90eebdc0d75b96feeac94b07333fed47756478b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="311ad-103">Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion</span><span class="sxs-lookup"><span data-stu-id="311ad-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="311ad-104">Lorsque vous configurez une conférence Audio dans Office 365, vous recevrez les numéros de téléphone et ce que l'on appelle un pont de téléconférence audio.</span><span class="sxs-lookup"><span data-stu-id="311ad-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="311ad-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="311ad-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="311ad-106">Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="311ad-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="311ad-107">Le pont de conférence répond à l’appelant avec des invites vocales de surveillance automatique et ensuite, en fonction de leurs paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="311ad-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="311ad-108">Les broches sont donnés aux organisateurs des réunions pour pouvoir démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="311ad-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="311ad-109">Toutefois, vous pouvez configurer un code confidentiel n’est pas requis pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="311ad-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="311ad-110">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="311ad-110">Set whether callers should record their name</span></span>

<span data-ttu-id="311ad-111">**À l’aide de Skype les équipes Microsoft pour Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="311ad-111">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="311ad-112">Dans la navigation de gauche, accédez à des **réunions** > **Les ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="311ad-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="311ad-113">En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="311ad-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="311ad-114">Activer ou désactiver **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="311ad-114">Enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span>

4. <span data-ttu-id="311ad-115">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="311ad-115">Click **Apply**.</span></span>


<span data-ttu-id="311ad-116">**À l’aide de la Skype pour entreprise Admin Center**</span><span class="sxs-lookup"><span data-stu-id="311ad-116">**Using the Skype for Business Admin Center**</span></span>
    
1. <span data-ttu-id="311ad-117">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="311ad-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="311ad-118">Sous **l’expérience de jointure de la réunion**, consultez la case à cocher intitulée **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="311ad-118">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="311ad-119">**Sélectionné** Vous demandera d’appelants pour enregistrer leur nom avant leur entrée à la réunion.</span><span class="sxs-lookup"><span data-stu-id="311ad-119">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="311ad-120">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="311ad-120">This is selected by default.</span></span>
    
  - <span data-ttu-id="311ad-121">**Désactivée** Les appelants ne seront pas invités à enregistrer leur nom avant leur entrée à la réunion.</span><span class="sxs-lookup"><span data-stu-id="311ad-121">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="311ad-122">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="311ad-122">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="311ad-123">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="311ad-123">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="311ad-124">Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="311ad-124">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="311ad-125">Windows PowerShell est la gestion des utilisateurs et les utilisateurs sont autorisés à faire.</span><span class="sxs-lookup"><span data-stu-id="311ad-125">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="311ad-126">En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="311ad-126">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="311ad-127">Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="311ad-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="311ad-128">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="311ad-128">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="311ad-129">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="311ad-129">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="311ad-130">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="311ad-130">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="311ad-131">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="311ad-131">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="311ad-132">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="311ad-132">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="311ad-133">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="311ad-133">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="311ad-134">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="311ad-134">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="311ad-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="311ad-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="311ad-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="311ad-137">Related topics</span></span>

[<span data-ttu-id="311ad-138">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="311ad-138">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
