---
title: Prise en charge de l’utilisation de la fonctionnalité SEFAUtil dans PowerShell dans Skype Entreprise Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez comment utiliser PowerShell pour obtenir la fonctionnalité SEFAUtil dans Skype Entreprise Server 2019 après l’installation de la mise à jour cumulative 1.'
ms.openlocfilehash: d97dd84a3d05cf18752e40dd73a8c5f7e9752d3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120505"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="cca0b-103">Utilisation de la fonctionnalité SEFAUtil via PowerShell dans Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="cca0b-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="cca0b-104">SEFAUtil (Secondary Extension Feature Activation) permet aux administrateurs de Skype Entreprise Server et aux agents du service d’aide de configurer les paramètres de sonnerie de délégué, de transfert d’appel et de prise d’appel de groupe pour le compte d’un utilisateur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cca0b-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="cca0b-105">Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="cca0b-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="cca0b-106">Après avoir installé la mise à jour cumulative de juillet 2019 de Skype Entreprise Server, les fonctionnalités suivantes qui peuvent actuellement être gérées uniquement via SEFAUtil sont également gérables via PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cca0b-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="cca0b-107">Paramètres de forwarding d’appel</span><span class="sxs-lookup"><span data-stu-id="cca0b-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="cca0b-108">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="cca0b-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="cca0b-109">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="cca0b-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="cca0b-110">Paramètres de forwarding d’appel</span><span class="sxs-lookup"><span data-stu-id="cca0b-110">Call forwarding settings</span></span>

<span data-ttu-id="cca0b-111">Les administrateurs peuvent modifier les paramètres de forwarding d’appel à l’aide de l’cmdlet suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cca0b-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="cca0b-112">Cette cmdlet renvoie les paramètres de forwardage d’appel de l’utilisateur spécifié en tant qu’objet et s’affiche de la même façon à l’écran.</span><span class="sxs-lookup"><span data-stu-id="cca0b-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="cca0b-113">Cette cmdlet modifie les paramètres de forwardage d’appel de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="cca0b-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="cca0b-114">Cette cmdlet renvoie les paramètres de forwardage d’appel de l’utilisateur spécifié en tant qu’objet et affiche la même chose à l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="cca0b-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="cca0b-115">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cca0b-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="cca0b-116">Cette cmdlet désactive les paramètres de forwarding d’appel de l’utilisateur (nous vous présentons deux exemples de paramètres différents ici).</span><span class="sxs-lookup"><span data-stu-id="cca0b-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="cca0b-117">Cette cmdlet modifie les paramètres de forwarding d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cca0b-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="cca0b-118">Cette cmdlet modifie les paramètres SimulRing (là encore, avec deux exemples de paramètres, l’un pour les messages vocaux sans réponse et l’autre pour les autres).</span><span class="sxs-lookup"><span data-stu-id="cca0b-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="cca0b-119">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="cca0b-119">Delegation settings</span></span>

<span data-ttu-id="cca0b-120">Les administrateurs peuvent modifier les paramètres de délégation à l’aide de l’cmdlet suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cca0b-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="cca0b-121">Cette cmdlet renvoie un objet de liste de délégués et affiche la liste des délégués de l’utilisateur spécifié, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="cca0b-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="cca0b-122">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cca0b-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="cca0b-123">Cette cmdlet modifie les paramètres de délégation de l’utilisateur spécifié, renvoie un objet de liste de délégués et affiche la liste des délégués, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="cca0b-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="cca0b-124">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cca0b-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="cca0b-125">Cette cmdlet ajoute ou supprime un délégué.</span><span class="sxs-lookup"><span data-stu-id="cca0b-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="cca0b-126">Cette cmdlet définit une liste de délégués pour des délégués spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cca0b-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="cca0b-127">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="cca0b-127">Team members and related settings</span></span>

<span data-ttu-id="cca0b-128">Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’cmdlet suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cca0b-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="cca0b-129">Cette cmdlet renvoie un objet qui contient la liste des membres de l’équipe et l’affiche à l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="cca0b-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="cca0b-130">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cca0b-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="cca0b-131">Cette cmdlet modifie la liste des membres de l’équipe de l’utilisateur spécifié, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="cca0b-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="cca0b-132">En cas d’échec, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cca0b-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="cca0b-133">Cette cmdlet ajoute ou supprime des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="cca0b-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="cca0b-134">Cette cmdlet définit une liste d’équipes pour des membres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cca0b-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="cca0b-135">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="cca0b-135">More information</span></span>

<span data-ttu-id="cca0b-136">Pour les déploiements locaux, les cmdlets introduites dans cette fonctionnalité peuvent uniquement être exécutés par les membres des groupes suivants, selon le niveau d’accès spécifié ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="cca0b-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="cca0b-137">CsAdministrator : obtenir et définir pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="cca0b-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="cca0b-138">CsVoiceAdministrator - Obtenir et définir pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="cca0b-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="cca0b-139">CsHelpDesk - Obtenir pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="cca0b-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="cca0b-140">Pour plus d’informations sur ces rôles d’administrateur, voir [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="cca0b-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="cca0b-141">L’administrateur peut accéder à ces cmdlets en se connectant directement ou à distance à un ordinateur serveur.</span><span class="sxs-lookup"><span data-stu-id="cca0b-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="cca0b-142">Pour un déploiement hybride, les administrateurs Skype Entreprise doivent être en mesure d’appeler Get et Set pour toutes les cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cca0b-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="cca0b-143">Pour plus d’informations sur la liste complète des rôles, voir [à propos des rôles d’administrateur.](/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="cca0b-143">For more information about the full list of roles, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="cca0b-144">La découverte automatique du serveur doit être activée.</span><span class="sxs-lookup"><span data-stu-id="cca0b-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="cca0b-145">Aucune exigence de licence supplémentaire n’est introduite pour l’utilisation des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cca0b-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>