---
title: Définir le nom de domaine complet de la conversation permanente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Vous créez un nouveau serveur de Chat permanent ou d’un pool de serveur de conversation persistant à l’aide de l’Assistant de définir un nouveau Pool de Chat permanent. Sélectionnez soit un pool ordinateur plusieurs ou un seul ordinateur. Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.
ms.openlocfilehash: b4fbeb54c926573e908b361e7556fab9d87da848
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="88b63-105">Définir le nom de domaine complet de la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="88b63-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="88b63-106">Vous créez un nouveau serveur de Chat permanent ou d’un pool de serveur de conversation persistant à l’aide de l’Assistant de **Définir un nouveau Pool de Chat permanent** .</span><span class="sxs-lookup"><span data-stu-id="88b63-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="88b63-107">Sélectionnez un **pool comportant plusieurs ordinateurs** ou un **pool comportant un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="88b63-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="88b63-108">Lorsque vous sélectionnez un pool comportant un seul ordinateur et qu’ensuite vous avez besoin d’un pool comportant plusieurs ordinateurs, vous devez supprimer le pool comportant un seul ordinateur afin de définir un pool comportant plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="88b63-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="88b63-109">Vous devez également définir un **Pool de nom de domaine complet** pour le serveur de Chat permanent ou d’un pool de serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="88b63-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="88b63-110">Le nom de domaine complet (FQDN) pool pour un pool d’ordinateur unique doit être le même que le nom de domaine complet de l’ordinateur qui composent le pool de serveur unique.</span><span class="sxs-lookup"><span data-stu-id="88b63-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="88b63-111">Pour un pool de plusieurs ordinateur, le nom de domaine complet doit être le nom que vous choisissez pour représenter ce pool ordinateur multiples et êtes défini dans le serveur DNS par un hôte (et AAAA si IPv6 est utilisé) enregistrement.</span><span class="sxs-lookup"><span data-stu-id="88b63-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88b63-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88b63-112">See also</span></span>

#### 

[<span data-ttu-id="88b63-113">Plan pour un serveur de conversation permanents dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88b63-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="88b63-114">Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="88b63-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

