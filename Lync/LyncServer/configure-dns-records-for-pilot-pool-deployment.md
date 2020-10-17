---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac28f32d6dc68cbfa23c3c1620a23b67fc182c43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499541"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="dc424-102">Configuration des enregistrements DNS pour le déploiement d’un pool pilote</span><span class="sxs-lookup"><span data-stu-id="dc424-102">Configure DNS records for pilot pool deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc424-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="dc424-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="dc424-104">Avant de déployer le pool pilote Lync Server 2013, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote.</span><span class="sxs-lookup"><span data-stu-id="dc424-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="dc424-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="dc424-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="dc424-106">**Pour configurer des enregistrement d’hôte DNS (A)**</span><span class="sxs-lookup"><span data-stu-id="dc424-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="dc424-107">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="dc424-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="dc424-108">Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="dc424-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="dc424-109">Cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="dc424-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="dc424-110">Cliquez sur **nom**, tapez le nom d’hôte du pool Lync Server 2013 (le nom de domaine est supposé à partir de la zone dans laquelle l’enregistrement est défini et il n’est pas nécessaire de l’entrer comme partie de l’enregistrement A).</span><span class="sxs-lookup"><span data-stu-id="dc424-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="dc424-111">Cliquez sur **adresse IP**, tapez l’adresse IP du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="dc424-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="dc424-112">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc424-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="dc424-113">Lorsque vous avez terminé, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="dc424-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

