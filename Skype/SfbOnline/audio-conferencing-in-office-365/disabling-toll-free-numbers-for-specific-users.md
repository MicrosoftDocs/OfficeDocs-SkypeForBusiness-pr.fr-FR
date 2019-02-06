---
title: Désactivation des numéros de téléphone gratuits pour Skype spécifique pour les utilisateurs professionnels en ligne
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler les organisateurs utilisation numéros gratuits pour leurs réunions.
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753757"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="e1853-103">Désactivation des numéros de téléphone gratuits pour Skype spécifique pour les utilisateurs professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="e1853-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="e1853-104">Pour plus d’informations sur la désactivation numéros sans outil pour les utilisateurs d’équipes, voir [désactivation des numéros gratuits pour les utilisateurs des équipes spécifiques](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="e1853-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="e1853-105">Si votre organisation dispose de numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e1853-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="e1853-106">Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="e1853-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="e1853-107">Si ce n’est pas le comportement souhaité pour certains utilisateurs au sein de votre organisation, vous pouvez empêcher des utilisateurs spécifiques d’à l’aide de ces numéros dans leurs réunions via un contrôle activation du numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="e1853-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="e1853-108">Lorsque les numéros gratuits sont désactivés pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="e1853-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="e1853-109">Un numéro gratuit sera n’est plus inclus dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="e1853-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="e1853-110">Numéros gratuits ne sont plus apparaît sur la page « Rechercher un numéro local » qui est référencée dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="e1853-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="e1853-111">Les participants ne puissent pas participer à la réunion de l’organisateur donné si elles composer un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e1853-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="e1853-112">Replanifier automatiquement toutes les réunions de l’organisateur et le numéro gratuit sera supprimé à partir de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="e1853-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="e1853-113">Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="e1853-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="e1853-114">Les participants peuvent poursuivre la participation à des réunions de l’organisateur à l’aide des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="e1853-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="e1853-115">Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="e1853-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="e1853-116">À partir du **Centre d’administration de Microsoft équipes**:</span><span class="sxs-lookup"><span data-stu-id="e1853-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e1853-117">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="e1853-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e1853-118">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e1853-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="e1853-119">Pour **désactiver**la valeur **inclure les numéros gratuits dans les demandes de cet utilisateur de réunion** .</span><span class="sxs-lookup"><span data-stu-id="e1853-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="e1853-120">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="e1853-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="e1853-121">**À l’aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e1853-121">**Using PowerShell**</span></span>  

<span data-ttu-id="e1853-122">Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle.</span><span class="sxs-lookup"><span data-stu-id="e1853-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="e1853-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e1853-123">For example:</span></span> 

- <span data-ttu-id="e1853-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="e1853-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
