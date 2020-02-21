---
title: 'Lync Server 2013 : Association de rapports de surveillance à une base de données miroir'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee0ddc9e5b505a03db1bb1b9f30780c4bc565b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="2a52d-102">Association des rapports de surveillance à une base de données miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a52d-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a52d-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="2a52d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="2a52d-104">Si vous configurez un miroir pour votre base de données de surveillance, cette base de données miroir prend le relais comme base de données principale en cas de basculement.</span><span class="sxs-lookup"><span data-stu-id="2a52d-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="2a52d-105">Toutefois, si vous utilisez les rapports de surveillance Lync Server et qu’un basculement se produit, vous pouvez constater que vos rapports de surveillance ne se connectent pas à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2a52d-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="2a52d-106">En effet, lorsque vous installez des rapports de surveillance, vous spécifiez uniquement l’emplacement de la base de données principale ; vous ne spécifiez pas l’emplacement de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2a52d-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="2a52d-107">Pour obtenir un basculement automatique des rapports de surveillance vers la base de données miroir, vous devez ajouter la base de données miroir en tant que « partenaire de basculement » aux deux bases de données utilisées par les rapports de surveillance (une base de données pour les données d’enregistrement des détails des appels et l’autre pour la qualité du Données de qualité de l’expérience (QoE)).</span><span class="sxs-lookup"><span data-stu-id="2a52d-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="2a52d-108">(Notez que cette étape doit être effectuée après avoir installé les rapports de surveillance.) Vous pouvez ajouter les informations de partenaire de basculement en modifiant manuellement les valeurs de chaîne de connexion utilisées par ces deux bases de données.</span><span class="sxs-lookup"><span data-stu-id="2a52d-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="2a52d-109">Pour ce faire, procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="2a52d-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="2a52d-110">Utilisez Internet Explorer pour ouvrir la page d’accueil **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="2a52d-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="2a52d-111">L’URL de la page d’accueil de Reporting Services comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2a52d-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="2a52d-112">Le préfixe **http :** .</span><span class="sxs-lookup"><span data-stu-id="2a52d-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="2a52d-113">Nom de domaine complet (FQDN) de l’ordinateur sur lequel Reporting Services est installé (par exemple, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="2a52d-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="2a52d-114">La chaîne de **caractères\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="2a52d-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="2a52d-115">Nom de l’instance de base de données dans laquelle les rapports de surveillance sont installés (par exemple, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="2a52d-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="2a52d-116">Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="2a52d-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="2a52d-117">Une fois que vous avez accédé à la page d’accueil de Reporting Services, cliquez sur **LyncServerReports**, puis sur **rapports\_content**.</span><span class="sxs-lookup"><span data-stu-id="2a52d-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="2a52d-118">Cela vous permettra d’accéder à la page de **contenu des rapports\_** pour les rapports de surveillance Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a52d-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="2a52d-119">Sur la **page\_contenu des rapports** , cliquez sur la source de données **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="2a52d-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="2a52d-120">Sur la page **CDRDB** , sous l’onglet **Propriétés** , recherchez la zone de texte intitulée **chaîne de connexion**.</span><span class="sxs-lookup"><span data-stu-id="2a52d-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="2a52d-121">La chaîne de connexion actuelle ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="2a52d-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="2a52d-122">**Source de données = (local\\) archinst ; catalogue initial = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="2a52d-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="2a52d-123">Modifiez la chaîne de connexion afin d’inclure le nom du serveur et l’instance de base de données pour la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2a52d-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="2a52d-124">Par exemple, si le serveur est nommé ATL-Mirror-001 et que la base de données miroir se trouve dans l’instance archinst, vous devrez ajouter pour spécifier la base de données miroir à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="2a52d-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="2a52d-125">**Partenaire de basculement = ATL-miroir\\-001 archinst**</span><span class="sxs-lookup"><span data-stu-id="2a52d-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="2a52d-126">La chaîne de connexion modifiée se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="2a52d-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="2a52d-127">**Source de données = (local\\) archinst ; Partenaire de basculement = ATL-miroir\\-001 archinst ; initial catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="2a52d-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="2a52d-128">Après avoir mis à jour la chaîne de connexion, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="2a52d-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="2a52d-129">Sur la page **CDRDB** , cliquez sur le lien **contenu des rapports\_** .</span><span class="sxs-lookup"><span data-stu-id="2a52d-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="2a52d-130">Cliquez sur la source de données **QMSDB** , puis modifiez la chaîne de connexion pour la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="2a52d-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="2a52d-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2a52d-131">For example:</span></span>
    
    <span data-ttu-id="2a52d-132">**Source de données = (local\\) archinst ; Partenaire de basculement = ATL-miroir\\-001 archinst ; initial catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="2a52d-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="2a52d-133">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="2a52d-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2a52d-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a52d-134">See Also</span></span>


[<span data-ttu-id="2a52d-135">Installation des rapports de surveillance Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a52d-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="2a52d-136">Utilisation des rapports de surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a52d-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

