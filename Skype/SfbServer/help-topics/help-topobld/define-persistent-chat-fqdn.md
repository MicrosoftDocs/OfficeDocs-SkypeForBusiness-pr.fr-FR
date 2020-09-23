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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Vous créez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à l’aide de l’Assistant définir un nouveau pool de conversations permanentes. Sélectionnez un pool de plusieurs ordinateurs ou un pool d’un seul ordinateur. Si vous sélectionnez un seul pool d’ordinateurs et que vous avez plus besoin d’un pool de plusieurs ordinateurs, vous devez supprimer le pool d’ordinateurs unique, puis définir un pool de plusieurs ordinateurs.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217548"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="5ffac-105">Définir le nom de domaine complet de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5ffac-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="5ffac-106">Vous créez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à l’aide de l’Assistant **définir un nouveau pool de conversations permanentes** .</span><span class="sxs-lookup"><span data-stu-id="5ffac-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="5ffac-107">Sélectionnez un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="5ffac-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="5ffac-108">Si vous sélectionnez un seul pool d’ordinateurs et que vous avez plus besoin d’un pool de plusieurs ordinateurs, vous devez supprimer le pool d’ordinateurs unique, puis définir un pool de plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="5ffac-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="5ffac-109">Vous devez également définir un **nom de domaine complet du pool** pour le serveur de conversation permanente ou le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5ffac-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="5ffac-110">Le nom de domaine complet (FQDN) du pool pour un seul pool d’ordinateurs doit être identique au nom de domaine complet (FQDN) de l’ordinateur qui constitue le pool de serveur unique.</span><span class="sxs-lookup"><span data-stu-id="5ffac-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="5ffac-111">Pour un pool de plusieurs ordinateurs, le nom de domaine complet doit être le nom que vous choisissez pour représenter ce pool de plusieurs ordinateurs et est défini dans le système DNS par l’enregistrement A (et le nom AAAA si IPv6 est utilisé).</span><span class="sxs-lookup"><span data-stu-id="5ffac-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ffac-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ffac-112">See also</span></span>

[<span data-ttu-id="5ffac-113">Planifier le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ffac-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5ffac-114">Ajouter un serveur de conversation permanente à votre topologie Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ffac-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
