---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="1ac21-102">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="1ac21-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ac21-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="1ac21-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="1ac21-104">Les versions précédentes d’Office Communications Server proposaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct pour permettre la Fédération avec des déploiements XMPP.</span><span class="sxs-lookup"><span data-stu-id="1ac21-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="1ac21-105">Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1ac21-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="1ac21-106">La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="1ac21-107">Du point de vue de la migration, un compte d’utilisateur Office Communications Server 2007 R2 peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1ac21-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="1ac21-108">Cela n’est possible que si le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="1ac21-109">En résumé, si Office Communications Server a été déployé avec la passerelle XMPP Office Communications Server 2007 R2 et que la Fédération XMPP a été activée pour les utilisateurs hérités d’Office Communications Server 2007 R2, pour migrer la Fédération XMPP vers Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="1ac21-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="1ac21-110">Déployez un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="1ac21-111">Déployez un serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="1ac21-112">Déplacez tous les utilisateurs vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="1ac21-113">Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="1ac21-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="1ac21-114">Activez la Fédération XMPP dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="1ac21-115">Mettez à jour les entrées DNS de sorte qu’elles pointent vers la passerelle XMPP Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ac21-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

