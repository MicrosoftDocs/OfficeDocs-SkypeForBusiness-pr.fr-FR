---
title: Workflow Response Groups
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: Groupes de réponses se composent des groupes d’agents, files d’attente et flux de travail. Flux de travail Response Group définissent les actions exécutées lorsque l’application Response Group reçoit un appel téléphonique.
ms.openlocfilehash: fad6e7ac71e36f89df712054d1322f8150bc1083
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899616"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="7dfb6-104">Workflow Response Groups</span><span class="sxs-lookup"><span data-stu-id="7dfb6-104">Response Groups Workflow</span></span>

<span data-ttu-id="7dfb6-105">Groupes de réponses se composent des groupes d’agents, files d’attente et flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="7dfb6-106">Flux de travail Response Group définissent les actions exécutées lorsque l’application Response Group reçoit un appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="7dfb6-107">Les **Groupes de réponses** - page**flux de travail** affiche une liste de tous les workflows du service Response Group qui sont définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7dfb6-108">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="7dfb6-108">Tasks you can perform</span></span>

<span data-ttu-id="7dfb6-109">Vous pouvez effectuer les tâches suivantes dans les **Groupes de réponses** - page**flux de travail** :</span><span class="sxs-lookup"><span data-stu-id="7dfb6-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="7dfb6-110">Créer ou modifier un flux de travail de groupe de recherche</span><span class="sxs-lookup"><span data-stu-id="7dfb6-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="7dfb6-111">Créer ou modifier un workflow interactif</span><span class="sxs-lookup"><span data-stu-id="7dfb6-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7dfb6-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="7dfb6-112">UI Reference</span></span>

<span data-ttu-id="7dfb6-113">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="7dfb6-114">**Créer ou modifier un flux de travail** Ouvre l’outil de Configuration Response Group pour créer ou modifier un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="7dfb6-115">**Actualiser** Actualise la liste des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="7dfb6-116">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7dfb6-117">**Nom** Nom unique affecté au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="7dfb6-118">**Service** Le service **ApplicationServer** qui héberge le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="7dfb6-119">**Adresse SIP** L’adresse SIP du groupe qui répondra aux appels du workflow.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="7dfb6-120">**Téléphone** Numéro de téléphone qui est appelé pour joindre ce groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="7dfb6-121">**Langue** La langue utilisée pour la reconnaissance vocale et.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="7dfb6-122">**Réponse vocale interactive** Indique si le flux de travail est un groupement de postes ou d’un flux de travail interactif.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="7dfb6-123">**Activé** Indique si le workflow est activé pour recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="7dfb6-124">Pour plus d’informations sur les fonctionnalités de Response Group, consultez [planification de l’application Response Group dans Skype pour Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="7dfb6-125">Pour plus d’informations sur l’utilisation des flux de travail Response Group, consultez [Gestion de flux de travail Response Group](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="7dfb6-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


