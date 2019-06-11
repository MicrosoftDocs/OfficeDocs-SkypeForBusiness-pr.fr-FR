---
title: 'Lync Server 2013: Association de rapports d’analyse à une base de données miroir'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="a089b-102">Association de rapports d’analyse à une base de données miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a089b-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a089b-103">_**Dernière modification de la rubrique:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="a089b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="a089b-104">Si vous configurez une instance miroir pour votre base de données de surveillance, cette base de données miroir prendra la relève en tant que base de données principale en cas de basculement.</span><span class="sxs-lookup"><span data-stu-id="a089b-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="a089b-105">Toutefois, si vous utilisez les rapports de surveillance de Lync Server et un basculement, il est possible que vos rapports d’analyse ne se connectent pas à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a089b-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="a089b-106">Et ce, car, lorsque vous installez des rapports de surveillance, vous spécifiez seulement l’emplacement de la base de données principale ; vous devez aussi spécifier l’emplacement de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a089b-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="a089b-p102">Pour que les rapports basculent automatiquement sur la base de données miroir, vous devez ajouter la base de données miroir comme « partenaire de basculement » pour les deux bases de données utilisées par les rapports de surveillance (l’une pour les données d’enregistrement des détails des appels, et l’autre pour les données de la qualité de l’expérience (QoE)). (Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire de basculement en modifiant manuellement les valeurs des chaînes de connexion utilisées par ces deux bases de données. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a089b-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="a089b-p103">Utilisez Internet Explorer pour ouvrir la page d’accueil de **SQL Server Reporting Services**. L’URL de cette page d’accueil comprend ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a089b-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="a089b-112">Le préfixe **http:**.</span><span class="sxs-lookup"><span data-stu-id="a089b-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="a089b-113">Le nom de domaine complet (FQDN) de l’ordinateur sur lequel les services de surveillance sont installés (par exemple, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="a089b-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="a089b-114">La chaîne de **caractères\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="a089b-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="a089b-115">Le nom de l’instance de la base de données où les rapports de surveillance sont installés (par exemple, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="a089b-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="a089b-116">Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="a089b-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="a089b-117">Après avoir consulté la page d’accueil de Reporting Services, cliquez sur **LyncServerReports**, puis cliquez sur **signaler\_le contenu**.</span><span class="sxs-lookup"><span data-stu-id="a089b-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="a089b-118">Vous serez ainsi dirigé vers la page de **contenu du rapport\_** pour les rapports de surveillance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a089b-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="a089b-119">Dans la page de **contenu du rapport\_** , cliquez sur la source de données **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="a089b-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="a089b-p105">Sur la page **CDRDB**, sous l’onglet **Propriétés**, recherchez le texte intitulé **Chaîne de connexion**. La chaîne de connexion actuelle a un format similaire à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="a089b-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="a089b-122">**Source de données = (local\\) archinst; catalogue initial = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="a089b-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="a089b-p106">Modifiez la chaîne de connexion façon à y inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-miroir-001 et que la base de données miroir est dans l’instance archinst, vous devez en plus spécifier la base de données miroir en utilisant cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="a089b-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="a089b-125">**Partenaire de basculement = ATL-miroir\\-001 archinst**</span><span class="sxs-lookup"><span data-stu-id="a089b-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="a089b-126">Votre chaîne de connexion modifiée ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="a089b-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="a089b-127">**Source de données = (local\\) archinst; Partenaire de basculement = ATL-Mirror\\-001 archinst; initial catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="a089b-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="a089b-128">Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="a089b-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="a089b-129">Dans la page **CDRDB** , cliquez sur le lien **rapports\_** sur le contenu.</span><span class="sxs-lookup"><span data-stu-id="a089b-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="a089b-130">Cliquez sur la source de données **QMSDB**, puis modifiez la chaîne de connexion pour la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="a089b-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="a089b-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a089b-131">For example:</span></span>
    
    <span data-ttu-id="a089b-132">**Source de données = (local\\) archinst; Partenaire de basculement = ATL-Mirror\\-001 archinst; initial catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="a089b-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="a089b-133">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="a089b-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a089b-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a089b-134">See Also</span></span>


[<span data-ttu-id="a089b-135">Installation des rapports d’analyse Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a089b-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="a089b-136">Utilisation de rapports d’analyse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a089b-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

