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
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser dans Microsoft Teams. '
ms.openlocfilehash: 6d0d986789fb987494ded16bb8d6f6d7c3bf58a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693829"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="ed92b-103">Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed92b-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="ed92b-104">Un code confidentiel est un code composé de chiffres qui est créé pour chaque utilisateur de Microsoft Teams activé pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="ed92b-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="ed92b-105">Les codes confidentiels d’audioconférence permettent aux organisateurs de réunions de s'identifier en tant que tels et de commencer une réunion téléphonique.</span><span class="sxs-lookup"><span data-stu-id="ed92b-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="ed92b-106">S'ils utilisent l’application Microsoft Teams pour commencer la réunion, un code confidentiel n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ed92b-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="ed92b-107">Si un utilisateur oublie son code confidentiel et qu'il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l'activer pour l’audioconférence, un administrateur peut le réinitialiser ou l’utilisateur peut réinitialiser son propre code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ed92b-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="ed92b-108">Les réunions peuvent commencer lorsqu'un utilisateur authentifié les rejoint en utilisant l’application Microsoft Teams ou lorsque l'organisateur saisit son code confidentiel à l'aide du téléphone pour participer.</span><span class="sxs-lookup"><span data-stu-id="ed92b-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="ed92b-109">Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence.</span><span class="sxs-lookup"><span data-stu-id="ed92b-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="ed92b-110">Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ed92b-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="ed92b-111">Réinitialiser le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed92b-111">Reset a user's PIN</span></span>

<span data-ttu-id="ed92b-112">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="ed92b-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ed92b-113">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ed92b-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ed92b-114">Cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="ed92b-114">Click **Edit**.</span></span>

3. <span data-ttu-id="ed92b-115">Sous **audioconférence**, cliquez sur **Réinitialiser le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="ed92b-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="ed92b-116">Cliquez sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="ed92b-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="ed92b-117">Réinitialisation par un utilisateur de son propre code confidentiel</span><span class="sxs-lookup"><span data-stu-id="ed92b-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="ed92b-118">Demander à l’utilisateur d' [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)accéder à.</span><span class="sxs-lookup"><span data-stu-id="ed92b-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="ed92b-119">Cliquez sur **Réinitialiser le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="ed92b-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="ed92b-120">Que devez-vous savoir d'autre sur les codes confidentiels ?</span><span class="sxs-lookup"><span data-stu-id="ed92b-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="ed92b-121">Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ed92b-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="ed92b-122">Après la réinitialisation de votre code confidentiel par un administrateur, le code confidentiel sera répertorié comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed92b-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="ed92b-123">L’envoi automatique de courriers électroniques à des utilisateurs est activé par défaut, et les utilisateurs reçoivent un message électronique contenant leur code confidentiel lorsqu’ils sont activés pour les conférences audio ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="ed92b-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="ed92b-124">Mais si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel n’est pas envoyé à l’utilisateur et vous devrez lui envoyer manuellement les informations sur le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ed92b-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="ed92b-p105">Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.</span><span class="sxs-lookup"><span data-stu-id="ed92b-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="ed92b-127">Par défaut, les appelants anonymes ne permettent pas de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="ed92b-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="ed92b-128">Lorsque vous activez un utilisateur pour l’audioconférence, il est envoyé par défaut des messages électroniques qui incluent des informations de conférence et leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="ed92b-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="ed92b-129">L’utilisateur doit avoir une boîte aux lettres Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l’utilisateur dans un message électronique à l’adresse SMTP principale (alias) définie pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed92b-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="ed92b-130">Lorsque vous configurez l’audioconférence, vous définissez les chiffres requis pour les broches de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ed92b-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="ed92b-131">Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5.</span><span class="sxs-lookup"><span data-stu-id="ed92b-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="ed92b-132">Si vous modifiez le paramètre de longueur du code confidentiel, ce paramètre n’est appliqué qu’aux codes confidentiels générés et ne s’applique pas au paramètre code confidentiel pour les utilisateurs existants qui sont activés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="ed92b-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="ed92b-133">Reportez-vous [à la section définir la longueur du code confidentiel pour les réunions de conférence audio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed92b-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="ed92b-134">Par défaut, l’adresse de courrier est définie sur 365 l’adresse SMTP principale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed92b-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="ed92b-135">Vous pouvez envoyer un courrier électronique à une adresse 365 autre qu’Office, telle qu’une adresse de messagerie Hotmail ou MSN.</span><span class="sxs-lookup"><span data-stu-id="ed92b-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="ed92b-136">Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed92b-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="ed92b-137">Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed92b-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ed92b-138">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="ed92b-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ed92b-p109">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed92b-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ed92b-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed92b-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ed92b-143">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed92b-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ed92b-144">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ed92b-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed92b-145">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ed92b-145">Related topics</span></span>

[<span data-ttu-id="ed92b-146">Réinitialiser l’ID de conférence d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed92b-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
