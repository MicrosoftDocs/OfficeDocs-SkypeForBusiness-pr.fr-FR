---
title: Ajouter un ordinateur frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous voulez ajouter en tant que serveur frontal du pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Après la publication de la topologie, la modification du nom de domaine complet nécessite la suppression du serveur dans le générateur de topologie et l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir définir et configurer un pool frontal dans la documentation de déploiement.
ms.openlocfilehash: a97437f9775c603ca768403f44699cfffc069fbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281478"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="de21f-106">Ajouter un ordinateur frontal</span><span class="sxs-lookup"><span data-stu-id="de21f-106">Add Front End Machine</span></span>

<span data-ttu-id="de21f-107">Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous voulez ajouter en tant que serveur frontal du pool.</span><span class="sxs-lookup"><span data-stu-id="de21f-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="de21f-108">Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie.</span><span class="sxs-lookup"><span data-stu-id="de21f-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="de21f-109">Après la publication de la topologie, la modification du nom de domaine complet nécessite la suppression du serveur dans le générateur de topologie et l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="de21f-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="de21f-110">Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="de21f-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de21f-111">Notez que le générateur de topologie indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool.</span><span class="sxs-lookup"><span data-stu-id="de21f-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="de21f-112">Le nombre maximal de serveurs pris en charge est 12.</span><span class="sxs-lookup"><span data-stu-id="de21f-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="de21f-113">Vous pouvez avoir jusqu’à 20 serveurs statefull définis dans le fabric, dont 12 peuvent être actifs et en ligne à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="de21f-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


