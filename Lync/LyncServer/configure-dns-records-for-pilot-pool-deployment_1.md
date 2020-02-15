---
title: Configuration des enregistrements DNS pour le déploiement du pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd9ae4eff928413838fc014a125b681aa15f0def
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="9e0d8-102">Configuration des enregistrements DNS pour le déploiement du pool pilote</span><span class="sxs-lookup"><span data-stu-id="9e0d8-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e0d8-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="9e0d8-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="9e0d8-104">Avant de déployer le pool pilote Lync Server 2013, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="9e0d8-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="9e0d8-106">**Pour configurer des enregistrement d’hôte DNS (A)**</span><span class="sxs-lookup"><span data-stu-id="9e0d8-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="9e0d8-107">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="9e0d8-108">Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="9e0d8-109">Cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="9e0d8-110">Cliquez sur **Nom**, tapez le nom d’hôte du pool (le nom de domaine est présumé à partir de la zone dans laquelle est défini l’enregistrement, il est inutile de l’entrer comme partie de l’enregistrement A).</span><span class="sxs-lookup"><span data-stu-id="9e0d8-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="9e0d8-111">Cliquez sur **adresse IP**, tapez l’adresse IP du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="9e0d8-112">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9e0d8-113">Lorsque vous avez terminé, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="9e0d8-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

