---
title: 'Lync Server 2013 : Configuration des enregistrements hôte DNS'
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
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="d0f9e-102">Configuration des enregistrements hôte DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f9e-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0f9e-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d0f9e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d0f9e-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="d0f9e-105">Pour configurer les enregistrements d’un hôte DNS</span><span class="sxs-lookup"><span data-stu-id="d0f9e-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="d0f9e-106">Sur le serveur DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="d0f9e-107">Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="d0f9e-108">Cliquez sur **nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="d0f9e-109">Cliquez sur **nom**, tapez le nom d’hôte de la liste (le nom de domaine est censé partir de la zone dans laquelle l’enregistrement est défini et qu’il n’est pas nécessaire d’entrer dans le cadre de l’enregistrement a).</span><span class="sxs-lookup"><span data-stu-id="d0f9e-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="d0f9e-110">Cliquez sur **IP Address (adresse IP**), puis tapez l’adresse IP virtuelle (VIP) de l’équilibrage de charge pour le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0f9e-111">Dans les déploiements qui utilisent un pool de réalisateurs, les enregistrements d’hôte (A) pour les URL simples doivent pointer vers l’adresse VIP du directeur de charge du directeur.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0f9e-112">Si vous déployez uniquement un serveur ou un directeur Enterprise Edition qui est connecté à la topologie sans équilibrage de charge, ou si vous déployez un serveur Standard Edition Server, tapez l’adresse IP du serveur Enterprise Edition Server, Standard Edition Server ou Director.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="d0f9e-113">Un équilibrage de charge est requis si vous déployez plusieurs serveurs ou Director Enterprise Edition dans un pool.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="d0f9e-114">Les équilibreurs de charge ne sont pas utilisés avec les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="d0f9e-115">Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="d0f9e-116">Pour créer un enregistrement A supplémentaires, répétez les étapes 4 et 5.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="d0f9e-117">Lorsque vous avez terminé de créer tous les enregistrements A dont vous avez besoin, cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="d0f9e-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

