---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Les administrateurs peuvent contrôler si les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions.
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837264"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="a45fd-103">Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques</span><span class="sxs-lookup"><span data-stu-id="a45fd-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="a45fd-104">Si votre organisation possède des numéros gratuits dans son pont d’audioconférence Microsoft, vous pouvez autoriser ou interdire leur utilisation dans les réunions d’organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a45fd-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="a45fd-105">Par défaut, tous les utilisateurs de votre organisation peuvent utiliser des numéros gratuits, ce qui signifie que si ces numéros sont disponibles, ils peuvent les utiliser pour participer à leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="a45fd-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="a45fd-106">Si vous souhaitez que certains utilisateurs de votre organisation ne puissent pas utiliser les numéros gratuits, vous pouvez leur interdire d’utiliser ces numéros dans leurs réunions via une commande d’activation des numéros gratuits.</span><span class="sxs-lookup"><span data-stu-id="a45fd-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="a45fd-107">Si les numéros gratuits sont désactivés pour un organisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="a45fd-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="a45fd-108">Un numéro gratuit ne sera plus inclus dans ses invitations à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="a45fd-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="a45fd-109">Les numéros gratuits ne seront plus répertoriés sur la page « Rechercher un numéro local » qui est référencée dans ses invitations à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="a45fd-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="a45fd-110">Les utilisateurs ne pourront plus participer à la réunion de cet organisateur spécifique s’ils composent un numéro gratuit de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="a45fd-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="a45fd-111">Toutes les réunions de l’organisateur seront replanifiées automatiquement et le numéro gratuit lui sera retiré.</span><span class="sxs-lookup"><span data-stu-id="a45fd-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="a45fd-112">Tous les courriers électroniques d’invitation de cet organisateur seront renvoyés à tous les participants à ces réunions.</span><span class="sxs-lookup"><span data-stu-id="a45fd-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="a45fd-113">Les utilisateurs peuvent continuer à participer aux réunions de l’organisateur en utilisant des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="a45fd-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="a45fd-114">Désactiver les numéros gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="a45fd-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="a45fd-115">Dans le **Centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="a45fd-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="a45fd-116">Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="a45fd-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a45fd-117">En regard de l’option **Audioconférence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a45fd-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="a45fd-118">Définissez **inclure les numéros sans frais dans les demandes de réunion de cet utilisateur** **.**</span><span class="sxs-lookup"><span data-stu-id="a45fd-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="a45fd-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a45fd-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="a45fd-120">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a45fd-120">**Using PowerShell**</span></span>  

<span data-ttu-id="a45fd-121">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="a45fd-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
