---
title: Définir la longueur du code confidentiel pour les réunions d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
- seo-marvel-mar2020
description: Découvrez les paramètres de longueur et les exigences d’un code confidentiel et apprenez à définir la durée des réunions dans Microsoft Teams.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691100"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="03034-103">Définir la longueur du code confidentiel pour les réunions d'audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03034-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="03034-104">Lorsque vous configurez l’audioconférence pour Microsoft Teams, vous obtenez un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="03034-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="03034-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="03034-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="03034-106">Le numéro de téléphone que vous définissez sera inclus dans les invitations à participer à la réunion de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03034-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="03034-107">Le pont d’audioconférence répond à l’appel des personnes qui composent un numéro pour accéder à une réunion en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="03034-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="03034-108">Il répond à l’appelant avec des invites vocales d’un standard automatique de conférence puis, en fonction de vos paramètres, il peut lire des notifications et demander aux appelants d’enregistrer leur nom.</span><span class="sxs-lookup"><span data-stu-id="03034-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="03034-109">Les **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et l’expérience d’accès aux réunions, et de définir la longueur des codes confidentiels utilisés par les organisateurs de réunions.</span><span class="sxs-lookup"><span data-stu-id="03034-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="03034-110">Les organisateurs de réunions utilisent des codes confidentiels s'ils ne peuvent pas rejoindre la réunion en utilisant l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03034-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="03034-111">Définir la longueur du code confidentiel</span><span class="sxs-lookup"><span data-stu-id="03034-111">Setting the PIN length</span></span>

<span data-ttu-id="03034-112">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="03034-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="03034-113">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="03034-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="03034-114">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="03034-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="03034-115">Dans le volet **paramètres du pont** , sous longueur du **code confidentiel**, sélectionnez le nombre de chiffres que vous voulez utiliser pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="03034-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="03034-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="03034-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="03034-p103">Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="03034-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="03034-121">Vous voulez en savoir plus sur les paramètres de code confidentiel ?</span><span class="sxs-lookup"><span data-stu-id="03034-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="03034-122">Les broches peuvent comporter de 4 à 12 chiffres ; la valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="03034-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="03034-123">Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="03034-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="03034-124">Les lettres et les caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="03034-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="03034-125">Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur de Microsoft teams n’a pas encore commencé la réunion.</span><span class="sxs-lookup"><span data-stu-id="03034-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="03034-126">Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="03034-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="03034-p106">Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique.</span><span class="sxs-lookup"><span data-stu-id="03034-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="03034-129">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="03034-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="03034-130">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="03034-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="03034-131">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="03034-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="03034-132">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="03034-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="03034-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="03034-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="03034-134">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03034-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="03034-135">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="03034-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="03034-136">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="03034-136">Related topics</span></span>

[<span data-ttu-id="03034-137">Essayez ou achetez une audioconférence dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="03034-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
