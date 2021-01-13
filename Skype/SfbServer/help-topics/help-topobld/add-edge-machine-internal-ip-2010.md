---
title: Ajouter l’adresse IP 2010 interne de l’ordinateur Edge
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour préciser l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
ms.openlocfilehash: eb5d2d8aa7dd0d7827e13089f7588f5090b6744a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828784"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="c8abc-103">Ajouter l’adresse IP 2010 interne de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="c8abc-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="c8abc-104">Utilisez cette page pour préciser l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="c8abc-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="c8abc-105">Dans **l’adresse IPv4 interne,** tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="c8abc-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="c8abc-106">Dans le nom de domaine complet **interne,** tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="c8abc-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="c8abc-107">Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c8abc-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="c8abc-108">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="c8abc-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="c8abc-109">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="c8abc-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c8abc-110">Vous devez donc configurer un suffixe DNS (Domain Name System) sur le nom de l'ordinateur à déployer en tant que serveur Edge non joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="c8abc-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="c8abc-111">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span><span class="sxs-lookup"><span data-stu-id="c8abc-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


