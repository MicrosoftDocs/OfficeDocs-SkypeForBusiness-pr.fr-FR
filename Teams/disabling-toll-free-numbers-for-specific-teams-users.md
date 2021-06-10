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
- seo-marvel-mar2020
description: Découvrez comment contrôler la façon dont les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions pont de conférence audio.
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096344"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="96a94-103">Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques</span><span class="sxs-lookup"><span data-stu-id="96a94-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="96a94-104">Si votre organisation a des numéros gratuits dans son pont de conférence audio Microsoft, vous pouvez autoriser ou empêcher leur utilisation pendant les réunions d’organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="96a94-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="96a94-105">Par défaut, tous les utilisateurs de votre organisation sont activés pour utiliser des numéros gratuits, ce qui signifie que ces numéros, s’ils sont disponibles, peuvent être utilisés par les participants pour rejoindre leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="96a94-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="96a94-106">Si ce n’est pas le comportement souhaité pour certains utilisateurs de votre organisation, vous pouvez restreindre l’utilisation de ces numéros par des utilisateurs spécifiques dans leurs réunions via un contrôle d' enablement de numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="96a94-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="96a94-107">Lorsque les numéros gratuits sont désactivés pour un organisateur donné :</span><span class="sxs-lookup"><span data-stu-id="96a94-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="96a94-108">Un numéro gratuit ne sera plus inclus dans ses invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="96a94-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="96a94-109">Les numéros gratuits ne seront plus répertoriés dans la page « Rechercher un numéro local » référencé dans ses invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="96a94-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="96a94-110">Les participants ne pourront pas participer à la réunion de l’organisateur donné s’ils composent un numéro gratuit de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="96a94-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="96a94-111">Toutes les réunions de l’organisateur sont automatiquement reprogrammées et le numéro gratuit leur est supprimé.</span><span class="sxs-lookup"><span data-stu-id="96a94-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="96a94-112">Cela renvoye toutes les invitations par courrier électronique de l’organisateur à tous les participants de ces réunions.</span><span class="sxs-lookup"><span data-stu-id="96a94-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="96a94-113">Les participants peuvent continuer à rejoindre les réunions de l’organisateur à l’aide de numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="96a94-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="96a94-114">Désactiver les numéros gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="96a94-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="96a94-115">À partir du **Microsoft Teams d’administration :**</span><span class="sxs-lookup"><span data-stu-id="96a94-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="96a94-116">Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="96a94-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="96a94-117">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="96a94-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="96a94-118">Set **Include toll-free numbers in meeting requests from this user** to **Off.**</span><span class="sxs-lookup"><span data-stu-id="96a94-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="96a94-119">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="96a94-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="96a94-120">**Utiliser PowerShell**</span><span class="sxs-lookup"><span data-stu-id="96a94-120">**Using PowerShell**</span></span>  

<span data-ttu-id="96a94-121">Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="96a94-121">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>