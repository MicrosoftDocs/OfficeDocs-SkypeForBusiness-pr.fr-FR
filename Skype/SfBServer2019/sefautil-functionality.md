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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez comment utiliser PowerShell pour obtenir la fonctionnalité SEFAUtil dans Skype entreprise Server 2019 après avoir installé la mise à jour cumulative 1.'
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868551"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="1499a-103">Utilisation de la fonctionnalité SEFAUtil via PowerShell dans Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="1499a-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="1499a-104">SEFAUtil (option d’activation secondaire) permet aux administrateurs de Skype entreprise Server et aux agents du support technique de configurer la sonnerie des délégués, le transfert d’appels et les paramètres de prise d’appel de groupe pour le compte d’un utilisateur de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1499a-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="1499a-105">Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="1499a-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="1499a-106">Après avoir installé la mise à jour cumulative de Skype entreprise Server 2019 juillet, les fonctionnalités suivantes, qui peuvent actuellement être gérées uniquement via SEFAUtil, seront également gérables via PowerShell :</span><span class="sxs-lookup"><span data-stu-id="1499a-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="1499a-107">Paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="1499a-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="1499a-108">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="1499a-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="1499a-109">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="1499a-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="1499a-110">Paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="1499a-110">Call forwarding settings</span></span>

<span data-ttu-id="1499a-111">Les administrateurs peuvent modifier les paramètres de transfert d’appel à l’aide de l’applet de commande suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="1499a-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="1499a-112">Cette applet de commande renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même sur l’écran.</span><span class="sxs-lookup"><span data-stu-id="1499a-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="1499a-113">Cette applet de commande modifie les paramètres de transfert d’appel de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="1499a-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="1499a-114">Cette applet de commande renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même sur l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="1499a-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="1499a-115">En cas de défaillance, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1499a-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="1499a-116">Cette applet de commande désactive les paramètres de transfert d’appel de l’utilisateur (nous affichons deux exemples de paramètres différents ici).</span><span class="sxs-lookup"><span data-stu-id="1499a-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="1499a-117">Cette applet de commande modifie les paramètres de transfert d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1499a-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="1499a-118">Cette applet de commande modifie les paramètres sonnerie simultanée (encore une fois, avec deux exemples de paramètres : un pour les messages sans réponse à la messagerie vocale et le second n’a pas répondu à d’autres).</span><span class="sxs-lookup"><span data-stu-id="1499a-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="1499a-119">Paramètres de délégation</span><span class="sxs-lookup"><span data-stu-id="1499a-119">Delegation settings</span></span>

<span data-ttu-id="1499a-120">Les administrateurs peuvent modifier les paramètres de délégation à l’aide de l’applet de commande suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="1499a-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="1499a-121">Cette applet de commande renvoie un objet de liste de délégués et affiche la liste de délégués de l’utilisateur spécifié, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="1499a-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="1499a-122">En cas de défaillance, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1499a-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="1499a-123">Cette applet de commande modifie les paramètres de délégation de l’utilisateur spécifié, renvoie une liste d’objets de délégués et affiche la liste des délégués en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="1499a-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="1499a-124">En cas de défaillance, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1499a-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="1499a-125">Cette applet de commande ajoute ou supprime un délégué.</span><span class="sxs-lookup"><span data-stu-id="1499a-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="1499a-126">Cette applet de commande définit une liste de délégués à des délégués spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1499a-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="1499a-127">Membres de l’équipe et paramètres associés</span><span class="sxs-lookup"><span data-stu-id="1499a-127">Team members and related settings</span></span>

<span data-ttu-id="1499a-128">Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’applet de commande suivante dans PowerShell :</span><span class="sxs-lookup"><span data-stu-id="1499a-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="1499a-129">Cette applet de commande renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="1499a-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="1499a-130">En cas de défaillance, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1499a-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="1499a-131">Cette applet de commande modifie la liste des membres de l’équipe spécifiée, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="1499a-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="1499a-132">En cas de défaillance, un message d’erreur approprié s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1499a-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="1499a-133">Cette applet de commande ajoute ou supprime des membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="1499a-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="1499a-134">Cette applet de commande définit une liste d’équipes sur des membres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1499a-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="1499a-135">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="1499a-135">More information</span></span>

<span data-ttu-id="1499a-136">Pour les déploiements locaux, les applets de commande introduites dans cette fonctionnalité ne peuvent être exécutées que par les membres des groupes suivants, selon le niveau d’accès spécifié ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="1499a-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="1499a-137">CsAdministrator – obtenir et définir pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="1499a-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="1499a-138">CsVoiceAdministrator-Get et Set pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="1499a-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="1499a-139">CsHelpDesk-Get pour toutes les cmdlets</span><span class="sxs-lookup"><span data-stu-id="1499a-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="1499a-140">Pour plus d’informations sur ces rôles d’administrateur, voir [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="1499a-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="1499a-141">L’administrateur peut accéder à ces applets de commande en ouvrant directement ou à distance une session sur un ordinateur serveur.</span><span class="sxs-lookup"><span data-stu-id="1499a-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="1499a-142">Pour un déploiement hybride, les administrateurs Skype entreprise doivent pouvoir appeler Get et Set pour toutes les cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1499a-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="1499a-143">Pour plus d’informations sur la liste complète des rôles, consultez la rubrique [à propos des rôles d’administrateur](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1499a-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="1499a-144">La découverte automatique de serveur doit être activée.</span><span class="sxs-lookup"><span data-stu-id="1499a-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="1499a-145">Aucune autre exigence en matière de licences ne sera introduite pour l’utilisation des applets de commande.</span><span class="sxs-lookup"><span data-stu-id="1499a-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
