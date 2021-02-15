---
title: 'File d’attente Response Groups : création d’une file d’attente ou modification d’une file d’attente existante'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Les files d’attente Response Group tiennent les appels à un groupe Response Group jusqu’à ce qu’un agent réponde à l’appel.
ms.openlocfilehash: cfe2d212f90f8dcdf83b8f827ebf470245ce87fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829314"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="eb51b-103">File d’attente des services Response Groups : création d’une nouvelle ou modification d’une file existante</span><span class="sxs-lookup"><span data-stu-id="eb51b-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="eb51b-104">Les files d’attente Response Group tiennent les appels à un groupe Response Group jusqu’à ce qu’un agent réponde à l’appel.</span><span class="sxs-lookup"><span data-stu-id="eb51b-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="eb51b-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="eb51b-105">UI Reference</span></span>

<span data-ttu-id="eb51b-106">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="eb51b-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="eb51b-107">**Nom** Chaque file d’attente doit avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="eb51b-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="eb51b-108">Tapez un nom descriptif pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="eb51b-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="eb51b-109">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="eb51b-109">**Description** This field is optional.</span></span> <span data-ttu-id="eb51b-110">Utilisez-le pour fournir des détails supplémentaires sur la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="eb51b-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="eb51b-111">**Groupes** Sélectionnez les groupes d’agents que vous souhaitez affecter à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="eb51b-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="eb51b-112">Cliquez **sur Sélectionner** pour ajouter des groupes d’agents à la liste.</span><span class="sxs-lookup"><span data-stu-id="eb51b-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="eb51b-113">Cliquez **sur Supprimer** pour supprimer le groupe d’agents sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="eb51b-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="eb51b-114">Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="eb51b-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="eb51b-115">L’ordre des groupes d’agents affecte l’ordre dans lequel Skype Entreprise Server recherche un agent disponible.</span><span class="sxs-lookup"><span data-stu-id="eb51b-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="eb51b-116">Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.</span><span class="sxs-lookup"><span data-stu-id="eb51b-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="eb51b-117">**Activer le délai d’attente de file d’attente** Cochez cette case pour spécifier une durée maximale pendant combien de temps un appelant doit attendre en attente avant qu’un agent réponde à l’appel.</span><span class="sxs-lookup"><span data-stu-id="eb51b-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="eb51b-118">Si vous sélectionnez cette option, vous devez également spécifier les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb51b-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="eb51b-119">**Délai d’attente (secondes)** Sélectionnez ou tapez le nombre maximal de secondes qu’un appelant peut attendre avant qu’un agent réponde à l’appel.</span><span class="sxs-lookup"><span data-stu-id="eb51b-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="eb51b-120">**Action d’appel** Sélectionnez l’action qui se produit à l’attente d’un appel. Vous avez le choix entre :</span><span class="sxs-lookup"><span data-stu-id="eb51b-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="eb51b-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="eb51b-121">**Disconnect**</span></span>

  - <span data-ttu-id="eb51b-122">**Forward to voice mail** Si vous sélectionnez cette option, dans l’adresse **SIP,** tapez une adresse de messagerie vocale au format sip ( par <username> @ <domainname> exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eb51b-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="eb51b-123">**Forward to telephone number** Si vous sélectionnez cette option, dans l’adresse **SIP,** tapez le numéro de téléphone au format sip ( par <number> @ <domainname> exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eb51b-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="eb51b-124">**Passer à l’adresse SIP** Sélectionnez cette option pour que l’appel soit transmis à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb51b-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="eb51b-125">Dans **l’adresse SIP,** tapez l’URI de l’utilisateur au format sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="eb51b-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="eb51b-126">**Forward to another queue** Si vous sélectionnez cette option, accédez à la file d’attente qui doit recevoir des appels au moment où les appels ont été mis à l’heure d’attente.</span><span class="sxs-lookup"><span data-stu-id="eb51b-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="eb51b-127">**Activer le dépassement de la file d’attente** Cochez cette case pour spécifier un nombre maximal d’appels que la file d’attente peut contenir.</span><span class="sxs-lookup"><span data-stu-id="eb51b-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="eb51b-128">Si vous sélectionnez cette option, vous devez également spécifier les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb51b-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="eb51b-129">**Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels que la file d’attente peut contenir.</span><span class="sxs-lookup"><span data-stu-id="eb51b-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="eb51b-130">**Forward the call** Sélectionnez l’appel à prendre en compte lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="eb51b-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="eb51b-131">**Action d’appel** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="eb51b-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="eb51b-132">Vos choix est les suivants :</span><span class="sxs-lookup"><span data-stu-id="eb51b-132">Your choices are:</span></span>

  - <span data-ttu-id="eb51b-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="eb51b-133">**Disconnect**</span></span>

  - <span data-ttu-id="eb51b-134">**Forward to voice mail** Si vous sélectionnez cette option, dans l’adresse **SIP,** tapez une adresse de messagerie vocale au format sip ( par <username> @ <domainname> exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eb51b-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="eb51b-135">**Forward to telephone number** Si vous sélectionnez cette option, dans l’adresse **SIP,** tapez le numéro de téléphone au format sip ( par <number> @ <domainname> exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eb51b-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="eb51b-136">**Passer à l’adresse SIP** Sélectionnez cette option pour que l’appel soit transmis à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb51b-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="eb51b-137">Dans **l’adresse SIP,** tapez l’URI de l’utilisateur au format sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="eb51b-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="eb51b-138">**Forward to another queue** Si vous sélectionnez cette option, accédez à la file d’attente qui doit recevoir des appels lorsque le seuil de dépassement de la file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="eb51b-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="eb51b-139">Pour plus d’informations sur les fonctionnalités de Response Group, voir [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="eb51b-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="eb51b-140">Pour plus d’informations sur l’utilisation des files d’attente, voir [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="eb51b-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


