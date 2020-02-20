---
title: Restauration d’un serveur principal Enterprise Edition en miroir-principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfc3f9a44adbd4967e3d32ac7a515a55bc5d974
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="4f79d-102">Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal</span><span class="sxs-lookup"><span data-stu-id="4f79d-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f79d-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4f79d-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4f79d-104">Si vous disposez d’un serveur principal Enterprise Edition dans une configuration en miroir et que seule la base de données principale échoue, suivez les procédures décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="4f79d-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="4f79d-105">En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f79d-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="4f79d-106">Si seul le miroir échoue, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="4f79d-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="4f79d-107">Si la base de données hébergeant le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="4f79d-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="4f79d-108">Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f79d-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="4f79d-109">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="4f79d-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="4f79d-110">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="4f79d-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="4f79d-111">Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="4f79d-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="4f79d-112">Dans cette rubrique, l’exemple de base de données principale aura un nom de domaine complet (FQDN) de BE1.contoso.com et la base de données miroir aura le nom de domaine complet (FQDN) de BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4f79d-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="4f79d-113">Pour restaurer une base de données principale de serveur principal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4f79d-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="4f79d-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4f79d-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="4f79d-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f79d-116">Forcez toutes les bases de données configurées à basculer vers le miroir.</span><span class="sxs-lookup"><span data-stu-id="4f79d-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="4f79d-117">Pour chaque type de base de données que vous avez configuré sur ce serveur, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4f79d-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="4f79d-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4f79d-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="4f79d-119">Si vous avez configuré votre base de données principale afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique.</span><span class="sxs-lookup"><span data-stu-id="4f79d-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="4f79d-120">Une fois le basculement terminé, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f79d-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="4f79d-121">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="4f79d-122">Désactivez la mise en miroir sur le serveur principal : cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** , puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="4f79d-123">Sous l’onglet **général** , sous **associations**, désactivez la case à cocher **activer la mise en miroir du magasin SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="4f79d-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="4f79d-124">Procédez ainsi pour l’archivage et la surveillance, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4f79d-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="4f79d-125">Cliquez ensuite sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="4f79d-126">Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="4f79d-127">Sélectionnez le serveur principal qui fonctionne toujours (BE2.contoso.com) comme nouveau magasin SQL.</span><span class="sxs-lookup"><span data-stu-id="4f79d-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="4f79d-128">Pour ce faire, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="4f79d-129">Sous l’onglet **général** , sous **associations**, tapez le nom de domaine complet du serveur principal opérationnel dans le champ **magasin SQL Server** (dans notre exemple, BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4f79d-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="4f79d-130">Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="4f79d-131">Redémarrez les services afin que chaque serveur puisse lire la nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="4f79d-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="4f79d-132">À partir d’un environnement Lync Server Management Shell, exécutez les applets de commande suivantes sur chaque serveur frontal qui appartient à ce pool :</span><span class="sxs-lookup"><span data-stu-id="4f79d-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="4f79d-133">Désinstaller la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="4f79d-133">Uninstall mirroring.</span></span> <span data-ttu-id="4f79d-134">À partir d’un environnement Lync Server Management Shell, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4f79d-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="4f79d-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4f79d-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="4f79d-136">Procédez ainsi pour tous les types de bases de données sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="4f79d-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="4f79d-137">Créez un serveur nouveau ou propre qui a le même nom de domaine complet (dans cet exemple, DB1.contoso.com) comme ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="4f79d-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="4f79d-138">Ce serveur fonctionnera en tant que nouveau miroir.</span><span class="sxs-lookup"><span data-stu-id="4f79d-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="4f79d-139">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="4f79d-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="4f79d-140">Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.</span><span class="sxs-lookup"><span data-stu-id="4f79d-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="4f79d-141">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4f79d-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="4f79d-142">Utilisez le générateur de topologie pour installer la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="4f79d-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="4f79d-143">Effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f79d-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="4f79d-144">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="4f79d-145">Activer la mise en miroir sur le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="4f79d-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="4f79d-146">Pour ce faire, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="4f79d-147">Sous l’onglet **général** , sous **associations**, activez la case à cocher **activer la mise en miroir du magasin SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="4f79d-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="4f79d-148">Effectuez également cette opération pour l’archivage et la surveillance, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4f79d-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="4f79d-149">Ensuite, dans le champ **magasin SQL Server de mise en miroir** , tapez le nom de domaine complet (FQDN) du nouveau serveur (n cet exemple, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4f79d-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="4f79d-150">Cliquez ensuite sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="4f79d-151">Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="4f79d-152">Suivez l’Assistant d' **installation de base de données** .</span><span class="sxs-lookup"><span data-stu-id="4f79d-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="4f79d-153">Sur la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.</span><span class="sxs-lookup"><span data-stu-id="4f79d-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="4f79d-154">Suivez l’Assistant jusqu’à ce que vous arriviez à l’invite **créer une base de données miroir**.</span><span class="sxs-lookup"><span data-stu-id="4f79d-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="4f79d-155">Sélectionnez la base de données que vous souhaitez installer et terminez ce processus.</span><span class="sxs-lookup"><span data-stu-id="4f79d-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

