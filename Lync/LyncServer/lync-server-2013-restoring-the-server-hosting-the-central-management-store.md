---
title: 'Lync Server 2013 : restauration du serveur qui héberge le magasin central de gestion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="f64ce-102">Restauration du serveur qui héberge le magasin central de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f64ce-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f64ce-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f64ce-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f64ce-104">Un déploiement Lync Server possède un seul magasin central de gestion, dont une copie est répliquée sur chaque serveur exécutant un rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f64ce-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="f64ce-105">Cette rubrique décrit comment restaurer un serveur principal ou un serveur Standard Edition qui héberge le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f64ce-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="f64ce-106">Pour trouver le pool où se trouve le serveur de gestion centralisée, ouvrez le générateur de topologies, cliquez sur **Lync Server**, puis regardez dans le volet droit sous **serveur de gestion centralisée**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="f64ce-107">Si le serveur principal qui héberge le magasin central de gestion se trouve dans une installation en miroir et que la base de données miroir reste fonctionnelle, nous vous recommandons d’effectuer une sauvegarde de ce miroir en continu, puis d’effectuer une restauration complète sur la base de données principale et sur le base de données miroir, à l’aide de cette sauvegarde, en suivant la procédure de restauration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f64ce-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="f64ce-108">Cette opération est nécessaire car la restauration du serveur principal nécessite la modification et la publication de la topologie, ce qui n’est possible que si la base de données principale hébergeant le MCG est opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="f64ce-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="f64ce-109">Notez également que les rôles de base de données principale et miroir ne peuvent pas être interchangeables si la topologie ne peut pas être publiée.</span><span class="sxs-lookup"><span data-stu-id="f64ce-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f64ce-110">Si un serveur principal ou un serveur Standard Edition qui n’héberge pas le magasin central de gestion a échoué, consultez la rubrique <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restauration d’un serveur principal Enterprise Edition dans Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restauration d’un serveur Standard Edition dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f64ce-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="f64ce-111">Si un serveur principal qui héberge le magasin central de gestion se trouve dans une configuration mise en miroir et que seul le miroir a échoué, consultez la rubrique <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="f64ce-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="f64ce-112">Si un autre serveur a échoué, consultez la rubrique <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restauration d’un serveur membre Enterprise Edition dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f64ce-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="f64ce-113">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="f64ce-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f64ce-114">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="f64ce-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f64ce-115">Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="f64ce-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="f64ce-116">Pour restaurer le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="f64ce-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="f64ce-117">Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="f64ce-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f64ce-118">Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="f64ce-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f64ce-119">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, ouvrez une session sur le serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="f64ce-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f64ce-120">Si vous restaurez un serveur Standard Edition, restaurez le magasin de fichiers en copiant le magasin de fichiers approprié à partir de $Backup vers l’emplacement du magasin de fichiers sur le serveur, puis partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="f64ce-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f64ce-121">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="f64ce-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="f64ce-122">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f64ce-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="f64ce-123">Si vous installez un serveur Standard Edition, accédez au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server qui \\se\\trouve\\à l’installation de amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="f64ce-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f64ce-124">Dans l’Assistant Déploiement, cliquez sur **préparer d’abord le serveur Standard Edition** et suivez l’Assistant pour installer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f64ce-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="f64ce-125">Si vous installez un serveur principal d’entreprise, installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.</span><span class="sxs-lookup"><span data-stu-id="f64ce-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f64ce-126">En fonction du serveur que vous restaurez et de votre déploiement, le serveur peut inclure plusieurs bases de données colocalisées ou distinctes.</span><span class="sxs-lookup"><span data-stu-id="f64ce-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="f64ce-127">Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée à l’origine pour déployer le serveur, avec les autorisations et les comptes de connexion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f64ce-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="f64ce-128">À partir d’un serveur frontal, démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="f64ce-129">Recréez le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f64ce-129">Re-create the Central Management store.</span></span> <span data-ttu-id="f64ce-130">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="f64ce-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f64ce-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="f64ce-132">Définissez le point de contrôle des services de domaine Active Directory pour le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f64ce-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="f64ce-133">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="f64ce-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f64ce-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f64ce-135">Si vous perdez le point de connexion, vous pouvez réexécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="f64ce-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="f64ce-136">Importez les données du magasin central de gestion à partir de $Backup.</span><span class="sxs-lookup"><span data-stu-id="f64ce-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="f64ce-137">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="f64ce-138">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f64ce-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="f64ce-p110">Activez les modifications que vous venez de faire. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f64ce-141">Lorsque vous avez activé la topologie, vous pouvez trouver le document de topologie dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f64ce-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="f64ce-142">Si vous restaurez un serveur principal Enterprise Edition qui héberge également le MCG, ou si vous devez recréer un miroir du MCG, suivez cette étape.</span><span class="sxs-lookup"><span data-stu-id="f64ce-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="f64ce-143">Sinon, passez à l’étape 11.</span><span class="sxs-lookup"><span data-stu-id="f64ce-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="f64ce-144">Installez les bases de données autonomes en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f64ce-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="f64ce-145">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f64ce-146">Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f64ce-p112">Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="f64ce-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="f64ce-149">Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="f64ce-150">Suivez l’Assistant d' **installation de base de données** .</span><span class="sxs-lookup"><span data-stu-id="f64ce-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="f64ce-151">Si vous restaurez une base de données autre que le magasin central de gestion sur ce serveur, dans la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.</span><span class="sxs-lookup"><span data-stu-id="f64ce-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f64ce-152">Seules les bases de données autonomes s’affichent dans la page <STRONG>Créer des bases de données</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f64ce-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="f64ce-153">Les bases de données colocalisées sont créées lorsque vous exécutez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f64ce-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="f64ce-154">Si vous restaurez un serveur principal en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que vous arriviez à une invite de créer une base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="f64ce-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="f64ce-155">Sélectionnez la base de données que vous souhaitez installer et terminez le processus.</span><span class="sxs-lookup"><span data-stu-id="f64ce-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="f64ce-156">Suivez le reste de l’Assistant, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f64ce-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f64ce-157">Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de commande <STRONG>install-applet csdatabase</STRONG> pour créer chaque base de données et la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="f64ce-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="f64ce-158">Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-applet csdatabase</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="f64ce-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="f64ce-159">Si vous restaurez un serveur Standard Edition, accédez au dossier d’installation ou au support de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="f64ce-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f64ce-160">Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f64ce-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="f64ce-161">Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="f64ce-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="f64ce-162">Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f64ce-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="f64ce-163">Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.</span><span class="sxs-lookup"><span data-stu-id="f64ce-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="f64ce-164">Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f64ce-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="f64ce-165">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, reportez-vous à la documentation de déploiement du rôle serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="f64ce-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="f64ce-166">Restaurez les données utilisateur en effectuant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f64ce-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f64ce-167">Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="f64ce-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f64ce-168">Avant de restaurer les données utilisateur, vous devez arrêter Lync services.</span><span class="sxs-lookup"><span data-stu-id="f64ce-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f64ce-169">Pour ce faire, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="f64ce-170">Pour restaurer les données utilisateur, à la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f64ce-171">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f64ce-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="f64ce-172">Redémarrez Lync services en tapant :</span><span class="sxs-lookup"><span data-stu-id="f64ce-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="f64ce-173">Restaurer les données d’informations d’emplacement dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f64ce-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="f64ce-174">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f64ce-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="f64ce-175">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f64ce-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="f64ce-176">Si vous avez déployé Response Group sur ce pool ou serveur Standard Edition, restaurez les données de configuration du groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="f64ce-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="f64ce-177">Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f64ce-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="f64ce-178">Si vous restaurez un serveur principal qui inclut des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un outil de gestion SQL Server, tel que SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f64ce-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="f64ce-179">Pour plus d’informations, reportez-vous à la rubrique [restauration des données de surveillance ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="f64ce-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

