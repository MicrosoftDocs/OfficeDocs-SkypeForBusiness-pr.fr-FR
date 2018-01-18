---
title: "Démarrer une conférence Audio par téléphone sans code confidentiel"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: c77921af87cab23b475c31205da4661755c56961
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="e60da-103">Démarrer une conférence Audio par téléphone sans code confidentiel</span><span class="sxs-lookup"><span data-stu-id="e60da-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="e60da-104">Il peut être frustrant pour les utilisateurs qui se connectent à une réunion qui se tiendra dans la salle d’attente de la réunion à l’écoute de musique car le Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft n’a pas démarré la réunion.</span><span class="sxs-lookup"><span data-stu-id="e60da-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="e60da-105">Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="e60da-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="e60da-106">Vous pouvez configurer afin que toute personne peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel pour démarrer la réunion.</span><span class="sxs-lookup"><span data-stu-id="e60da-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="e60da-107">Vous pouvez utiliser le Skype pour le centre d’administration Business pour activer ou désactiver ce paramètre pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e60da-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="e60da-108">Un code confidentiel n’est pas obligatoire pour l’organisateur de la réunion si quelqu'un a démarré la réunion à partir d’un Skype pour application métier ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e60da-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="e60da-109">Un code PIN n’est requis lors de leur réunion joint à un organisateur de réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="e60da-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="e60da-110">Le code confidentiel de réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Conférence Audio** et sont activées pour la conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="e60da-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e60da-111">Reportez-vous à la section [Envoyer un courrier électronique à un utilisateur avec les informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) et dans les [courriels qui sont automatiquement envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="e60da-112">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="e60da-112">Enable or disable anonymous callers from joining a meeting</span></span>

1. <span data-ttu-id="e60da-113">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="e60da-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e60da-114">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="e60da-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e60da-115">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e60da-115">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
4. <span data-ttu-id="e60da-116">Dans la liste, sélectionnez l’utilisateur et dans le volet Actions, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e60da-116">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
5. <span data-ttu-id="e60da-117">Sur la page de propriétés de l’utilisateur, sous **options de la réunion**, activez ou désactivez les appelants d’autoriser non authentifié **pour être les premiers dans une réunion. Si non, puis ils attendra dans la salle d’attente jusqu'à ce qu’un utilisateur authentifié de jointures**.</span><span class="sxs-lookup"><span data-stu-id="e60da-117">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
6. <span data-ttu-id="e60da-118">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e60da-118">Click **Save**.</span></span> 
    
 <span data-ttu-id="e60da-119">**Pour activer ou désactiver des appelants anonymes à toutes les réunions de l’utilisateur à l’aide de Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="e60da-119">**To enable or disable anonymous callers to all of your user's meetings using Windows Powershell**</span></span>
  
- <span data-ttu-id="e60da-120">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e60da-120">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="e60da-121">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e60da-121">What else should you know?</span></span>

- <span data-ttu-id="e60da-122">Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la rubrique [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="e60da-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="e60da-123">Si l’accès anonyme, ou un code confidentiel démarrer une réunion, ne nécessitant ne pas est activé :</span><span class="sxs-lookup"><span data-stu-id="e60da-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="e60da-124">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant demandera s’il est l’organisateur ; Si il répond Oui, il serez invité pour son code confidentiel et une fois qu’il le code PIN est une entrée, la réunion démarre et l’utilisateur doit joindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="e60da-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="e60da-125">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : un appelant ne sera pas invité si il est l’organisateur et il serez jamais de code confidentiel ; la réunion est déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="e60da-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="e60da-126">Si l’accès anonyme, ou un code confidentiel démarrer une réunion, ne nécessitant ne pas est désactivé :</span><span class="sxs-lookup"><span data-stu-id="e60da-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="e60da-127">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant ne sera pas invité si elle en est l’organisateur et elle demandera jamais de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="e60da-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="e60da-128">Étant donné que le paramètre de l’organisateur est défini sur off, la réunion démarre et les appelants anonymes seront joindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="e60da-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="e60da-129">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : un appelant ne sera pas invité si elle en est l’organisateur et elle demandera jamais le PIN, la réunion a déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="e60da-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e60da-130">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="e60da-130">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e60da-131">Pour gagner du temps ou automatiser cette procédure pour plusieurs utilisateurs, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="e60da-131">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="e60da-p104">Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e60da-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="e60da-135">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e60da-135">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="e60da-136">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="e60da-136">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e60da-137">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="e60da-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="e60da-138">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e60da-138">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e60da-139">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e60da-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e60da-140">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e60da-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e60da-141">Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e60da-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e60da-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="e60da-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e60da-144">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e60da-144">Related topics</span></span>

[<span data-ttu-id="e60da-145">Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e60da-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
