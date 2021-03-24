---
title: Associer un pool frontal à un serveur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: Chaque pool frontal ne peut être associé qu’à un seul serveur Edge ou pool edge. Lorsque vous activez l’accès des utilisateurs externes pour un site, vous pouvez prendre en charge les utilisateurs distants. Vous pouvez également activer la prise en charge des utilisateurs fédérés, qui peut inclure la prise en charge des utilisateurs de fournisseurs de connectivité de messagerie instantanée publique spécifiques (tels que Windows Live) et la prise en charge des utilisateurs anonymes.
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103220"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="5b01d-105">Associer un pool frontal à un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="5b01d-105">Associate Front End With Edge</span></span>

<span data-ttu-id="5b01d-106">Chaque pool frontal ne peut être associé qu’à un seul serveur Edge ou pool edge.</span><span class="sxs-lookup"><span data-stu-id="5b01d-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="5b01d-107">Lorsque vous activez l’accès des utilisateurs externes pour un site, vous pouvez prendre en charge les utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="5b01d-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="5b01d-108">Vous pouvez également activer la prise en charge des utilisateurs fédérés, qui peut inclure la prise en charge des utilisateurs de fournisseurs de connectivité de messagerie instantanée publics spécifiques (tels que Windows Live) et la prise en charge des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="5b01d-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="5b01d-109">Tous les pools d’un site et les pools de plusieurs sites centraux peuvent utiliser le même serveur Edge si l’utilisation ne dépasse pas la capacité du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5b01d-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="5b01d-110">Pour plus d’informations sur la surveillance, y compris la mise à l'échelle, voir [Planification de l’accès des utilisateurs externes](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="5b01d-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="5b01d-111">Pour plus d’informations sur la conception d’une topologie en vue de prendre en charge l’accès des utilisateurs externes, voir [Définir la topologie Edge](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5b01d-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>