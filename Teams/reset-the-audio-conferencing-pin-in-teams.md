---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser dans Microsoft Teams. '
ms.openlocfilehash: b88ab6ee2cd498a38026e1fe2bfde04344514901
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014250"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="77b2a-103">Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77b2a-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="77b2a-104">Un code confidentiel est un code constitué de numéros sont créées pour chaque utilisateur de Microsoft Teams qui est activé pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="77b2a-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="77b2a-105">Codes confidentiels de conférence audio sont utilisés par les organisateurs de réunion pour identifier qu’ils sont l’organisateur de la réunion et de démarrer une réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="77b2a-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="77b2a-106">S’ils utilisent l’application Microsoft Teams pour démarrer la réunion, un code confidentiel n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="77b2a-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="77b2a-107">Si les utilisateurs oublient leur code confidentiel et qu’ils ne peut pas trouver dans le courrier électronique qui a été envoyé lorsqu’ils ont été activés pour l’audioconférence, un administrateur peut réinitialiser leur code confidentiel, ou ils peuvent réinitialiser leur propre code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="77b2a-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="77b2a-108">Réunions peuvent être démarrées lorsqu’un utilisateur authentifié se joint à l’aide de l’application Microsoft Teams ou lorsque l’organisateur de jointures avec son code confidentiel sur le téléphone.</span><span class="sxs-lookup"><span data-stu-id="77b2a-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="77b2a-109">Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence.</span><span class="sxs-lookup"><span data-stu-id="77b2a-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="77b2a-110">Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="77b2a-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="77b2a-111">Réinitialiser le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="77b2a-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="77b2a-112">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="77b2a-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="77b2a-113">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="77b2a-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="77b2a-114">Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="77b2a-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="77b2a-115">Laisser un utilisateur réinitialiser son propre code confidentiel</span><span class="sxs-lookup"><span data-stu-id="77b2a-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="77b2a-116">L’utilisateur doit accéder à [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span><span class="sxs-lookup"><span data-stu-id="77b2a-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="77b2a-117">Cliquez sur **Réinitialiser le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="77b2a-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="77b2a-118">Que devez-vous savoir d'autre sur les codes confidentiels ?</span><span class="sxs-lookup"><span data-stu-id="77b2a-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="77b2a-119">Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="77b2a-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="77b2a-120">Une fois que le code confidentiel est réinitialisé par un administrateur, le code confidentiel est répertorié comme \*\*\*.</span><span class="sxs-lookup"><span data-stu-id="77b2a-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="77b2a-121">Envoyer automatiquement des messages électroniques aux utilisateurs est activée par défaut, et les utilisateurs reçoivent un message électronique avec leur code confidentiel lorsqu’elles sont activées pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="77b2a-121">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="77b2a-122">Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé à un utilisateur et vous devez envoyer manuellement les informations de code confidentiel à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77b2a-122">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="77b2a-p105">Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.</span><span class="sxs-lookup"><span data-stu-id="77b2a-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="77b2a-125">Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.</span><span class="sxs-lookup"><span data-stu-id="77b2a-125">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="77b2a-126">Lorsque vous activez un utilisateur pour l’audioconférence, par défaut, ils sont envoyés les messages électroniques qui incluent des informations de conférence et de leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="77b2a-126">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="77b2a-127">L’utilisateur doit avoir une boîte aux lettres Office 365, étant donné que lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l’utilisateur dans le message électronique à leur adresse SMTP principale (alias) est définie pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77b2a-127">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="77b2a-128">Lorsque vous configurez les services d’audioconférence, vous définissez les chiffres qui sont requis pour les codes confidentiels dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="77b2a-128">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="77b2a-129">Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5.</span><span class="sxs-lookup"><span data-stu-id="77b2a-129">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="77b2a-130">Si vous modifiez le paramètre de longueur de code confidentiel, le paramètre est appliqué uniquement sur les codes confidentiels nouvellement créés et n’est pas appliqué au paramètre code confidentiel pour les utilisateurs existants qui sont activées pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="77b2a-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="77b2a-131">Voir [définir la longueur de l’axe des réunions de conférence Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="77b2a-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="77b2a-132">Le courrier électronique par défaut est fixé à l’adresse SMTP principale d’Office 365 de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77b2a-132">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="77b2a-133">Vous pouvez envoyer un message électronique à une adresse non Office 365 tels que Hotmail ou MSN.</span><span class="sxs-lookup"><span data-stu-id="77b2a-133">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="77b2a-134">Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77b2a-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="77b2a-135">Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="77b2a-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="77b2a-136">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="77b2a-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="77b2a-p109">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="77b2a-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77b2a-140">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="77b2a-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="77b2a-141">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77b2a-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="77b2a-142">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="77b2a-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77b2a-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="77b2a-143">Related topics</span></span>

[<span data-ttu-id="77b2a-144">Réinitialiser l'ID de conférence d'un utilisateur</span><span class="sxs-lookup"><span data-stu-id="77b2a-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
