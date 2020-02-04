---
title: Workflow Response Groups
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Les groupes de réponse sont des groupes d’agents, des files d’attente et des flux de travail. Les flux de travail de groupe de réponse définissent les actions effectuées lorsque l’application de Response Group reçoit un appel téléphonique.
ms.openlocfilehash: 2d32ed7ca2cc793603b0d426bc8b223075d086a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699749"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="44002-104">Workflow Response Groups</span><span class="sxs-lookup"><span data-stu-id="44002-104">Response Groups Workflow</span></span>

<span data-ttu-id="44002-105">Les groupes de réponse sont des groupes d’agents, des files d’attente et des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="44002-106">Les flux de travail de groupe de réponse définissent les actions effectuées lorsque l’application de Response Group reçoit un appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="44002-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="44002-107">La page de**flux de travail** **groupes** - de réponse affiche la liste de tous les flux de travail de groupe de réponse définis pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="44002-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="44002-108">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="44002-108">Tasks you can perform</span></span>

<span data-ttu-id="44002-109">Vous pouvez effectuer les tâches suivantes à partir de la page**flux de travail** **groupes** - de réponse :</span><span class="sxs-lookup"><span data-stu-id="44002-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="44002-110">Création ou modification d’un flux de travail de groupe de recherche</span><span class="sxs-lookup"><span data-stu-id="44002-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="44002-111">Création ou modification d’un flux de travail interactif</span><span class="sxs-lookup"><span data-stu-id="44002-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="44002-112">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="44002-112">UI Reference</span></span>

<span data-ttu-id="44002-113">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="44002-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="44002-114">**Création ou modification d’un flux de travail** Ouvre l’outil de configuration de Response Group pour créer ou modifier un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="44002-115">**Actualiser** Actualise la liste des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="44002-116">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="44002-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="44002-117">**Nom** Nom unique affecté au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="44002-118">**Service (service** ) Service **ApplicationServer** qui héberge le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="44002-119">**Adresse SIP** Adresse SIP du groupe qui répondra aux appels au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="44002-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="44002-120">**Téléphone** Le numéro de téléphone qui est appelé pour joindre ce groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="44002-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="44002-121">**Language (langue** ) Langue utilisée pour la reconnaissance vocale et la conversion de texte par synthèse vocale.</span><span class="sxs-lookup"><span data-stu-id="44002-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="44002-122">**IVR** Indique si le flux de travail est un groupe de recherche ou un flux de travail interactif.</span><span class="sxs-lookup"><span data-stu-id="44002-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="44002-123">**Activée** Indique si le flux de travail est activé pour recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="44002-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="44002-124">Pour plus d’informations sur les fonctionnalités et les fonctionnalités des groupes de réponse, voir [planifier l’application Response Group dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="44002-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="44002-125">Pour plus d’informations sur l’utilisation des flux de travail de groupe de réponse, voir [gestion des flux de travail de groupe de réponses](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="44002-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


