---
title: Mise en file d’attente de groupes de réponse créer un nouveau ou modifier un groupe existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Les files d’attente de groupe de réponse contiennent les appels d’un groupe de réponse tant qu’un agent ne répond pas à l’appel.
ms.openlocfilehash: ae1809a725a8bcb343347975e432adc053ad1d66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690809"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="92de6-103">File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante</span><span class="sxs-lookup"><span data-stu-id="92de6-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="92de6-104">Les files d’attente de groupe de réponse contiennent les appels d’un groupe de réponse tant qu’un agent ne répond pas à l’appel.</span><span class="sxs-lookup"><span data-stu-id="92de6-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="92de6-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="92de6-105">UI Reference</span></span>

<span data-ttu-id="92de6-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="92de6-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="92de6-107">**Nom** Chaque file d’attente doit avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="92de6-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="92de6-108">Tapez un nom descriptif pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="92de6-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="92de6-109">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="92de6-109">**Description** This field is optional.</span></span> <span data-ttu-id="92de6-110">Utilisez-la pour fournir des informations supplémentaires sur la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="92de6-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="92de6-111">**Groupes** Sélectionnez les groupes d’agents que vous voulez affecter à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="92de6-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="92de6-112">Cliquez sur **Sélectionner** pour ajouter des groupes d’agents à la liste.</span><span class="sxs-lookup"><span data-stu-id="92de6-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="92de6-113">Cliquez sur **supprimer** pour supprimer le groupe d’agents sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="92de6-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="92de6-114">Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="92de6-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="92de6-115">L’ordre des groupes d’agents affecte l’ordre dans lequel le serveur Skype entreprise recherche un agent disponible.</span><span class="sxs-lookup"><span data-stu-id="92de6-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="92de6-116">Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.</span><span class="sxs-lookup"><span data-stu-id="92de6-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="92de6-117">**Temps d’activation de la file d’attente** Activez cette case à cocher pour spécifier un délai maximal pendant lequel l’appelant doit patienter avant d’avoir répondu à l’appel.</span><span class="sxs-lookup"><span data-stu-id="92de6-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="92de6-118">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="92de6-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="92de6-119">**Période de délai (secondes)** Sélectionnez ou tapez le nombre maximal de secondes qu’un appelant peut patienter avant qu’un agent réponde à l’appel.</span><span class="sxs-lookup"><span data-stu-id="92de6-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="92de6-120">**Action appeler** Sélectionner l’action qui se produit lorsqu’un appel arrive à expiration. Les choix possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="92de6-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="92de6-121">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="92de6-121">**Disconnect**</span></span>

  - <span data-ttu-id="92de6-122">**Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format SIP :<username> @ <domainname> (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="92de6-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="92de6-123">**Transférer vers le numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** , tapez le numéro de téléphone au format SIP<number> @ <domainname> : (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="92de6-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="92de6-124">**Transférer vers l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92de6-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="92de6-125">Dans **adresse SIP**, tapez l’URI de l’utilisateur au format SIP :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="92de6-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="92de6-126">**Transférer vers une autre file d’attente** Si vous sélectionnez cette option, naviguez jusqu’à la file d’attente pour recevoir des appels lorsque le délai d’appels est écoulé.</span><span class="sxs-lookup"><span data-stu-id="92de6-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="92de6-127">**Activer le dépassement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels que la file d’attente peut contenir.</span><span class="sxs-lookup"><span data-stu-id="92de6-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="92de6-128">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="92de6-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="92de6-129">**Nombre maximum d’appels** Sélectionnez ou tapez le nombre maximal d’appels que la file d’attente peut contenir.</span><span class="sxs-lookup"><span data-stu-id="92de6-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="92de6-130">**Transférer l’appel** Sélectionnez l’appel qui doit agir lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="92de6-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="92de6-131">**Action appeler** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="92de6-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="92de6-132">Les choix possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="92de6-132">Your choices are:</span></span>

  - <span data-ttu-id="92de6-133">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="92de6-133">**Disconnect**</span></span>

  - <span data-ttu-id="92de6-134">**Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format SIP :<username> @ <domainname> (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="92de6-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="92de6-135">**Transférer vers le numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** , tapez le numéro de téléphone au format SIP<number> @ <domainname> : (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="92de6-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="92de6-136">**Transférer vers l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="92de6-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="92de6-137">Dans **adresse SIP**, tapez l’URI de l’utilisateur au format SIP :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="92de6-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="92de6-138">**Transférer vers une autre file d’attente** Si vous sélectionnez cette option, naviguez jusqu’à la file d’attente pour recevoir des appels lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="92de6-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="92de6-139">Pour plus d’informations sur les fonctionnalités et les fonctionnalités des groupes de réponse, voir [planifier l’application Response Group dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="92de6-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="92de6-140">Pour plus d’informations sur l’utilisation des files d’attente, reportez-vous à la rubrique [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="92de6-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


