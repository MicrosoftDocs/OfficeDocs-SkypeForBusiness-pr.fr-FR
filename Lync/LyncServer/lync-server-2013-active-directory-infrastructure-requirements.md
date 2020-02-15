---
title: 'Lync Server 2013 : configuration requise pour l’infrastructure Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="f46b6-102">Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f46b6-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f46b6-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f46b6-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f46b6-104">Avant de commencer le processus de préparation des services de domaine Active Directory pour Lync Server 2013, assurez-vous que votre infrastructure Active Directory répond aux conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="f46b6-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="f46b6-105">Tous les contrôleurs de domaine (qui incluent tous les serveurs de catalogue global) dans la forêt où vous déployez Lync Server exécutent l’un des systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="f46b6-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="f46b6-106">Système d’exploitation Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f46b6-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="f46b6-107">Système d’exploitation Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f46b6-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="f46b6-108">système d’exploitation Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f46b6-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="f46b6-109">système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f46b6-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="f46b6-110">Windows Server 2008 Enterprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="f46b6-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="f46b6-111">versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="f46b6-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="f46b6-112">versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="f46b6-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="f46b6-113">Tous les domaines dans lesquels vous déployez Lync Server sont élevés à un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f46b6-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="f46b6-114">La forêt dans laquelle vous déployez Lync Server est élevée à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f46b6-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f46b6-115">Pour modifier le niveau fonctionnel de votre domaine ou de votre forêt, voir « augmentation des niveaux fonctionnels des domaines et <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>des forêts » dans la bibliothèque TechNet à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f46b6-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="f46b6-116">Un catalogue global est déployé dans chaque domaine où vous déployez des ordinateurs ou des utilisateurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f46b6-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="f46b6-117">Lync Server 2013 prend en charge les groupes universels dans les systèmes d’exploitation Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f46b6-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="f46b6-118">Les membres des groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arborescence de domaine ou de la forêt et peuvent se voir attribuer des autorisations dans n’importe quel domaine de l’arborescence de domaine ou de la forêt.</span><span class="sxs-lookup"><span data-stu-id="f46b6-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="f46b6-119">La prise en charge de groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f46b6-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="f46b6-120">Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre pour permettre à un administrateur de gérer les deux.</span><span class="sxs-lookup"><span data-stu-id="f46b6-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

