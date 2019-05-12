---
title: File d’attente de groupes de réponses créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Files d’attente les appels vers un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.
ms.openlocfilehash: 2c7c474cb778fce03302bd1c579fac0f39649b7b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925136"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="b3593-103">File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante</span><span class="sxs-lookup"><span data-stu-id="b3593-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="b3593-104">Files d’attente les appels vers un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b3593-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b3593-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3593-105">UI Reference</span></span>

<span data-ttu-id="b3593-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="b3593-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b3593-107">**Nom** Chaque file d’attente doit avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="b3593-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="b3593-108">Tapez un nom descriptif pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="b3593-109">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="b3593-109">**Description** This field is optional.</span></span> <span data-ttu-id="b3593-110">Utilisez-le pour fournir plus d’informations sur la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="b3593-111">**Groupes** Sélectionnez les groupes d’agents que vous souhaitez attribuer à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="b3593-112">Cliquez sur **Sélectionner** pour ajouter des groupes d’agents à la liste.</span><span class="sxs-lookup"><span data-stu-id="b3593-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="b3593-113">Cliquez sur **Supprimer** pour supprimer le groupe d’agents sélectionné dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b3593-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="b3593-114">Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="b3593-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="b3593-115">L’ordre des groupes d’agents affecte l’ordre dans lequel Skype pour Business Server recherche un agent disponible.</span><span class="sxs-lookup"><span data-stu-id="b3593-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="b3593-116">Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.</span><span class="sxs-lookup"><span data-stu-id="b3593-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="b3593-117">**Activer le délai d’expiration de la file d’attente** Activez cette case à cocher pour spécifier une durée maximale pour l’appelant doit attendre un agent répond à l’appel en attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="b3593-118">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b3593-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b3593-119">**Délai d’expiration (secondes)** Sélectionnez ou tapez le nombre maximal de secondes de que l’appelant peut attendre avant qu’un agent répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b3593-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="b3593-120">**Action d’appel** Sélectionnez l’action qui se produit lorsqu’un appel arrive à expiration. Vos choix est les suivants :</span><span class="sxs-lookup"><span data-stu-id="b3593-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="b3593-121">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="b3593-121">**Disconnect**</span></span>

  - <span data-ttu-id="b3593-122">**Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3593-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b3593-123">**Transférer au numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3593-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b3593-124">**Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3593-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b3593-125">Dans **adresse IP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="b3593-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b3593-126">**Transférer vers une autre file d’attente** Si vous sélectionnez cette option, accédez à la file d’attente qui est à recevoir des appels lorsque le délai d’attente les appels.</span><span class="sxs-lookup"><span data-stu-id="b3593-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="b3593-127">**Activer le débordement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels que la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="b3593-128">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b3593-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b3593-129">**Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels de que la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3593-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="b3593-130">**Transférer l’appel** Sélectionnez l’appel d’effectuer une action lorsque le seuil de saturation de file d’attente est remplie.</span><span class="sxs-lookup"><span data-stu-id="b3593-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="b3593-131">**Action d’appel** Sélectionnez l’action qui se produit lorsque le seuil de saturation de file d’attente est remplie.</span><span class="sxs-lookup"><span data-stu-id="b3593-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="b3593-132">Vos choix est les suivants :</span><span class="sxs-lookup"><span data-stu-id="b3593-132">Your choices are:</span></span>

  - <span data-ttu-id="b3593-133">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="b3593-133">**Disconnect**</span></span>

  - <span data-ttu-id="b3593-134">**Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3593-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b3593-135">**Transférer au numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3593-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b3593-136">**Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3593-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b3593-137">Dans **adresse IP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="b3593-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b3593-138">**Transférer vers une autre file d’attente** Si vous sélectionnez cette option, accédez à la file d’attente qui recevra les appels lorsque le seuil de saturation de file d’attente est remplie.</span><span class="sxs-lookup"><span data-stu-id="b3593-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="b3593-139">Pour plus d’informations sur les fonctionnalités de Response Group, consultez [planification de l’application Response Group dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b3593-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="b3593-140">Pour plus d’informations sur l’utilisation des files d’attente, reportez-vous à la rubrique [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="b3593-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


