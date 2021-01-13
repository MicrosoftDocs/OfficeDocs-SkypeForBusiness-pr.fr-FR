---
title: Définir le nom de domaine complet de la conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Vous créez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à l’aide de l’Assistant Définir un nouveau pool de conversation permanente. Sélectionnez un pool de plusieurs ordinateurs ou un pool d’un seul ordinateur. Si vous sélectionnez un pool d’ordinateurs unique et que vous avez besoin ultérieurement d’un pool de plusieurs ordinateurs, vous devez supprimer le pool d’un seul ordinateur, puis définir un pool de plusieurs ordinateurs.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818444"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="5d2e7-105">Définir le nom de domaine complet de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5d2e7-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="5d2e7-106">Vous créez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à l’aide de l’Assistant Définir **un nouveau pool de conversation** permanente.</span><span class="sxs-lookup"><span data-stu-id="5d2e7-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="5d2e7-107">Sélectionnez un **pool de plusieurs ordinateurs** ou **un pool d’un seul ordinateur.**</span><span class="sxs-lookup"><span data-stu-id="5d2e7-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="5d2e7-108">Si vous sélectionnez un pool d’ordinateurs unique et que vous avez besoin ultérieurement d’un pool de plusieurs ordinateurs, vous devez supprimer le pool d’un seul ordinateur, puis définir un pool de plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="5d2e7-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="5d2e7-109">Vous devez également définir un **nom de pool pour** le serveur de conversation permanente ou le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5d2e7-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="5d2e7-110">Le nom de domaine complet (FQDN) du pool d’un seul ordinateur doit être identique au nom de domaine complet de l’ordinateur qui constitue le pool de serveurs unique.</span><span class="sxs-lookup"><span data-stu-id="5d2e7-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="5d2e7-111">Pour un pool de plusieurs ordinateurs, le nom de domaine complet doit être le nom que vous choisissez pour représenter ce pool de plusieurs ordinateurs et est défini dans DNS par un enregistrement hôte A (et AAAA si IPv6 est utilisé).</span><span class="sxs-lookup"><span data-stu-id="5d2e7-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d2e7-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d2e7-112">See also</span></span>

[<span data-ttu-id="5d2e7-113">Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d2e7-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5d2e7-114">Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d2e7-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
