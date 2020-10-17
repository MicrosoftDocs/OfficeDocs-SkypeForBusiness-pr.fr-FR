---
title: 'Lync Server 2013 : configuration des enregistrements d’hôte DNS'
description: 'Lync Server 2013 : configurez les enregistrements d’hôte DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd403402d0d2f089d7fc92a62296a56df0cf2e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553430"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="e2b05-103">Configuration des enregistrements d’hôte DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b05-103">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b05-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e2b05-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e2b05-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="e2b05-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="e2b05-106">Pour configurer des enregistrement d’hôte DNS (A)</span><span class="sxs-lookup"><span data-stu-id="e2b05-106">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="e2b05-107">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e2b05-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="e2b05-108">Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="e2b05-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="e2b05-109">Cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="e2b05-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="e2b05-110">Cliquez sur **Nom**, tapez le nom d’hôte du pool (le nom de domaine est présumé à partir de la zone dans laquelle est défini l’enregistrement, il est inutile de l’entrer comme partie de l’enregistrement A).</span><span class="sxs-lookup"><span data-stu-id="e2b05-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="e2b05-111">Cliquez sur **adresse IP**, tapez l’adresse IP virtuelle de l’équilibreur de charge pour le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="e2b05-111">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e2b05-112">Dans les déploiements qui utilisent un pool directeur, les enregistrements hôtes (A) pour les URL simples doivent pointer sur l’adresse IP virtuelle du programme d’équilibrage de la charge du directeur.</span><span class="sxs-lookup"><span data-stu-id="e2b05-112">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2b05-p101">Si vous déployez un seul serveur Enterprise Edition Server connecté à la topologie sans programme d’équilibrage de la charge, ou si vous déployez un serveur Standard Edition, tapez l’adresse IP du serveur Enterprise Edition Server, Standard Edition Server ou du directeur. L’utilisation d’un programme d’équilibrage de la charge est nécessaire si vous déployez plusieurs serveurs Enterprise Edition Server ou directeur dans un pool. Les programmes d’équilibrage de la charge ne sont pas utilisés avec les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e2b05-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="e2b05-116">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2b05-116">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="e2b05-117">Pour créer un enregistrement A supplémentaire, répétez les étapes 4 et 5.</span><span class="sxs-lookup"><span data-stu-id="e2b05-117">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="e2b05-118">Lorsque vous avez terminé de créer tous les enregistrements A dont vous avez besoin, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e2b05-118">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

