---
title: Mettre à jour les enregistrements SRV DNS
description: Mettre à jour les enregistrements SRV DNS.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579590"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="de9a8-103">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="de9a8-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de9a8-104">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="de9a8-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="de9a8-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="de9a8-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="de9a8-106">Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de9a8-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="de9a8-107">Une fois que tous les utilisateurs ont été déplacés vers Lync Server 2013, mais avant que le pool ou le directeur de Lync Server 2010 hérité ne soit désactivé, vous devez mettre à jour les enregistrements SRV DNS dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="de9a8-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="de9a8-108">Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="de9a8-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="de9a8-109">**Pour configurer un enregistrement DNS SRV**</span><span class="sxs-lookup"><span data-stu-id="de9a8-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="de9a8-110">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="de9a8-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="de9a8-111">Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, développez le domaine SIP dans lequel Lync Server 2013 est installé, puis accédez au paramètre \*\* \_ TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="de9a8-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="de9a8-112">Dans le volet droit, cliquez avec le bouton droit sur \*\* \_ sipinternaltls\*\* , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="de9a8-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="de9a8-113">Dans **hôte offrant ce service**, mettez à jour le nom de domaine complet de l’hôte de sorte qu’il pointe vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de9a8-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="de9a8-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="de9a8-114">Click **OK**.</span></span>

<span data-ttu-id="de9a8-115">**Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu**</span><span class="sxs-lookup"><span data-stu-id="de9a8-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="de9a8-116">Ouvrez une session sur un ordinateur client du domaine.</span><span class="sxs-lookup"><span data-stu-id="de9a8-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="de9a8-117">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="de9a8-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="de9a8-118">Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="de9a8-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="de9a8-119">À l’invite de commandes, tapez **nslookup** \<FQDN of the Front End pool\> ou \<FQDN of the Standard Edition server\> , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="de9a8-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="de9a8-120">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="de9a8-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

