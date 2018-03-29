---
title: Parcage d’appel
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Lorsqu’un appel est stocké, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer une table avec les plages de numéros d’extension que vous réservez pour les appels en stationnement. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté). Chaque pool qui exécute l’application d’appel Park peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: 710d923ae9c1e44320438334ad42a89d9d14062f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-park"></a><span data-ttu-id="746ab-106">parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="746ab-106">Call Park</span></span>
 
<span data-ttu-id="746ab-107">Lorsqu’un appel est stocké, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer une table avec les plages de numéros d’extension que vous réservez pour les appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="746ab-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="746ab-108">Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté).</span><span class="sxs-lookup"><span data-stu-id="746ab-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="746ab-109">Chaque pool qui exécute l’application d’appel Park peut avoir une ou plusieurs plages d’extensions.</span><span class="sxs-lookup"><span data-stu-id="746ab-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="746ab-110">Ces plages doivent être globalement uniques dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="746ab-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="746ab-111">Le ** appel Park ** page affiche une liste de toutes les plages numéros Park d’appel qui sont définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="746ab-111">The ** Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="746ab-112">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="746ab-112">Tasks you can perform</span></span>

<span data-ttu-id="746ab-113">Dans la page **Parcage d’appel**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="746ab-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="746ab-114">Création d’une plage de numéros</span><span class="sxs-lookup"><span data-stu-id="746ab-114">Create a new number range</span></span>
    
- <span data-ttu-id="746ab-115">Modification d’une plage de numéros existante</span><span class="sxs-lookup"><span data-stu-id="746ab-115">Change an existing number range</span></span>
    
- <span data-ttu-id="746ab-116">Suppression d’une plage de numéros</span><span class="sxs-lookup"><span data-stu-id="746ab-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="746ab-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="746ab-117">UI Reference</span></span>

<span data-ttu-id="746ab-118">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="746ab-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="746ab-119">**Nouveau** Démarre une nouvelle plage de numéros appel Park.</span><span class="sxs-lookup"><span data-stu-id="746ab-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="746ab-120">**Modifier** Ouvre la plage de numéros sélectionnée pour modification, sélectionne toutes les plages de numéros de la liste ou supprime la plage de numéros sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="746ab-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="746ab-121">**Actualiser** Actualise la liste des plages de numéros.</span><span class="sxs-lookup"><span data-stu-id="746ab-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="746ab-122">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="746ab-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="746ab-123">**Nom** Le nom unique qui identifie la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="746ab-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="746ab-124">**Plage de début** Le numéro de début de la plage.</span><span class="sxs-lookup"><span data-stu-id="746ab-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="746ab-125">**Plage de fin** Le numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="746ab-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="746ab-126">**Destination** Le domaine complet (FQDN) de nom ou ID du service d’Application qui héberge l’application d’appel Park pour la plage de numéros de service.</span><span class="sxs-lookup"><span data-stu-id="746ab-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="746ab-127">Pour plus d’informations sur les fonctionnalités d’appel Park de, voir [planification de parc d’appel dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="746ab-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="746ab-128">Pour plus d’informations sur l’utilisation des plages de numéros d’appel Park, consultez [Configurer les Extensions numéro de téléphone pour les appels de stationnement](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="746ab-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

