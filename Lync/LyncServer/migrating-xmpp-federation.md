---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5957be57e749cbf8e62532afef669a7404169e7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="82f81-102">Migration de la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="82f81-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82f81-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="82f81-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="82f81-104">Les versions précédentes de Lync Server et Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP.</span><span class="sxs-lookup"><span data-stu-id="82f81-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="82f81-105">Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="82f81-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="82f81-106">La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="82f81-107">Du point de vue de la migration, un compte d’utilisateur Lync Server peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="82f81-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="82f81-108">Cela n’est possible que si le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="82f81-109">En résumé, si Lync Server 2010 a été déployé avec la passerelle XMPP et la passerelle XMPP Office Communications Server 2007 R2, la Fédération XMPP a été activée pour les utilisateurs hérités de Lync Server 2010, pour migrer la Fédération XMPP vers Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="82f81-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="82f81-110">Déployez un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="82f81-111">Déployez un serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="82f81-112">Déplacer tous les utilisateurs vers le pool Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f81-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="82f81-113">Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="82f81-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="82f81-114">Activez la Fédération XMPP dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="82f81-115">Mettez à jour les entrées DNS de sorte qu’elles pointent vers la passerelle XMPP Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82f81-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

