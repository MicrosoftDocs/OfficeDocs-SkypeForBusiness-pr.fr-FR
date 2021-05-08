---
title: Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Découvrez comment activer ou désactiver l’enregistrement des noms des utilisateurs lorsqu’ils rejoignent une réunion dans Skype Entreprise Online.
ms.openlocfilehash: ee6ae85946453d6065a6473ec331b93e4509ebc9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237310"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="cf253-103">Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cf253-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="cf253-104">Si vous souhaitez autoriser les utilisateurs à enregistrer leurs noms dans Teams, Consultez [Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="cf253-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="cf253-105">Lorsque vous configurationnez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone et un « pont de conférence » audio.</span><span class="sxs-lookup"><span data-stu-id="cf253-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="cf253-106">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="cf253-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="cf253-107">Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone.</span><span class="sxs-lookup"><span data-stu-id="cf253-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="cf253-108">Le pont de conférence répond à l’appelant à l’aide d’invites vocales d’un attendant automatique, puis, selon les paramètres, peut lire des notifications, demander aux appelants d’enregistrer leur nom et configurer la sécurité du code confidentiel pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="cf253-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="cf253-109">Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="cf253-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="cf253-110">Toutefois, vous pouvez configurer de sorte qu’aucun code confidentiel ne soit nécessaire pour commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="cf253-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="cf253-111">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="cf253-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="cf253-112">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  </span><span class="sxs-lookup"><span data-stu-id="cf253-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="cf253-113">Sous **Expérience de participation aux réunions**, voir la case nommée **Activer les notifications d’entrée et de sortie de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="cf253-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="cf253-114">**Sélectionné** Les appelants seront invités à enregistrer leur nom avant d’accéder à la réunion.</span><span class="sxs-lookup"><span data-stu-id="cf253-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="cf253-115">Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf253-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="cf253-116">**Effacé** Les appelants ne seront pas invités à enregistrer leur nom avant d’accéder à la réunion.</span><span class="sxs-lookup"><span data-stu-id="cf253-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="cf253-117">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cf253-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cf253-118">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="cf253-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cf253-119">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="cf253-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="cf253-120">Windows PowerShell vous permet de gérer les utilisateurs et ce qu’ils sont autorisés à faire.</span><span class="sxs-lookup"><span data-stu-id="cf253-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="cf253-121">En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="cf253-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="cf253-122">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="cf253-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cf253-123">Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf253-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="cf253-124">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cf253-124">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="cf253-125">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour plusieurs utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="cf253-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cf253-126">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf253-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="cf253-127">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cf253-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cf253-128">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cf253-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cf253-129">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cf253-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="cf253-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="cf253-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cf253-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cf253-132">Related topics</span></span>

[<span data-ttu-id="cf253-133">Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="cf253-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
