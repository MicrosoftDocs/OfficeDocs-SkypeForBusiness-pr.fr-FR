---
title: File d’attente de réponse groupes créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Files d’attente de la réponse groupe contiennent des appels à un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.
ms.openlocfilehash: f5223aaca700c10a25631131db69a55de1362ddc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="c789a-103">File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante</span><span class="sxs-lookup"><span data-stu-id="c789a-103">Response Groups Queue: Create New or Edit Existing</span></span>
 
<span data-ttu-id="c789a-104">Files d’attente de la réponse groupe contiennent des appels à un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="c789a-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="c789a-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="c789a-105">UI Reference</span></span>

<span data-ttu-id="c789a-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="c789a-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="c789a-107">**Nom** Chaque file d’attente doit avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="c789a-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="c789a-108">Tapez un nom descriptif pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-108">Type a descriptive name for the queue.</span></span>
    
- <span data-ttu-id="c789a-109">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="c789a-109">**Description** This field is optional.</span></span> <span data-ttu-id="c789a-110">Elle permet de fournir des détails supplémentaires sur la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-110">Use it to provide additional details about the queue.</span></span>
    
- <span data-ttu-id="c789a-111">**Groupes** Sélectionnez les groupes de l’agent que vous souhaitez attribuer à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="c789a-112">Cliquez sur **Sélectionner** pour ajouter des groupes de l’agent à la liste.</span><span class="sxs-lookup"><span data-stu-id="c789a-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="c789a-113">Cliquez sur **Supprimer** pour supprimer le groupe sélectionné de l’agent à partir de la liste.</span><span class="sxs-lookup"><span data-stu-id="c789a-113">Click **Remove** to delete the selected agent group from the list.</span></span>
    
    <span data-ttu-id="c789a-114">Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="c789a-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="c789a-115">L’ordre des groupes de l’agent affecte l’ordre dans lequel Skype pour Business Server recherche un agent disponible.</span><span class="sxs-lookup"><span data-stu-id="c789a-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="c789a-116">Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.</span><span class="sxs-lookup"><span data-stu-id="c789a-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>
    
- <span data-ttu-id="c789a-117">**Activer le délai d’attente de la file d’attente** Activez cette case à cocher pour spécifier une période maximale d’un appelant doit attendre un agent répond à l’appel en attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="c789a-118">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c789a-118">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="c789a-119">**Délai d’attente (en secondes)** Sélectionnez ou tapez le nombre maximal de secondes pendant lesquelles qu'un appelant peut attendre avant un agent répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="c789a-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>
    
  - <span data-ttu-id="c789a-120">**Appeler l’action** Sélectionnez l’action qui se produit lorsqu’un appel arrive à expiration. Les choix possibles sont :</span><span class="sxs-lookup"><span data-stu-id="c789a-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>
    
  - <span data-ttu-id="c789a-121">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="c789a-121">**Disconnect**</span></span>
    
  - <span data-ttu-id="c789a-122">**Transférer à la messagerie vocale** Si vous sélectionnez cette option, dans **l’adresse de SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c789a-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="c789a-123">**Transférer à un numéro de téléphone** Si vous sélectionnez cette option, dans le **SIP adresse** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c789a-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="c789a-124">**Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c789a-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="c789a-125">Dans **adresse de SIP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="c789a-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="c789a-126">**Transférer à une autre file d’attente de** Si vous sélectionnez cette option, accédez à la file d’attente pour recevoir des appels lorsque le délai d’attente appels.</span><span class="sxs-lookup"><span data-stu-id="c789a-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>
    
- <span data-ttu-id="c789a-127">**Activer le dépassement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="c789a-128">Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c789a-128">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="c789a-129">**Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels de que la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c789a-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>
    
  - <span data-ttu-id="c789a-130">**Transférer l’appel** Sélectionnez l’appel doit intervenir lorsque le seuil de dépassement de capacité de file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="c789a-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>
    
  - <span data-ttu-id="c789a-131">**Appeler l’action** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de capacité de file d’attente est atteint.</span><span class="sxs-lookup"><span data-stu-id="c789a-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="c789a-132">Les choix possibles sont :</span><span class="sxs-lookup"><span data-stu-id="c789a-132">Your choices are:</span></span>
    
  - <span data-ttu-id="c789a-133">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="c789a-133">**Disconnect**</span></span>
    
  - <span data-ttu-id="c789a-134">**Transférer à la messagerie vocale** Si vous sélectionnez cette option, dans **l’adresse de SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c789a-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="c789a-135">**Transférer à un numéro de téléphone** Si vous sélectionnez cette option, dans le **SIP adresse** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c789a-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="c789a-136">**Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c789a-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="c789a-137">Dans **adresse de SIP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="c789a-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="c789a-138">**Transférer à une autre file d’attente de** Si vous sélectionnez cette option, accédez à la file d’attente qui est à recevoir des appels lorsque le seuil de dépassement de capacité de file d’attente est remplie.</span><span class="sxs-lookup"><span data-stu-id="c789a-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>
    
<span data-ttu-id="c789a-139">Pour plus d’informations sur les fonctionnalités de groupe de la réponse de, afficher un [Plan pour l’application de groupe de réponse dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c789a-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="c789a-140">Pour plus d’informations sur l’utilisation des files d’attente, voir [Gérer les files d’attente de réponse groupe](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="c789a-140">For details about working with queues, see [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>
  

