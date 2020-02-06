---
title: Définir le nom de domaine complet de la conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Pour ce faire, vous devez créer un serveur de chat permanent ou un pool de serveurs de chat permanent à l’aide de l’Assistant définir un pool de discussions permanent. Sélectionnez un pool comportant plusieurs ordinateurs ou un pool comportant un seul ordinateur. Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820196"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="5b3a6-105">Définir le nom de domaine complet de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5b3a6-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="5b3a6-106">Pour ce faire, vous devez créer un serveur de chat permanent ou un pool de serveurs de chat permanent à l’aide de l’Assistant **définir un pool de discussions permanent** .</span><span class="sxs-lookup"><span data-stu-id="5b3a6-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="5b3a6-107">Sélectionnez un **pool comportant plusieurs ordinateurs** ou un **pool comportant un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="5b3a6-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="5b3a6-108">Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="5b3a6-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="5b3a6-109">Vous devez également définir un **nom de domaine complet de pool** pour le serveur de chat permanent ou le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5b3a6-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="5b3a6-110">Le nom de domaine complet (FQDN) du pool d’un seul pool d’ordinateurs doit être identique à celui de l’ordinateur qui compose le pool de serveur unique.</span><span class="sxs-lookup"><span data-stu-id="5b3a6-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="5b3a6-111">Dans le cas d’un pool d’ordinateurs multiples, le nom de domaine complet doit correspondre au nom que vous avez choisi pour représenter ce pool d’ordinateurs et est défini dans DNS par l’enregistrement de l’hôte A (et du protocole AAAA en cas d’utilisation D’ipv6).</span><span class="sxs-lookup"><span data-stu-id="5b3a6-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b3a6-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b3a6-112">See also</span></span>

[<span data-ttu-id="5b3a6-113">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5b3a6-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5b3a6-114">Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5b3a6-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
