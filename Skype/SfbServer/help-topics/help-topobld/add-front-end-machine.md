---
title: Ajouter un ordinateur frontal
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool. Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie. Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir Définir et configurer un pool frontal dans la documentation de déploiement.
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800147"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="8488f-106">Ajouter un ordinateur frontal</span><span class="sxs-lookup"><span data-stu-id="8488f-106">Add Front End Machine</span></span>

<span data-ttu-id="8488f-107">Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="8488f-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="8488f-108">Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="8488f-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="8488f-109">Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="8488f-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="8488f-110">Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [Définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8488f-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8488f-111">Notez que le Générateur de topologie indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool.</span><span class="sxs-lookup"><span data-stu-id="8488f-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="8488f-112">Le nombre maximal de serveurs pris en charge est de 12.</span><span class="sxs-lookup"><span data-stu-id="8488f-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="8488f-113">Vous pouvez avoir jusqu’à 20 serveurs avec état définis dans la structure, dont 12 peuvent être actifs et en ligne à tout moment.</span><span class="sxs-lookup"><span data-stu-id="8488f-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


