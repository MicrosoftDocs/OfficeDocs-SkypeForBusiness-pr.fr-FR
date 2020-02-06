---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les versions précédentes ont fourni une passerelle de service de messagerie et de présence extensible qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. La fonctionnalité XMPP n’est plus disponible & déconseillée dans Skype entreprise Server 2019. Si vous souhaitez continuer à utiliser la fonctionnalité XMPP, vous pouvez l’utiliser dans l’environnement coexitence avec la version héritée (Skype entreprise Server 2015/Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et sur la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813432"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="055fb-106">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="055fb-106">Migrating XMPP federation</span></span>

<span data-ttu-id="055fb-107">Les versions précédentes ont fourni une passerelle de service de messagerie et de présence extensible qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP.</span><span class="sxs-lookup"><span data-stu-id="055fb-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="055fb-108">La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="055fb-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="055fb-109">Si vous voulez continuer à utiliser la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype entreprise Server 2015 ou Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="055fb-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="055fb-110">La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge hérité et sur la passerelle XMPP qui s’exécute sur le serveur frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="055fb-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="055fb-111">Du point de vue de la migration, les utilisateurs qui souhaitent utiliser la fonctionnalité XMPP doivent demeurer sur le serveur hérité et ne doivent pas être déplacés vers un pool Skype entreprise Server 2019, mais continuer à utiliser l’ancienne passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="055fb-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="055fb-112">Ce n’est possible que lorsque le partenaire fédéré XMPP est configuré dans Skype entreprise Server 2015 ou Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="055fb-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="055fb-113">Pour continuer à utiliser la fonctionnalité XMPP, il est préférable de ne pas migrer le serveur Edge hérité vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="055fb-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="055fb-114">Toutefois, vous pouvez avoir coexistence du serveur Edge hérité (avec proxy XMPP) et du serveur Edge 2019 Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="055fb-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

