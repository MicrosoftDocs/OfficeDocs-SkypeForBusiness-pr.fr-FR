---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 927bdab6721583fd744f68969a852f29ba478027
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="4afd9-102">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="4afd9-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4afd9-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="4afd9-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="4afd9-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="4afd9-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4afd9-105">Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4afd9-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="4afd9-106">Une fois tous les utilisateurs déplacés vers Lync Server 2013, mais avant la désactivation du pool ou du réalisateur d’ancienne version d’Office Communications Server 2007 R2, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="4afd9-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="4afd9-107">Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="4afd9-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="4afd9-108">**Pour configurer un enregistrement SRV DNS**</span><span class="sxs-lookup"><span data-stu-id="4afd9-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="4afd9-109">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4afd9-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4afd9-110">Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, développez le domaine SIP dans lequel Lync Server 2013 est installé, puis accédez au paramètre \*\* \_TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="4afd9-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="4afd9-111">Dans le volet droit, cliquez avec le bouton droit sur \*\* \_sipinternaltls\*\* , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4afd9-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="4afd9-112">Dans la liste des **hôtes proposant ce service**, mettez à jour le nom de domaine complet (FQDN) du serveur pour qu’il pointe sur le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4afd9-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="4afd9-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4afd9-113">Click **OK**.</span></span>

<span data-ttu-id="4afd9-114">**Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu**</span><span class="sxs-lookup"><span data-stu-id="4afd9-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="4afd9-115">Connectez-vous à un ordinateur client dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="4afd9-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="4afd9-116">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="4afd9-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4afd9-117">Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4afd9-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4afd9-118">À l’invite de commandes, tapez **nslookup** \<FQDN du pool\> frontal ou \<du FQDN du serveur\>Standard Edition, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="4afd9-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="4afd9-119">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4afd9-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

