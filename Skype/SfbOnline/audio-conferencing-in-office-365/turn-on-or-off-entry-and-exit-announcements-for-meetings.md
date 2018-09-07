---
title: Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Découvrez comment activer et désactiver les annonces d'entrée et de sortie d'une réunion Skype Entreprise Online en utilisant centre d'administration Skype Entreprise. "
ms.openlocfilehash: 8d91db2014439eb2c9e38f65215cf85d6f047157
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863262"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="f2de3-103">Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2de3-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f2de3-104">Pour plus d’informations sur les annonces d’entrée et de sortie dans Microsoft Teams, voir [Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f2de3-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="f2de3-105">Lorsque vous configurez les services d’audioconférence dans Office 365, vous obtenez un pont d'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="f2de3-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f2de3-106">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes pourront utiliser pour rejoindre une réunion Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2de3-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="f2de3-107">Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone.</span><span class="sxs-lookup"><span data-stu-id="f2de3-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f2de3-108">Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="f2de3-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f2de3-109">Un code confidentiel est attribué à l'organisateur de la réunion Skype Entreprise et permet de démarrer une réunion s'il lui est impossible de démarrer la réunion en utilisant l'application Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2de3-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="f2de3-110">Vous pouvez toute fois le régler pour qu'aucun code confidentiel ne soit nécessaire pour débuter une réunion.</span><span class="sxs-lookup"><span data-stu-id="f2de3-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f2de3-111">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="f2de3-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="f2de3-112">Dans le **Centre d'administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f2de3-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="f2de3-113">Sous **Expérience de participation aux réunions**, sélectionnez ou désélectionnez **Activer les notifications d’entrée et de sortie de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="f2de3-113">Under \*\* Meeting join experience\*\* > check or uncheck Enable meeting entry and exit notifications to be turned on This is selected by default.</span></span> <span data-ttu-id="f2de3-114">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="f2de3-114">This is selected by default.</span></span> <span data-ttu-id="f2de3-115">Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsque quelqu’un rejoindra ou quittera la réunion.</span><span class="sxs-lookup"><span data-stu-id="f2de3-115">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="f2de3-116">Sous **Type d'annonce d’entrée/sortie**, sélectionnez **Noms ou numéros de téléphone** ou **Tonalités**.</span><span class="sxs-lookup"><span data-stu-id="f2de3-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="f2de3-117">Activez ou désactivez **Demander aux appelants d’enregistrer leur nom avant de participer à la réunion**.</span><span class="sxs-lookup"><span data-stu-id="f2de3-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="f2de3-118">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f2de3-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f2de3-119">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="f2de3-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f2de3-120">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2de3-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="f2de3-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2de3-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f2de3-124">Quels avantages vous pouvez tirer de PowerShell Office 365</span><span class="sxs-lookup"><span data-stu-id="f2de3-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f2de3-125">Six raisons d'utiliser Windows PowerShell pour gérer Office 365</span><span class="sxs-lookup"><span data-stu-id="f2de3-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f2de3-126">Windows PowerShell offre de nombreux avantages en termes de rapidité, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Office 365 seul, par exemple lorsque vous désirez effectuer des modifications de paramètres pour un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2de3-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f2de3-127">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2de3-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f2de3-128">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2de3-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f2de3-129">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2de3-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f2de3-130">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2de3-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f2de3-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="f2de3-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f2de3-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f2de3-133">Related topics</span></span>

[<span data-ttu-id="f2de3-134">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="f2de3-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
