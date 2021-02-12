---
title: Désactivation des numéros gratuits pour des utilisateurs spécifiques de Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler la façon dont les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695679"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="4d89e-103">Désactivation des numéros gratuits pour des utilisateurs spécifiques de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4d89e-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="4d89e-104">Pour plus d’informations sur la désactivation des numéros gratuits pour les utilisateurs de Teams, voir Désactivation des numéros gratuits [pour certains utilisateurs de Teams.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)</span><span class="sxs-lookup"><span data-stu-id="4d89e-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="4d89e-105">Si votre organisation dispose de numéros gratuits dans son pont de conférence audio Microsoft, vous pouvez autoriser ou empêcher leur utilisation pendant les réunions d’organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4d89e-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="4d89e-106">Par défaut, tous les utilisateurs de votre organisation sont activés pour utiliser des numéros gratuits, ce qui signifie que ces numéros, s’ils sont disponibles, peuvent être utilisés par les participants pour rejoindre leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="4d89e-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="4d89e-107">Si ce n’est pas le comportement souhaité pour certains utilisateurs dans votre organisation, vous pouvez restreindre l’utilisation de ces numéros par des utilisateurs spécifiques dans leurs réunions via un contrôle d' enablement de numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="4d89e-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="4d89e-108">Lorsque les numéros gratuits sont désactivés pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="4d89e-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="4d89e-109">Un numéro gratuit ne sera plus inclus dans ses invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="4d89e-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4d89e-110">Les numéros gratuits ne seront plus répertoriés dans la page « Rechercher un numéro local » référencé dans ses invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="4d89e-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4d89e-111">Les participants ne pourront pas participer à la réunion de l’organisateur donné s’ils composent un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4d89e-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="4d89e-112">Toutes les réunions de l’organisateur sont automatiquement reprogrammées et le numéro gratuit leur est supprimé.</span><span class="sxs-lookup"><span data-stu-id="4d89e-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="4d89e-113">Cela renvoye toutes les invitations par courrier électronique de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="4d89e-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="4d89e-114">Les participants peuvent continuer à rejoindre les réunions de l’organisateur à l’aide de numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="4d89e-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="4d89e-115">Désactiver les numéros gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="4d89e-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="4d89e-116">À partir du **Centre d’administration Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="4d89e-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="4d89e-117">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d89e-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4d89e-118">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4d89e-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="4d89e-119">Set **Include toll-free numbers in meeting requests from this user** to **Off.**</span><span class="sxs-lookup"><span data-stu-id="4d89e-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="4d89e-120">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="4d89e-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="4d89e-121">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d89e-121">**Using PowerShell**</span></span>  

<span data-ttu-id="4d89e-122">Vous pouvez utiliser le paramètre AllowTollFreeDialIn de la cmdlet Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle.</span><span class="sxs-lookup"><span data-stu-id="4d89e-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="4d89e-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4d89e-123">For example:</span></span> 

- <span data-ttu-id="4d89e-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="4d89e-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
