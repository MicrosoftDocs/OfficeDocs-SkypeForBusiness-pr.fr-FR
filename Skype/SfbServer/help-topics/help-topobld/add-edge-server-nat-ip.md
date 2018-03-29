---
title: Ajouter l’adresse IP du serveur NAT bord
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L’adresse IP publique est l’adresse IP qui est utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement repositionnable. Ceci est nécessaire car vous avez sélectionné l’adresse IP externe de ce bord pool est traduite en option NAT sur la page Sélectionnez les fonctionnalités de cet Assistant.
ms.openlocfilehash: 4bfbcb7d8859dc928c78c8e32b21604ef473317b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="21073-105">Ajouter l’adresse IP du serveur NAT bord</span><span class="sxs-lookup"><span data-stu-id="21073-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="21073-106">L’adresse IP publique est l’adresse IP qui est utilisée par la traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="21073-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="21073-107">L’adresse IP doit être publiquement repositionnable.</span><span class="sxs-lookup"><span data-stu-id="21073-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="21073-108">Ceci est nécessaire car vous avez sélectionné l’option de **l’adresse IP externe de ce pool de bord est convertie par NAT** sur la page **Sélectionnez des fonctionnalités** de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="21073-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21073-109">Traduction d’adresses réseau (NAT) permet des clients ou des serveurs sur un réseau privé (par exemple, le 192.168.0.0 plage) de communiquer avec les systèmes sur des réseaux distants via les réseaux Internet publics.</span><span class="sxs-lookup"><span data-stu-id="21073-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="21073-110">NAT fonctionne en utilisant une seule adresse IP publique sur une interface externe et en associant les adresses IP internes avec une adresse IP publique.</span><span class="sxs-lookup"><span data-stu-id="21073-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="21073-111">Mappage NAT mappe une adresse interne à l’adresse IP publique externe.</span><span class="sxs-lookup"><span data-stu-id="21073-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="21073-112">Le système distant ne voit que l’adresse publique de la source.</span><span class="sxs-lookup"><span data-stu-id="21073-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="21073-113">Le système distant répond à la source, et la source fait référence à la table NAT pour déterminer l’adresse IP interne à que la réponse doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="21073-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="21073-114">Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou par la suite.</span><span class="sxs-lookup"><span data-stu-id="21073-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="21073-115">Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, consultez [Définition de votre topologie de bord](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) dans la documentation de déploiement de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="21073-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

