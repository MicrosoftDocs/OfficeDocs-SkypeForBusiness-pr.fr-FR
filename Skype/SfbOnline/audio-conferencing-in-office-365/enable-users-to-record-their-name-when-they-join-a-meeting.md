---
title: Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype Entreprise Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to enable or disable whether your users can record their names when they join a meeting in Skype Entreprise Online.
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850040"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="b10c0-103">Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b10c0-103">Enable users to record their name when they join a meeting</span></span>

> [!Note]
> <span data-ttu-id="b10c0-104">Si vous souhaitez autoriser les utilisateurs à enregistrer leurs noms dans Teams, Consultez [Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="b10c0-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="b10c0-105">Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone et ce que l’on appelle un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b10c0-105">When you are setting up dial-in conferencing in Skype for Business Online, you will receive phone numbers and what is called a dial-in or audio conferencing bridge.</span></span> <span data-ttu-id="b10c0-106">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="b10c0-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="b10c0-107">Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone.</span><span class="sxs-lookup"><span data-stu-id="b10c0-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b10c0-108">Le pont de conférence répond en utilisant une invite vocale à partir d’un standard automatique, puis, selon leurs paramètres, propose des notifications, demande aux appelants d’enregistrer leur nom et, pour les organisateurs de réunions, définit leur sécurité par code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="b10c0-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="b10c0-109">Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="b10c0-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="b10c0-110">Vous pouvez toutefois le régler de manière à ce qu’aucun code confidentiel ne soit nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="b10c0-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="b10c0-111">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="b10c0-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="b10c0-112">Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b10c0-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="b10c0-113">Sous **Expérience de participation aux réunions**, voir la case nommée **Activer les notifications d’entrée et de sortie de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="b10c0-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="b10c0-114">**Activé** : les appelants seront invités à enregistrer leur nom avant d’assister à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b10c0-114">**Checked** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="b10c0-115">Cette fonctionnalité est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="b10c0-115">This is selected by default.</span></span>
    
  - <span data-ttu-id="b10c0-116">**Désactivé** : les appelants ne seront pas invités à enregistrer leur nom avant d’assister à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b10c0-116">**Unchecked** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="b10c0-117">Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b10c0-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b10c0-118">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="b10c0-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b10c0-119">Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="b10c0-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="b10c0-120">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu’ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="b10c0-120">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b10c0-121">En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="b10c0-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b10c0-122">Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b10c0-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b10c0-123">Pourquoi vous devez utiliser Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b10c0-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b10c0-124">Six raisons d'utiliser Windows PowerShell pour gérer Office 365</span><span class="sxs-lookup"><span data-stu-id="b10c0-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b10c0-125">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="b10c0-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b10c0-126">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b10c0-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b10c0-127">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b10c0-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b10c0-128">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b10c0-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b10c0-129">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b10c0-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b10c0-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="b10c0-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b10c0-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b10c0-132">Related topics</span></span>

[<span data-ttu-id="b10c0-133">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="b10c0-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
