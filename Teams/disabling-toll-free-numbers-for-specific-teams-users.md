---
title: Désactivation des numéros de téléphone gratuits pour les utilisateurs des équipes spécifiques
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler les organisateurs utilisation numéros gratuits pour leurs réunions.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887379"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="59742-103">Désactivation des numéros de téléphone gratuits pour les utilisateurs des équipes spécifiques</span><span class="sxs-lookup"><span data-stu-id="59742-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="59742-104">Si votre organisation dispose de numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="59742-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="59742-105">Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="59742-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="59742-106">Si ce n’est pas le comportement souhaité pour certains utilisateurs au sein de votre organisation, vous pouvez empêcher des utilisateurs spécifiques d’à l’aide de ces numéros dans leurs réunions via un contrôle activation du numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="59742-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="59742-107">Lorsque les numéros gratuits sont désactivés pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="59742-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="59742-108">Un numéro gratuit sera n’est plus inclus dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="59742-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="59742-109">Numéros gratuits ne sont plus apparaît sur la page « Rechercher un numéro local » qui est référencée dans son ou sa réunion invite.</span><span class="sxs-lookup"><span data-stu-id="59742-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="59742-110">Les participants ne puissent pas participer à la réunion de l’organisateur donné si elles composer un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="59742-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="59742-111">Replanifier automatiquement toutes les réunions de l’organisateur et le numéro gratuit sera supprimé à partir de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="59742-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="59742-112">Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="59742-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="59742-113">Les participants peuvent poursuivre la participation à des réunions de l’organisateur à l’aide des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="59742-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="59742-114">Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="59742-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="59742-115">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="59742-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="59742-116">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="59742-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="59742-117">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="59742-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="59742-118">Désactivez l’option **inclure les numéros gratuits dans les demandes de réunion à partir de cet utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="59742-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="59742-119">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="59742-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="59742-120">**À l’aide de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="59742-120">**Using PowerShell**</span></span>  

<span data-ttu-id="59742-121">Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="59742-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
