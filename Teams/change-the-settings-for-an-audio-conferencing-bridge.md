---
title: Modifier les paramètres d’un pont d’audioconférence.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modifiez les paramètres du pont de conférence audio, y compris les notifications d’entrée et de sortie, appelez les appelants et appelez-les pour enregistrer leur nom.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102640"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="12a01-103">Modifier les paramètres d’un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="12a01-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="12a01-104">Lors de la configuration de l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone pour vos utilisateurs, ainsi qu’un « pont de conférence audio ».</span><span class="sxs-lookup"><span data-stu-id="12a01-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="12a01-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="12a01-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="12a01-106">Ces numéros de téléphone sont utilisés lorsque les appelants appellent une réunion.</span><span class="sxs-lookup"><span data-stu-id="12a01-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="12a01-107">Le numéro de téléphone est inclus dans la partie inférieure de l’invitation à la réunion Skype Entreprise ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12a01-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="12a01-108">Le pont de conférence répond à un appel et invite l’appelant à lire les invites vocales à l’aide d’un employé de la réunion automatique de la réunion, puis, selon vos paramètres, il peut lire les notifications, demander aux appelants d’enregistrer leur nom et de contrôler les paramètres du code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="12a01-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="12a01-109">Les piN sont attribués aux organisateurs de la réunion pour leur permettre de commencer une réunion lorsqu’ils n’utilisent pas une application Skype Entreprise ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12a01-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="12a01-110">Un code confidentiel n’est nécessaire pour l’organisateur de la réunion que si un utilisateur de l’application Skype Entreprise ou Microsoft Teams n’a pas encore commencé la réunion.</span><span class="sxs-lookup"><span data-stu-id="12a01-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="12a01-111">Si tout le monde compose un numéro pour se rendre à la réunion, le code confidentiel est nécessaire pour que l’organisateur puisse commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="12a01-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="12a01-113">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12a01-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="12a01-114">Dans le navigateur de gauche, allez sur **des ponts de conférence**  >  **Réunions.**</span><span class="sxs-lookup"><span data-stu-id="12a01-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="12a01-115">En haut de la page **Ponts de conférence,** cliquez **sur Paramètres du pont.**</span><span class="sxs-lookup"><span data-stu-id="12a01-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12a01-116">Dans le **volet Paramètres du** pont, sélectionnez :</span><span class="sxs-lookup"><span data-stu-id="12a01-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="12a01-117">**Notifications d’entrée et de sortie des réunions** Si vous la désactiver, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l’arrivée ou du départ d’une personne.</span><span class="sxs-lookup"><span data-stu-id="12a01-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="12a01-118">Lorsque vous activerez les **notifications d’entrée et de sortie** des réunions, vous pouvez sélectionner ces options :</span><span class="sxs-lookup"><span data-stu-id="12a01-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="12a01-119">**Noms ou numéros de téléphone** Lorsque les utilisateurs appellent pour rejoindre une réunion, leur numéro de téléphone est joué lorsqu’ils la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="12a01-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="12a01-120">**Sonnerie** Lorsque les utilisateurs composent un numéro pour rejoindre une réunion, une sonnerie est sonore lorsqu’ils la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="12a01-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="12a01-121">**Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion** Si vous la désactiver, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre une réunion.</span><span class="sxs-lookup"><span data-stu-id="12a01-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="12a01-122">Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste des longueurs **du** code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="12a01-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="12a01-123">Pour indiquer si vous pouvez envoyer des courriers électroniques à vos utilisateurs, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leur configuration d’audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="12a01-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="12a01-124">Consultez les messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs [paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change-in-teams.md) dans Microsoft Teams ou dans les messages électroniques envoyés aux utilisateurs lorsque leurs [paramètres](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) changent dans Skype Entreprise Online pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="12a01-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="12a01-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12a01-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="12a01-126">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="12a01-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="12a01-127">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)</span><span class="sxs-lookup"><span data-stu-id="12a01-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="12a01-128">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="12a01-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="12a01-129">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="12a01-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="12a01-130">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="12a01-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12a01-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="12a01-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="12a01-132">[Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="12a01-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="12a01-133">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="12a01-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="12a01-134">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="12a01-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="12a01-135">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="12a01-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="12a01-136">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="12a01-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="12a01-137">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="12a01-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="12a01-p107">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="12a01-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12a01-140">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="12a01-140">Related topics</span></span>

[<span data-ttu-id="12a01-141">Configurer Audioconférence pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12a01-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="12a01-142">Configurer l’audioconférence pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="12a01-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)