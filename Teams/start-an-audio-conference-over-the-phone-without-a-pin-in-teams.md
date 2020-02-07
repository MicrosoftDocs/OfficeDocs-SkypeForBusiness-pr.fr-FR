---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Découvrez comment empêcher ou autoriser ou empêcher les appelants anonymes à participer à une réunion depuis le Centre d’administration de Teams. '
ms.openlocfilehash: 87588bc8edfcc4d50b5589339f92f56829ec38ef
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837914"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="6419c-103">Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6419c-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="6419c-104">Il peut être frustrant pour des utilisateurs qui composent le numéro de téléphone d'une réunion d'être placés dans la salle d'attente de la réunion car l'organisateur de la réunion Microsoft Teams ne l’a pas encore commencée.</span><span class="sxs-lookup"><span data-stu-id="6419c-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="6419c-105">Si l'organisateur d’une réunion appelle la réunion, un code confidentiel lui est demandé par défaut pour que la réunion puisse commencer.</span><span class="sxs-lookup"><span data-stu-id="6419c-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="6419c-106">Vous pouvez modifier ce paramètre pour que n'importe qui puisse composer le numéro de téléphone de la réunion et y puisse y participer sans avoir à composer de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="6419c-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="6419c-107">Le Centre d'administration permet d'activer ou de désactiver ce paramètre pour un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="6419c-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="6419c-108">Un code confidentiel n'est pas nécessaire pour l'organisateur de la réunion si quelqu'un a commencé la réunion à partir de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6419c-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="6419c-109">Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="6419c-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="6419c-110">Le code confidentiel des réunions est envoyé aux utilisateurs téléphoniques qui possèdent une licence pour l’**Audioconférence** ou pour lesquels la fonction d’audioconférence est activée.</span><span class="sxs-lookup"><span data-stu-id="6419c-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="6419c-111">Reportez-vous aux sections [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) et [Courriers électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6419c-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="6419c-112">Empêcher ou autoriser les appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="6419c-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="6419c-113">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="6419c-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6419c-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6419c-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="6419c-115">Sélectionnez un utilisateur dans la liste et cliquez sur **Modifier** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="6419c-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="6419c-116">En regard de l’option **Audioconférence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6419c-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="6419c-117">Dans le volet **audioconférence Conferencing** , vous pouvez activer ou désactiver **les appelants**rendez-vous dans une réunion.</span><span class="sxs-lookup"><span data-stu-id="6419c-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="6419c-118">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="6419c-118">Click **Apply**.</span></span> 

<span data-ttu-id="6419c-119">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="6419c-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="6419c-120">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6419c-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="6419c-121">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6419c-121">What else should you know?</span></span>

- <span data-ttu-id="6419c-122">Si vous souhaitez réinitialiser le code confidentiel, reportez-vous à la section [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6419c-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="6419c-123">Si l’accès anonyme ou ne nécessite pas un code confidentiel pour démarrer une réunion, est désactivé :</span><span class="sxs-lookup"><span data-stu-id="6419c-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="6419c-124">Si la réunion n’a pas commencé (personne n’a encore rejoint la réunion) : un appelant sera invité à indiquer s’il est l’organisateur et, s’il répond oui, il sera invité à saisir son code confidentiel. Une fois qu’il aura saisi son code confidentiel, la réunion commencera et l’utilisateur pourra y participer.</span><span class="sxs-lookup"><span data-stu-id="6419c-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="6419c-125">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="6419c-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="6419c-126">Si vous avez accès anonyme ou si vous n’avez pas besoin d’un code confidentiel pour démarrer une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="6419c-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="6419c-127">Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="6419c-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="6419c-128">Étant donné que le paramètre de l'organisateur est défini sur Désactivé, la réunion commence et les appelants anonymes peuvent y participer.</span><span class="sxs-lookup"><span data-stu-id="6419c-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="6419c-129">Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="6419c-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6419c-130">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="6419c-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6419c-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6419c-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6419c-134">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6419c-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6419c-135">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6419c-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6419c-136">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6419c-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6419c-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6419c-137">Related topics</span></span>

[<span data-ttu-id="6419c-138">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="6419c-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
