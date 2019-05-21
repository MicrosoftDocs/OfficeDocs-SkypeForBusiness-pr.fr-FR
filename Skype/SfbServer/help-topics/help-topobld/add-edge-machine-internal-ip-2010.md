---
title: Ajouter l’adresse IP 2010 interne de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
ms.openlocfilehash: 53b4a3d7d7347a151cc34195236f50d492206825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304715"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="210de-103">Ajouter l’adresse IP 2010 interne de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="210de-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="210de-104">Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="210de-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="210de-105">Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous voulez ajouter à la liste.</span><span class="sxs-lookup"><span data-stu-id="210de-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="210de-106">Dans **FQDN interne**, tapez le nom de domaine complet (FQDN) du serveur de périphérie que vous voulez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="210de-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="210de-107">Le nom de domaine complet (FQDN) que vous spécifiez doit être identique à celui de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="210de-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="210de-108">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="210de-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="210de-109">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="210de-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="210de-110">Par conséquent, vous devez configurer un suffixe DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant que serveur Edge qui n’est pas joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="210de-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="210de-111">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [configurer la prise en charge de DNS pour les périphériques](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="210de-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


