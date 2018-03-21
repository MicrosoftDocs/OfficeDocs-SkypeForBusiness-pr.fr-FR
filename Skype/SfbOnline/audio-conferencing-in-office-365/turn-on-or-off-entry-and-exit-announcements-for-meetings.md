---
title: "Activer ou désactiver les annonces d'entrée et de sortie des réunions"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
ms.openlocfilehash: ca109a1e6a1538c6561e8f5a6e29bd0f70cf5efe
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="6fe14-103">Activer ou désactiver les annonces d'entrée et de sortie des réunions</span><span class="sxs-lookup"><span data-stu-id="6fe14-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="6fe14-104">Lorsque vous configurez une conférence Audio dans Office 365, vous obtiendrez un pont de téléconférence audio.</span><span class="sxs-lookup"><span data-stu-id="6fe14-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6fe14-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui sera véritablement utilisée pour appeler un Skype pour une réunion commerciale ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fe14-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="6fe14-106">Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="6fe14-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6fe14-107">Le pont de conférence répond à l’appelant avec des invites vocales à partir d’une surveillance automatique de conférence et ensuite, en fonction de vos paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN.</span><span class="sxs-lookup"><span data-stu-id="6fe14-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="6fe14-108">Un code confidentiel est attribué un Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft, et il permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide d’un Skype pour application métier ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fe14-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="6fe14-109">Vous pouvez, toutefois, définir afin qu’un code PIN n’est pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="6fe14-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="6fe14-110">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="6fe14-110">Setting meeting join options</span></span>

1. <span data-ttu-id="6fe14-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="6fe14-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6fe14-112">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6fe14-113">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="6fe14-114">Sous **l’expérience de jointure de la réunion**, activez ou désactivez **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-114">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="6fe14-115">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="6fe14-115">This is selected by default.</span></span> <span data-ttu-id="6fe14-116">Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="6fe14-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="6fe14-117">Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
6. <span data-ttu-id="6fe14-118">Activez ou désactivez des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-118">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="6fe14-119">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6fe14-119">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6fe14-120">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="6fe14-120">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6fe14-121">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).</span><span class="sxs-lookup"><span data-stu-id="6fe14-121">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="6fe14-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fe14-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="6fe14-125">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fe14-125">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="6fe14-126">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="6fe14-126">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="6fe14-127">Windows PowerShell a de nombreux avantages de vitesse, de simplicité et de productivité qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="6fe14-127">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="6fe14-128">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fe14-128">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6fe14-129">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6fe14-129">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6fe14-130">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6fe14-130">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6fe14-131">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6fe14-131">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="6fe14-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="6fe14-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6fe14-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6fe14-134">Related topics</span></span>

[<span data-ttu-id="6fe14-135">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="6fe14-135">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
