---
title: Ajouter la Machine adresse IP interne Edge 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.
ms.openlocfilehash: d25819b45fea7ba46501e931beeb8d5032b43c1f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975384"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="a4e2e-103">Ajouter la Machine adresse IP interne Edge 2010</span><span class="sxs-lookup"><span data-stu-id="a4e2e-103">Add Edge Machine Internal IP 2010</span></span>
 
<span data-ttu-id="a4e2e-104">Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
- <span data-ttu-id="a4e2e-105">Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>
    
- <span data-ttu-id="a4e2e-106">Dans **Nom de domaine complet interne**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>
    
<span data-ttu-id="a4e2e-107">Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur qui est configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="a4e2e-108">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a4e2e-109">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a4e2e-110">Par conséquent, vous devez configurer un suffixe de nom de domaine DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant qu’un serveur de périphérie qui n’est pas lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="a4e2e-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a4e2e-111">Pour plus d’informations sur l’ajout d’un suffixe DNS pour un nom d’ordinateur, voir [Configurer le serveur DNS pour la prise en charge Edge](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4e2e-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

