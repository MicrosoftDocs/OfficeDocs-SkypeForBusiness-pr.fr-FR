---
title: Démarrer une conférence Audio par téléphone sans code confidentiel dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment activer ou désactiver les appelants anonymes de rejoindre une réunion à partir du centre d’administration équipes. '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861042"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="4c687-103">Démarrer une conférence Audio par téléphone sans code confidentiel dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c687-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="4c687-104">Il peut être frustrant pour les utilisateurs qui se connectent à une réunion à être conservés dans la salle d’attente de la réunion à l’écoute de la musique, car l’organisateur de la réunion Teams Microsoft n’a pas démarré la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c687-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="4c687-105">Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est requis pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="4c687-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="4c687-106">Vous pouvez configurer il afin que tout le monde peut se connecter à une réunion et ne pas être invité à entrer un code confidentiel démarrer la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c687-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="4c687-107">Vous pouvez utiliser le centre d’administration pour activer ou désactiver ce paramètre pour un utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="4c687-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="4c687-108">Un code confidentiel n’est pas requis pour l’organisateur de la réunion si une personne a démarré la réunion à partir de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c687-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="4c687-109">Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone.</span><span class="sxs-lookup"><span data-stu-id="4c687-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="4c687-110">Le code confidentiel pour les réunions est envoyé à l’utilisateur audio lorsqu’ils sont affectés à la licence de **Services d’audioconférence** et sont activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="4c687-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4c687-111">Voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) et [messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4c687-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="4c687-112">Autorisation ou refus des appelants anonymes à participer à une réunion</span><span class="sxs-lookup"><span data-stu-id="4c687-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="4c687-113">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="4c687-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4c687-114">Dans la navigation de gauche, cliquez sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4c687-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="4c687-115">Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** dans la partie supérieure de la page.</span><span class="sxs-lookup"><span data-stu-id="4c687-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="4c687-116">En regard de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4c687-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="4c687-117">Dans le volet de **Conférence Audio** , activer ou désactiver **les appelants non authentifiés peuvent être la première personne à une réunion**.</span><span class="sxs-lookup"><span data-stu-id="4c687-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="4c687-118">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4c687-118">Click **Save**.</span></span> 

<span data-ttu-id="4c687-119">**Utilisation de Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="4c687-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="4c687-120">Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="4c687-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="4c687-121">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4c687-121">What else should you know?</span></span>

- <span data-ttu-id="4c687-122">Si vous souhaitez réinitialiser le code confidentiel, consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4c687-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="4c687-123">Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est activé :</span><span class="sxs-lookup"><span data-stu-id="4c687-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="4c687-124">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : un appelant est invité s’il est l’organisateur ; Si il indique Oui, il vous demandé pour son code confidentiel et après des entrées le code confidentiel, il démarre la réunion et l’utilisateur sera participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c687-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="4c687-125">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si il est l’organisateur et il serez jamais pour le code confidentiel ; la réunion est déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="4c687-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="4c687-126">Si l’accès anonyme, ou ne nécessitant ne pas d’un code confidentiel démarrer une réunion, est désactivée :</span><span class="sxs-lookup"><span data-stu-id="4c687-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="4c687-127">Si la réunion n’a pas démarré (il n’existe pas dans la réunion encore) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="4c687-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="4c687-128">Étant donné que le paramètre de l’organisateur est défini sur désactivé, la réunion démarre et les appelants anonymes participerez à la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c687-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="4c687-129">Si la réunion déjà démarré (une autre personne est déjà dans la réunion) : l’appelant ne vous demandera si elle est l’organisateur et elle demandera jamais pour le code confidentiel, la réunion est déjà démarrée, et l’appelant joint.</span><span class="sxs-lookup"><span data-stu-id="4c687-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4c687-130">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="4c687-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4c687-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c687-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4c687-134">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c687-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4c687-135">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="4c687-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4c687-136">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="4c687-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4c687-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4c687-137">Related topics</span></span>

[<span data-ttu-id="4c687-138">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="4c687-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
