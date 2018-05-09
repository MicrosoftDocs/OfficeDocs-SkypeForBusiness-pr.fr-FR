---
title: Démarrer une conférence Audio par téléphone sans un code confidentiel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 4deb415e9fd7154d72b7d598bcc5dfb8eabed6ed
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="fbbbc-103">Démarrer une conférence Audio par téléphone sans un code confidentiel</span><span class="sxs-lookup"><span data-stu-id="fbbbc-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="fbbbc-104">Il peut être frustrant pour les utilisateurs qui se connectent à une réunion à être conservés dans la salle d’attente de la réunion à l’écoute de la musique, car le Skype pour l’organisateur de réunion Microsoft Teams ou de l’entreprise n’a pas démarré la réunion.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="fbbbc-105">Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est requis pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="fbbbc-106">Vous pouvez configurer il afin que tout le monde peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel démarrer la réunion.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="fbbbc-107">Le Centre d'administration Skype Entreprise permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="fbbbc-108">Un code confidentiel n’est pas requis pour l’organisateur de la réunion si une personne a démarré la réunion à partir d’un Skype pour l’application Microsoft Teams ou de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="fbbbc-109">Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="fbbbc-110">Le code confidentiel pour les réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Services d’audioconférence** et sont activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="fbbbc-111">Voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md) et [messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="fbbbc-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="fbbbc-112">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="fbbbc-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="fbbbc-113">![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="fbbbc-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="fbbbc-114">Dans la navigation de gauche, cliquez sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="fbbbc-115">Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** dans la partie supérieure de la page.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="fbbbc-116">Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="fbbbc-117">Dans le volet de **fournisseur de pont de conférence** , activez ou désactivez Autoriser non authentifié **appelants sont les premiers à une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié rejoint**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="fbbbc-118">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-118">Click **Apply**.</span></span> 

<span data-ttu-id="fbbbc-119">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="fbbbc-119">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="fbbbc-120">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="fbbbc-121">Dans la liste, sélectionnez l’utilisateur, dans le volet Actions, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="fbbbc-122">Sur la page de propriétés de l’utilisateur, sous **options de la réunion**, activez ou désactivez Autoriser non authentifié **appelants sont les premiers à une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié rejoint**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="fbbbc-123">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-123">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
 <span data-ttu-id="fbbbc-124">**Utilisation de Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="fbbbc-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="fbbbc-125">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="fbbbc-126">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fbbbc-126">What else should you know?</span></span>

- <span data-ttu-id="fbbbc-127">Si vous souhaitez réinitialiser le code confidentiel, consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="fbbbc-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="fbbbc-128">Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="fbbbc-129">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant est invité s’il est l’organisateur ; Si il indique Oui, il vous demandé pour son code confidentiel et après des entrées le code confidentiel, il démarre la réunion et l’utilisateur sera participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="fbbbc-130">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si il est l’organisateur et il serez jamais pour le code confidentiel ; la réunion est déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="fbbbc-131">Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est désactivée :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="fbbbc-132">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="fbbbc-133">Étant donné que le paramètre de l’organisateur est défini sur désactivé, la réunion démarre et les appelants anonymes participerez à la réunion.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="fbbbc-134">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel, la réunion est déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fbbbc-135">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="fbbbc-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fbbbc-136">Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="fbbbc-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="fbbbc-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="fbbbc-140">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-140">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="fbbbc-141">Les meilleures façons de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbbbc-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="fbbbc-142">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="fbbbc-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="fbbbc-143">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="fbbbc-143">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="fbbbc-144">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fbbbc-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="fbbbc-145">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fbbbc-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fbbbc-146">Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fbbbc-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="fbbbc-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="fbbbc-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fbbbc-149">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fbbbc-149">Related topics</span></span>

[<span data-ttu-id="fbbbc-150">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="fbbbc-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
