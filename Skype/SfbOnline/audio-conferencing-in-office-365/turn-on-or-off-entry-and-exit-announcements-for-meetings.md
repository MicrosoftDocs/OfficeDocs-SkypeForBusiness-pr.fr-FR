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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Découvrez comment activer et désactiver les annonces d'entrée et de sortie d'une réunion Skype Entreprise Online en utilisant centre d'administration Skype Entreprise. "
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237570"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="7953a-103">Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7953a-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="7953a-104">Pour plus d’informations sur les annonces d’entrée et de sortie dans Microsoft Teams, voir [Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="7953a-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="7953a-105">Lorsque vous configurationnez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="7953a-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="7953a-106">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes pourront utiliser pour rejoindre une réunion Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7953a-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="7953a-107">Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone.</span><span class="sxs-lookup"><span data-stu-id="7953a-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="7953a-108">Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="7953a-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="7953a-109">Un code confidentiel est attribué à l'organisateur de la réunion Skype Entreprise et permet de démarrer une réunion s'il lui est impossible de démarrer la réunion en utilisant l'application Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7953a-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="7953a-110">Vous pouvez toute fois le régler pour qu'aucun code confidentiel ne soit nécessaire pour débuter une réunion.</span><span class="sxs-lookup"><span data-stu-id="7953a-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="7953a-111">Définir les options de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="7953a-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="7953a-112">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  </span><span class="sxs-lookup"><span data-stu-id="7953a-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="7953a-113">Sous **Expérience de participation à une réunion,** activez ou activez ou non les notifications d’entrée et de sortie de **réunion.**</span><span class="sxs-lookup"><span data-stu-id="7953a-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="7953a-114">Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="7953a-114">This is selected by default.</span></span> <span data-ttu-id="7953a-115">Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l'arrivée ou du départ des autres participants.</span><span class="sxs-lookup"><span data-stu-id="7953a-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="7953a-116">Sous **Type d'annonce d’entrée/sortie**, sélectionnez **Noms ou numéros de téléphone** ou **Tonalités**.</span><span class="sxs-lookup"><span data-stu-id="7953a-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="7953a-117">Cochez ou **décochez demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion.**</span><span class="sxs-lookup"><span data-stu-id="7953a-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="7953a-118">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7953a-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7953a-119">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="7953a-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7953a-120">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7953a-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="7953a-121">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="7953a-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7953a-122">En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="7953a-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7953a-123">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="7953a-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7953a-124">Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7953a-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7953a-125">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7953a-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="7953a-126">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="7953a-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="7953a-127">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7953a-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7953a-128">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7953a-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="7953a-129">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7953a-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="7953a-130">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7953a-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="7953a-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="7953a-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7953a-133">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="7953a-133">Related topics</span></span>

[<span data-ttu-id="7953a-134">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="7953a-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
