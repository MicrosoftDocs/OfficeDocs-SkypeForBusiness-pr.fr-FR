---
title: Prise en charge de l’utilisation de la fonctionnalité SEFAUtil dans PowerShell dans Skype entreprise Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé: Découvrez comment utiliser PowerShell pour obtenir le fonctionnement de SEFAUtil dans Skype entreprise Server 2019 après l’installation de la mise à jour cumulative 1.'
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821323"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="6fb55-103">Utiliser la fonctionnalité SEFAUtil via PowerShell dans Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="6fb55-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="6fb55-104">SEFAUtil (l’activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux techniciens du support technique de Skype entreprise de configurer la sonnerie de délégué, le transfert d’appel et les paramètres de cueillette de groupe pour le compte d’un utilisateur de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6fb55-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="6fb55-105">L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="6fb55-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="6fb55-106">Après l’installation de cette mise à jour, les fonctionnalités suivantes qui peuvent être gérées uniquement via SEFAUtil peuvent également être gérées via PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6fb55-106">After you install this update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="6fb55-107">Paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="6fb55-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="6fb55-108">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="6fb55-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="6fb55-109">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="6fb55-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="6fb55-110">Paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="6fb55-110">Call forwarding settings</span></span>

<span data-ttu-id="6fb55-111">Les administrateurs peuvent modifier les paramètres de transfert d’appel à l’aide de l’applet de commande suivante dans PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6fb55-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="6fb55-112">Cette cmdlet renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même écran sur l’écran.</span><span class="sxs-lookup"><span data-stu-id="6fb55-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="6fb55-113">Cette applet de demande modifie les paramètres de transfert d’appel de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="6fb55-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="6fb55-114">Ce cmdlet renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même écran, en cas de succès.</span><span class="sxs-lookup"><span data-stu-id="6fb55-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="6fb55-115">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6fb55-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="6fb55-116">Cette applet de demande désactive les paramètres de transfert d’appel de l’utilisateur (nous affichons deux exemples de paramètres différents ici).</span><span class="sxs-lookup"><span data-stu-id="6fb55-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="6fb55-117">Cette applet de demande modifie les paramètres de transfert d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6fb55-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="6fb55-118">Cette applet de cmdlet modifie les paramètres de SimulRing (de nouveau, avec deux exemples de paramètres: un pour sans réponse à la boîte vocale et le second en absence de réponse à d’autres).</span><span class="sxs-lookup"><span data-stu-id="6fb55-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="6fb55-119">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="6fb55-119">Delegation settings</span></span>

<span data-ttu-id="6fb55-120">Les administrateurs peuvent modifier les paramètres de délégation en utilisant l’applet de commande suivante dans PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6fb55-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="6fb55-121">Cette cmdlet renvoie un objet de liste de délégués et affiche la liste de délégués de l’utilisateur spécifié, en cas de succès.</span><span class="sxs-lookup"><span data-stu-id="6fb55-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="6fb55-122">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6fb55-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="6fb55-123">Cette applet de demande modifie les paramètres de délégation de l’utilisateur spécifié, renvoie un objet de liste délégués et affiche la liste des délégués, en cas de succès.</span><span class="sxs-lookup"><span data-stu-id="6fb55-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="6fb55-124">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6fb55-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="6fb55-125">Cette applet de cmdlet ajoute ou supprime un délégué.</span><span class="sxs-lookup"><span data-stu-id="6fb55-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="6fb55-126">Cette applet de cmdlet définit une liste de délégués pour des délégués spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6fb55-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="6fb55-127">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="6fb55-127">Team members and related settings</span></span>

<span data-ttu-id="6fb55-128">Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’applet de commande suivante dans PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6fb55-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="6fb55-129">Cette cmdlet renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de succès.</span><span class="sxs-lookup"><span data-stu-id="6fb55-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="6fb55-130">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6fb55-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="6fb55-131">Cette applet de demande modifie la liste des membres de l’équipe spécifiée, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de succès.</span><span class="sxs-lookup"><span data-stu-id="6fb55-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="6fb55-132">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6fb55-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="6fb55-133">Cette applet de cmdlet ajoute ou supprime des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="6fb55-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="6fb55-134">Cette applet de cmdlet définit une liste d’équipes pour des membres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6fb55-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="6fb55-135">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="6fb55-135">More information</span></span>

<span data-ttu-id="6fb55-136">Pour les déploiements sur site, les applets de commande introduites dans cette fonctionnalité ne peuvent être exécutées que par les membres des groupes suivants, selon le niveau d’accès indiqué ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="6fb55-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="6fb55-137">CsAdministrator – Get et Set pour toutes les applets de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6fb55-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="6fb55-138">CsVoiceAdministrator-Get et Set pour toutes les applets de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6fb55-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="6fb55-139">CsHelpDesk-obtenir toutes les applets de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6fb55-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="6fb55-140">Pour plus d’informations sur ces rôles d’administrateur, reportez-vous à la rubrique [création d’administrateurs du panneau de configuration Skype entreprise Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="6fb55-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="6fb55-141">L’administrateur peut accéder à ces applets de commande en se connectant directement ou à distance à un ordinateur serveur.</span><span class="sxs-lookup"><span data-stu-id="6fb55-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="6fb55-142">Pour un déploiement hybride, les administrateurs Skype entreprise doivent pouvoir appeler Get et Set pour toutes les applets de méthode.</span><span class="sxs-lookup"><span data-stu-id="6fb55-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="6fb55-143">Pour plus d’informations sur la liste complète des rôles, voir [à propos des rôles d’administrateur Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="6fb55-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="6fb55-144">La découverte automatique du serveur doit être activée.</span><span class="sxs-lookup"><span data-stu-id="6fb55-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="6fb55-145">Aucun besoin de licence supplémentaire n’est introduit pour l’utilisation des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6fb55-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
