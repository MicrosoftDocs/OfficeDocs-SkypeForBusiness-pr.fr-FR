---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les versions précédentes fournissaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible & déconseillée dans Skype entreprise Server 2019. Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez l’utiliser dans un environnement coexitence avec une version héritée (Skype entreprise Server 2015/Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752646"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="8b082-106">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="8b082-106">Migrating XMPP federation</span></span>

<span data-ttu-id="8b082-107">Les versions précédentes fournissaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP.</span><span class="sxs-lookup"><span data-stu-id="8b082-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8b082-108">La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b082-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="8b082-109">Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype entreprise Server 2015 ou Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="8b082-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="8b082-110">La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="8b082-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="8b082-111">Du point de vue de la migration, les utilisateurs qui souhaitent utiliser la fonctionnalité XMPP doivent rester sur le serveur hérité et ne doivent pas être déplacés vers un pool Skype entreprise Server 2019, mais continuer à utiliser la passerelle XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="8b082-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="8b082-112">Ceci n’est possible que lorsque le partenaire fédéré XMPP est configuré dans Skype entreprise Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b082-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="8b082-113">Vous ne devez pas migrer le serveur Edge hérité vers Skype entreprise Server 2019 si vous souhaitez continuer à utiliser la fonctionnalité XMPP.</span><span class="sxs-lookup"><span data-stu-id="8b082-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="8b082-114">Toutefois, vous pouvez coexister le serveur Edge hérité (avec le proxy XMPP) et le serveur Edge Skype entreprise 2019.</span><span class="sxs-lookup"><span data-stu-id="8b082-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

