---
title: Workflow Response Groups
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Les groupes Response Group sont constitués de groupes d’agents, de files d’attente et de flux de travail. Les flux de travail Response Group définissent les actions qui sont prises lorsque l’application Response Group reçoit un appel téléphonique.
ms.openlocfilehash: 7f35fc32670e6374be69430a72c506a0bf9fae5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829284"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="6b022-104">Flux de travail des services Response Groups</span><span class="sxs-lookup"><span data-stu-id="6b022-104">Response Groups Workflow</span></span>

<span data-ttu-id="6b022-105">Les groupes Response Group sont constitués de groupes d’agents, de files d’attente et de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="6b022-106">Les flux de travail Response Group définissent les actions qui sont prises lorsque l’application Response Group reçoit un appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="6b022-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="6b022-107">La page **Flux de** travail Response Groups affiche la liste de tous les flux de travail Response Group définis pour votre  -   organisation.</span><span class="sxs-lookup"><span data-stu-id="6b022-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6b022-108">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="6b022-108">Tasks you can perform</span></span>

<span data-ttu-id="6b022-109">Vous pouvez effectuer les tâches suivantes à partir de la page flux de travail **Response Groups**  -   :</span><span class="sxs-lookup"><span data-stu-id="6b022-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="6b022-110">Créer ou modifier un flux de travail de groupe de recherche</span><span class="sxs-lookup"><span data-stu-id="6b022-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="6b022-111">Créer ou modifier un flux de travail interactif</span><span class="sxs-lookup"><span data-stu-id="6b022-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6b022-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b022-112">UI Reference</span></span>

<span data-ttu-id="6b022-113">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="6b022-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="6b022-114">**Créer ou modifier un flux de travail** Ouvre l’outil de configuration Response Group pour créer ou modifier un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="6b022-115">**Actualiser** Actualise la liste des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="6b022-116">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="6b022-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6b022-117">**Nom** Nom unique attribué au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="6b022-118">**Service** Service **ApplicationServer** qui héberge le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="6b022-119">**Adresse SIP** Adresse SIP du groupe qui répondra aux appels au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6b022-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="6b022-120">**Téléphone** Numéro de téléphone appelé pour joindre ce groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="6b022-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="6b022-121">**Langue** Langue utilisée pour la reconnaissance vocale et la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="6b022-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="6b022-122">**Réponse vocale vocale (IVR)** Indique si le flux de travail est un groupement de recherche ou un flux de travail interactif.</span><span class="sxs-lookup"><span data-stu-id="6b022-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="6b022-123">**Activé** Indique si le flux de travail est activé pour recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="6b022-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="6b022-124">Pour plus d’informations sur les fonctionnalités de Response Group, voir [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="6b022-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="6b022-125">Pour plus d’informations sur l’working with Response Group workflows, voir [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="6b022-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


