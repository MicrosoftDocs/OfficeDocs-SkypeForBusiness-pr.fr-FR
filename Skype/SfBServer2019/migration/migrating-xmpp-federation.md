---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Les versions précédentes fournissaient une passerelle de protocole (XMPP) de messagerie et de présence extensible peut être déployée en tant qu’un rôle de serveur distinct pour autoriser la fédération avec des déploiements XMPP. La fonctionnalité XMPP n’est plus disponible & déconseillées dans Skype pour Business Server 2019. Si vous souhaitez poursuivre la fonctionnalité XMPP, qui peut être eu dans un environnement coexitence avec la version héritée (Skype pour Business Server 2015 / Lync Server 2013). La fonctionnalité XMPP est installée en deux parties : comme un XMPP proxy qui s’exécute sur hérité serveur Edge et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.'
ms.openlocfilehash: fa91741c1be8d80443363caba7c840b1d985d8f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879327"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="a40d6-106">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="a40d6-106">Migrating XMPP federation</span></span>

<span data-ttu-id="a40d6-107">Les versions précédentes fournissaient une passerelle de protocole (XMPP) de messagerie et de présence extensible peut être déployée en tant qu’un rôle de serveur distinct pour autoriser la fédération avec des déploiements XMPP.</span><span class="sxs-lookup"><span data-stu-id="a40d6-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="a40d6-108">La fonctionnalité XMPP n’est plus disponible et est déconseillée dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a40d6-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="a40d6-109">Si vous souhaitez poursuivre la fonctionnalité XMPP, vous pouvez le faire dans un environnement de coexistence avec une version héritée (Skype pour Business Server 2015 ou Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="a40d6-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="a40d6-110">La fonctionnalité XMPP est installée en deux parties : comme un XMPP proxy qui s’exécute sur hérité serveur Edge et la passerelle XMPP qui s’exécute sur le serveur frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="a40d6-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="a40d6-111">À partir du point de vue de la migration, les utilisateurs qui souhaitent bénéficier de la fonctionnalité XMPP doivent rester dans le serveur hérité et ne doivent pas être déplacés vers un Skype pour le pool d’entreprise Server 2019 mais continuent à utiliser la passerelle XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="a40d6-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="a40d6-112">Cela est possible uniquement lorsque le partenaire fédéré XMPP est configuré dans Skype pour Business Server 2015 ou de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a40d6-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="a40d6-113">Vous ne devez pas migrer le serveur Edge hérité à Skype pour Business Server 2019 si vous souhaitez poursuivre la fonctionnalité XMPP.</span><span class="sxs-lookup"><span data-stu-id="a40d6-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="a40d6-114">Toutefois, vous pouvez avoir coexistence entre le serveur Edge hérité (avec Proxy XMPP) et le Skype pour Business 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="a40d6-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

