---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment réinitialiser le code confidentiel d’un utilisateur pour l’audioconférence dans Microsoft Teams et apprenez les faits importants sur les code confidentiels.
ms.openlocfilehash: 1ee3360668084bf6bf99b3ede25584ce9800dd5b
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861438"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="419b1-103">Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="419b1-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="419b1-104">Un code confidentiel est un code composé de nombres, créé pour chaque utilisateur de Microsoft Teams activé pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="419b1-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="419b1-105">Les conférences audioconférences sont utilisées par les organisateurs de la réunion pour identifier qu’ils en sont l’organisateur et les autoriser à démarrer une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="419b1-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="419b1-106">S’ils utilisent l’application Microsoft Teams pour démarrer la réunion, un code confidentiel n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="419b1-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="419b1-107">Si un utilisateur oublie son code confidentiel et qu’il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l’audioconférence, un administrateur peut réinitialiser son code confidentiel ou réinitialiser son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="419b1-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="419b1-108">Les réunions peuvent être démarrées lorsqu’un utilisateur authentifié participe à l’aide de l’application Microsoft Teams ou lorsque l’organisateur participe avec son code confidentiel par téléphone.</span><span class="sxs-lookup"><span data-stu-id="419b1-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="419b1-109">Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence.</span><span class="sxs-lookup"><span data-stu-id="419b1-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="419b1-110">Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="419b1-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="419b1-111">Réinitialiser le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="419b1-111">Reset a user's PIN</span></span>

<span data-ttu-id="419b1-112">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="419b1-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="419b1-113">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="419b1-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="419b1-114">Cliquez **sur Modifier.**</span><span class="sxs-lookup"><span data-stu-id="419b1-114">Click **Edit**.</span></span>

3. <span data-ttu-id="419b1-115">Sous **Audioconférence,** cliquez sur **Réinitialiser le code confidentiel.**</span><span class="sxs-lookup"><span data-stu-id="419b1-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="419b1-116">Cliquez sur **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="419b1-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="419b1-117">Réinitialiser le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="419b1-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="419b1-118">Aider l’utilisateur à se rendre sur [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .</span><span class="sxs-lookup"><span data-stu-id="419b1-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="419b1-119">Cliquez sur **Réinitialiser le code confidentiel.**</span><span class="sxs-lookup"><span data-stu-id="419b1-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="419b1-120">Pour GCCH, voir https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing : .</span><span class="sxs-lookup"><span data-stu-id="419b1-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="419b1-121">Que devez-vous savoir d'autre sur les codes confidentiels ?</span><span class="sxs-lookup"><span data-stu-id="419b1-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="419b1-122">Pour des raisons de sécurité, le code confidentiel n’est présenté qu’une fois à un administrateur lors de la réinitialisation du code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="419b1-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="419b1-123">Une fois le code confidentiel réinitialisé par un administrateur, il s’intitialise \*\*\*\*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="419b1-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="419b1-124">L’envoi automatique de courriers électroniques aux utilisateurs est activé par défaut et les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="419b1-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="419b1-125">Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel ne sera pas envoyé à l’utilisateur et vous de aurez à envoyer manuellement les informations de code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="419b1-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="419b1-126">Lorsqu’une réunion commence, tous les utilisateurs qui se retrouvent dans la salle d’accueil la rejoignent automatiquement.</span><span class="sxs-lookup"><span data-stu-id="419b1-126">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="419b1-127">Par exemple, si deux participants essaient de rejoindre une réunion avant qu’elle ait commencé, ils sont placés dans la salle d’attente et écoutent de la musique pendant la mise en attente, et lorsque l’organisateur de la réunion rejoint la réunion à l’aide de son code confidentiel par téléphone, la réunion commence et les participants dans la salle d’attente la rejoignent.</span><span class="sxs-lookup"><span data-stu-id="419b1-127">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="419b1-128">Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="419b1-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="419b1-129">Lorsque vous activez l’audioconférence pour un utilisateur, celui-ci est envoyé par défaut par courrier électronique qui inclut les informations sur la conférence et son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="419b1-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="419b1-130">L’utilisateur doit avoir une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur par courrier électronique à son adresse SMTP principale (alias) définie pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="419b1-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="419b1-131">Lorsque vous définissez l’audioconférence, vous définissez les chiffres requis pour les coden de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="419b1-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="419b1-132">Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5.</span><span class="sxs-lookup"><span data-stu-id="419b1-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="419b1-133">Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s’applique uniquement aux nouveaux code confidentiels générés et ne s’applique pas au paramètre de code confidentiel pour les utilisateurs déjà activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="419b1-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="419b1-134">Consultez [la longueur du code confidentiel pour les réunions d’audioconférence.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="419b1-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="419b1-135">Par défaut, le courrier électronique sera réglé sur l’adresse SMTP principale Microsoft 365 ou Office 365 de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="419b1-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="419b1-136">Vous pouvez envoyer un courrier électronique à une adresse non Microsoft 365 ou non-Office 365 telle qu’une adresse de messagerie Hotmail ou MSN.</span><span class="sxs-lookup"><span data-stu-id="419b1-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="419b1-137">Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="419b1-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="419b1-138">Ceci est utile si les utilisateurs n’ont pas de boîte aux lettres Exchange dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="419b1-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="419b1-139">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="419b1-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="419b1-140">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="419b1-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="419b1-141">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="419b1-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="419b1-142">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="419b1-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="419b1-143">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="419b1-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="419b1-144">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="419b1-144">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="419b1-145">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="419b1-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="419b1-146">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="419b1-146">Related topics</span></span>

[<span data-ttu-id="419b1-147">Réinitialiser l’ID de conférence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="419b1-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
