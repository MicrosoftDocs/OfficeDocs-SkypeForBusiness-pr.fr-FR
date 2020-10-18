---
title: 'Lync Server 2013 : conditions requises pour publier une topologie'
description: 'Lync Server 2013 : configuration requise pour publier une topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577860"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="24a25-103">Conditions requises pour publier une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-103">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24a25-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="24a25-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="24a25-105">Cette rubrique décrit l’infrastructure et les logiciels requis pour publier une topologie, qu’il s’agisse du générateur de topologies ou de l’interface de ligne de commande de l’environnement de ligne de commande Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="24a25-105">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="24a25-106">Ces exigences sont en plus du système d’exploitation, des logiciels et des autorisations requis pour tous les outils d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24a25-106">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="24a25-107">Assurez-vous que vous répondez à tous les outils d’administration requis avant de publier une topologie.</span><span class="sxs-lookup"><span data-stu-id="24a25-107">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="24a25-108">Vous devez exécuter le générateur de topologie sur un ordinateur qui est joint au même domaine ou à la même forêt que le déploiement Lync Server 2013 que vous créez afin que les étapes de préparation des services de domaine Active Directory soient déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur pour publier correctement votre topologie.</span><span class="sxs-lookup"><span data-stu-id="24a25-108">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="24a25-p102">Les ordinateurs définis dans la topologie doivent être ajoutés au domaine, à l’exception des serveurs Edge, et aux services de domaine Active Directory (AD DS). En revanche, ils n’ont pas besoin d’être en ligne au moment où vous publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="24a25-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="24a25-111">Vous devez créer le partage de fichiers du pool et le mettre à la disposition des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="24a25-111">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="24a25-112">Pour publier un pool frontal Enterprise Edition, le serveur principal basé sur SQL Server doit être joint au domaine dans lequel vous déployez les serveurs, en ligne et configuré avec les règles de pare-feu appropriées pour le mettre à la disposition des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="24a25-112">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="24a25-113">Pour plus d’informations sur la spécification des exceptions de pare-feu, voir [Understanding Firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24a25-113">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="24a25-114">Pour plus d’informations sur la configuration de SQL Server, voir [configurer SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="24a25-114">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24a25-115">Le serveur Standard Edition dispose d’une base de données colocalisée qui acceptera la configuration publiée.</span><span class="sxs-lookup"><span data-stu-id="24a25-115">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="24a25-116">Vous devez d’abord exécuter la tâche <STRONG>préparer le premier serveur Standard Edition Server</STRONG> dans l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24a25-116">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="24a25-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24a25-117">See Also</span></span>


[<span data-ttu-id="24a25-118">Publier la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-118">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="24a25-119">Déléguer les autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-119">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="24a25-120">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-120">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="24a25-121">Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-121">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="24a25-122">Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a25-122">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

