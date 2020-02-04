---
title: Ajouter l’adresse IP NAT du serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être routable publiquement. Ce n’est pas obligatoire, car vous avez sélectionné l’adresse IP externe de ce pool d’arêtes en option NAT dans la page Sélectionner des fonctionnalités de cet Assistant.
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698399"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="50f40-105">Ajouter l’adresse IP NAT du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="50f40-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="50f40-106">L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="50f40-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="50f40-107">L’adresse IP doit être routable publiquement.</span><span class="sxs-lookup"><span data-stu-id="50f40-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="50f40-108">Ce n’est pas obligatoire, car vous avez sélectionné **l’adresse IP externe de ce pool d’arêtes en option NAT** dans la page **Sélectionner des fonctionnalités** de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="50f40-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="50f40-109">La traduction d’adresses réseau (NAT) permet aux clients ou serveurs sur un réseau privé (par exemple, la plage 192.168.0.0) de communiquer avec des systèmes sur des réseaux distants via des réseaux Internet publics.</span><span class="sxs-lookup"><span data-stu-id="50f40-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="50f40-110">TAR fonctionne à l’aide d’une seule adresse IP publique sur une interface externe et en associant les adresses IP internes à une adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="50f40-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="50f40-111">Le mappage NAT mappe une adresse interne à l’adresse IP publique externe.</span><span class="sxs-lookup"><span data-stu-id="50f40-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="50f40-112">Le système distant voit uniquement l’adresse publique de la source.</span><span class="sxs-lookup"><span data-stu-id="50f40-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="50f40-113">Le système distant répond à la source et la source fait référence à la carte NAT pour déterminer l’adresse IP interne à laquelle la réponse doit être renvoyée.</span><span class="sxs-lookup"><span data-stu-id="50f40-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="50f40-p104">Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou par la suite. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, reportez-vous à la rubrique [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) de la documentation de déploiement des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="50f40-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


