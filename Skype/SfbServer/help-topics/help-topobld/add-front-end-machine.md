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
ms.openlocfilehash: b100cfd933f19c87213fa48d4d030eda52e90dc8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119763"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="8608c-106">Ajouter un ordinateur frontal</span><span class="sxs-lookup"><span data-stu-id="8608c-106">Add Front End Machine</span></span>

<span data-ttu-id="8608c-107">Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="8608c-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="8608c-108">Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="8608c-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="8608c-109">Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="8608c-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="8608c-110">Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [Définir et configurer un pool frontal](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8608c-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8608c-111">Notez que le Générateur de topologie indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool.</span><span class="sxs-lookup"><span data-stu-id="8608c-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="8608c-112">Le nombre maximal de serveurs pris en charge est de 12.</span><span class="sxs-lookup"><span data-stu-id="8608c-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="8608c-113">Vous pouvez avoir jusqu’à 20 serveurs avec état définis dans la structure, dont 12 peuvent être actifs et en ligne à tout moment.</span><span class="sxs-lookup"><span data-stu-id="8608c-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>