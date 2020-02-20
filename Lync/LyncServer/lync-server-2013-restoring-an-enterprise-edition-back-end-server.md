---
title: 'Lync Server 2013 : restauration d’un serveur principal Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1da289a6c0cf73e1466acdf28a74b1fbce76251a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="c2087-102">Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2087-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2087-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="c2087-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="c2087-104">Utilisez la procédure décrite dans cette rubrique dans les deux cas suivants :</span><span class="sxs-lookup"><span data-stu-id="c2087-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="c2087-105">Les bases de données principale et miroir d’un serveur principal Enterprise Edition mis en miroir échouent.</span><span class="sxs-lookup"><span data-stu-id="c2087-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="c2087-106">Un serveur principal Enterprise Edition qui n’est pas mis en miroir échoue.</span><span class="sxs-lookup"><span data-stu-id="c2087-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="c2087-107">Si vous disposez d’un serveur principal Enterprise Edition en miroir et que seule la base de données miroir ou principale échoue, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition en miroir dans Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) pour la restauration de la base de données principale et [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-miroir](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) pour restaurer le miroir.</span><span class="sxs-lookup"><span data-stu-id="c2087-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="c2087-108">Si le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="c2087-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="c2087-109">Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="c2087-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c2087-110">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="c2087-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="c2087-111">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="c2087-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="c2087-112">Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="c2087-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="c2087-113">Pour restaurer un serveur principal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c2087-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="c2087-114">Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="c2087-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c2087-115">Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="c2087-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="c2087-116">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="c2087-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="c2087-117">Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.</span><span class="sxs-lookup"><span data-stu-id="c2087-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c2087-118">En fonction de votre déploiement, le serveur principal peut inclure plusieurs bases de données colocalisées ou distinctes.</span><span class="sxs-lookup"><span data-stu-id="c2087-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="c2087-119">Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée à l’origine pour déployer le serveur, avec les autorisations et les comptes de connexion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c2087-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="c2087-120">Après avoir installé SQL Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c2087-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="c2087-121">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c2087-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="c2087-122">Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2087-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="c2087-p104">Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="c2087-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="c2087-125">Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="c2087-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="c2087-126">Suivez l’Assistant **Publication de la topologie**.</span><span class="sxs-lookup"><span data-stu-id="c2087-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="c2087-127">Sur la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.</span><span class="sxs-lookup"><span data-stu-id="c2087-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c2087-128">Seules les bases de données autonomes s’affichent dans la page <STRONG>Créer des bases de données</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c2087-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="c2087-129">Si vous restaurez un serveur principal qui a été mis en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que l’invite **créer une base de données miroir** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c2087-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="c2087-130">Sélectionnez la base de données que vous souhaitez installer et terminez le processus.</span><span class="sxs-lookup"><span data-stu-id="c2087-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="c2087-131">Suivez le reste de l’Assistant, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c2087-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c2087-132">Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de commande <STRONG>install-applet csdatabase</STRONG> pour créer chaque base de données et la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c2087-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="c2087-133">Pour plus d’informations, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c2087-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="c2087-134">Restaurez les données utilisateur en effectuant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c2087-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="c2087-135">Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="c2087-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="c2087-136">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2087-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="c2087-137">Avant de restaurer les données utilisateur, vous devez arrêter Lync services.</span><span class="sxs-lookup"><span data-stu-id="c2087-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="c2087-138">Pour ce faire, tapez :</span><span class="sxs-lookup"><span data-stu-id="c2087-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="c2087-139">Pour restaurer les données utilisateur, à la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="c2087-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="c2087-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c2087-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="c2087-141">Redémarrez Lync services en tapant :</span><span class="sxs-lookup"><span data-stu-id="c2087-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="c2087-142">Si vous avez déployé Response Group sur ce pool, restaurez les données de configuration du groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="c2087-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="c2087-143">Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c2087-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="c2087-144">Si vous restaurez un serveur principal qui inclut des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un outil SQL Server, tel que SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c2087-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="c2087-145">Pour plus d’informations, reportez-vous à la rubrique [restauration des données de surveillance ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="c2087-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

