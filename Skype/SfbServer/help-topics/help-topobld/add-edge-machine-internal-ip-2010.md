---
title: Ajouter l’adresse IP 2010 interne de l’ordinateur Edge
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.
ms.openlocfilehash: b54fae5ce536e1f859c4c05059b18b5e5067af7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873325"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="2db5d-103">Ajouter l’adresse IP 2010 interne de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="2db5d-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="2db5d-104">Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="2db5d-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="2db5d-105">Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="2db5d-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="2db5d-106">Dans **Nom de domaine complet interne**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="2db5d-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="2db5d-107">Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur qui est configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2db5d-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="2db5d-108">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="2db5d-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2db5d-109">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="2db5d-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2db5d-110">Par conséquent, vous devez configurer un suffixe de nom de domaine DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant qu’un serveur de périphérie qui n’est pas lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="2db5d-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2db5d-111">Pour plus d’informations sur l’ajout d’un suffixe DNS pour un nom d’ordinateur, voir [Configurer le serveur DNS pour la prise en charge Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="2db5d-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


