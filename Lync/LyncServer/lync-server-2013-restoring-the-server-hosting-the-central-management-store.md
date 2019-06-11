---
title: 'Lync Server 2013: restauration du serveur qui héberge le magasin de gestion central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="2cdda-102">Restauration du serveur qui héberge le magasin de gestion central dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cdda-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cdda-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2cdda-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2cdda-104">Le déploiement d’un serveur Lync dispose d’une banque d’administration centrale unique, dont une copie est répliquée sur chaque serveur exécutant un rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cdda-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="2cdda-105">Cette rubrique décrit la procédure de restauration d’un serveur principal ou d’un serveur Standard Edition Server qui héberge la Banque centrale de gestion.</span><span class="sxs-lookup"><span data-stu-id="2cdda-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="2cdda-106">Pour trouver le pool sur lequel se trouve le serveur de gestion central, ouvrez le générateur de topologies, cliquez sur **Lync Server**et recherchez dans le volet droit sous **serveur de gestion central**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="2cdda-107">Si le serveur principal hébergeant la Banque de gestion centrale se trouve dans une configuration en miroir et que la base de données miroir est toujours fonctionnelle, nous vous recommandons d’effectuer une sauvegarde de ce miroir en continu, puis de procéder à une restauration complète sur la base de données principale et sur la base de données miroir, à l’aide de cette sauvegarde, en suivant la procédure de restauration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2cdda-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="2cdda-108">Cela est nécessaire, car la restauration du serveur principal nécessite la modification et la publication de la topologie, et cette opération peut être réalisée uniquement si le CMS de la base de données principale est opérationnel.</span><span class="sxs-lookup"><span data-stu-id="2cdda-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="2cdda-109">Notez également que les rôles de base de données principaux et en miroir ne peuvent pas être modifiés si la topologie ne peut pas être publiée.</span><span class="sxs-lookup"><span data-stu-id="2cdda-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cdda-110">Si un serveur principal ou un serveur Standard Edition n’héberge pas le magasin d’administration centrale, voir <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restauration d’un serveur principal Enterprise Edition dans Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restauration d’un serveur Standard Edition Server dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2cdda-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="2cdda-111">S’il s’agit d’un serveur principal qui héberge le magasin central de gestion est dans une configuration en miroir et que le miroir ne peut pas être utilisé, voir <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurer un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="2cdda-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="2cdda-112">Si un autre serveur a échoué, voir <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restauration d’un serveur membre Enterprise Edition dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2cdda-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="2cdda-113">Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="2cdda-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2cdda-114">Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration.</span><span class="sxs-lookup"><span data-stu-id="2cdda-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2cdda-115">Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="2cdda-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="2cdda-116">Pour restaurer le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="2cdda-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="2cdda-117">Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="2cdda-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cdda-118">Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2cdda-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="2cdda-119">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe administrateurs locaux, connectez-vous au serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="2cdda-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="2cdda-120">Si vous restaurez un serveur Standard Edition Server, restaurez le magasin de fichiers à partir de $Backup à l’emplacement de stockage des fichiers sur le serveur, puis partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="2cdda-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2cdda-121">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé pour que les composants qui les utilisent puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="2cdda-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="2cdda-122">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2cdda-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="2cdda-123">Si vous installez un serveur Standard Edition Server, recherchez le dossier d’installation ou le média de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de Setup. exe amd64. exe.</span><span class="sxs-lookup"><span data-stu-id="2cdda-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="2cdda-124">Dans l’Assistant Déploiement, cliquez sur **préparer le premier Standard Edition Server** et suivez les instructions de l’Assistant pour installer le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="2cdda-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="2cdda-125">Si vous installez un serveur back-end d’entreprise, installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.</span><span class="sxs-lookup"><span data-stu-id="2cdda-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2cdda-126">En fonction du serveur que vous restaurez et sur votre déploiement, le serveur peut inclure plusieurs bases de données colocalisées ou distinctes.</span><span class="sxs-lookup"><span data-stu-id="2cdda-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="2cdda-127">Suivez la même procédure pour installer SQL Server que vous avez utilisé à l’origine pour déployer le serveur, y compris les autorisations et les connexions SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cdda-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="2cdda-128">À partir d’un serveur frontal, démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="2cdda-129">Recréez le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="2cdda-129">Re-create the Central Management store.</span></span> <span data-ttu-id="2cdda-130">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2cdda-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="2cdda-131">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2cdda-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="2cdda-132">Définissez le point de contrôle des services de domaine Active Directory pour le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="2cdda-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="2cdda-133">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2cdda-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="2cdda-134">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2cdda-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cdda-135">Si vous perdez le point de connexion, vous pouvez réexécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cdda-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="2cdda-136">Importez les données du magasin de gestion central à partir de $Backup.</span><span class="sxs-lookup"><span data-stu-id="2cdda-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="2cdda-137">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2cdda-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="2cdda-138">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2cdda-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="2cdda-139">Activez les modifications que vous venez d’apporter.</span><span class="sxs-lookup"><span data-stu-id="2cdda-139">Enable the changes you have just made.</span></span> <span data-ttu-id="2cdda-140">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2cdda-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cdda-141">Après l’activation de la topologie, vous pouvez rechercher le document de topologie dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2cdda-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="2cdda-142">Si vous restaurez un serveur principal Enterprise Edition qui héberge également le MCG, ou si vous avez besoin de recréer un miroir du MCG, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2cdda-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="2cdda-143">Dans le cas contraire, passez à l’étape 11.</span><span class="sxs-lookup"><span data-stu-id="2cdda-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="2cdda-144">Installez les bases de données autonomes en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="2cdda-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="2cdda-145">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="2cdda-146">Cliquez sur **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="2cdda-147">Sélectionnez la topologie, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="2cdda-148">Cliquez sur **Oui** pour confirmer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="2cdda-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="2cdda-149">Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="2cdda-150">Suivez l’Assistant d' **installation de base de données** .</span><span class="sxs-lookup"><span data-stu-id="2cdda-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="2cdda-151">S’il s’agit de la restauration d’une base de données autre que la Banque centrale de gestion de ce serveur, dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.</span><span class="sxs-lookup"><span data-stu-id="2cdda-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2cdda-152">Seules les bases de données autonomes sont affichées dans la page <STRONG>créer des bases de données</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="2cdda-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="2cdda-153">Les bases de données colocalisées sont créées lorsque vous exécutez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cdda-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="2cdda-154">Si vous restaurez un serveur principal en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que vous arriviez à l’invite de création d’une base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2cdda-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="2cdda-155">Sélectionnez la base de données que vous voulez installer, puis terminez la procédure.</span><span class="sxs-lookup"><span data-stu-id="2cdda-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="2cdda-156">Suivez les autres instructions de l’Assistant, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2cdda-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2cdda-157">Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de applet <STRONG>install-CsDatabase</STRONG> pour créer une base de données et l’applet de la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="2cdda-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="2cdda-158">Pour en savoir plus, voir <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">installer-CsDatabase</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">installer-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="2cdda-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="2cdda-159">Si vous restaurez un serveur Standard Edition Server, recherchez le dossier d’installation ou le média de Lync Server et démarrez l’Assistant Déploiement de Lync \\Server\\situé\\à l’installation de Setup. exe amd64. exe.</span><span class="sxs-lookup"><span data-stu-id="2cdda-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="2cdda-160">Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="2cdda-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="2cdda-161">Exécutez l' **étape 1: installer le magasin de configuration local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="2cdda-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="2cdda-162">Exécutez l' **étape 2: configurer ou supprimer les composants serveur Lync** pour installer les rôles serveur de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cdda-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="2cdda-163">Exécutez l' **étape 3: demandez, installez ou attribuez des certificats** pour attribuer les certificats.</span><span class="sxs-lookup"><span data-stu-id="2cdda-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="2cdda-164">Exécutez l' **étape 4: démarrer des services** pour démarrer des services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2cdda-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="2cdda-165">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement pour le rôle de serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="2cdda-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="2cdda-166">Restaurez les données utilisateur en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="2cdda-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="2cdda-167">Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="2cdda-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="2cdda-168">Avant de restaurer les données utilisateur, vous devez arrêter les services Lync.</span><span class="sxs-lookup"><span data-stu-id="2cdda-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="2cdda-169">Pour ce faire, tapez:</span><span class="sxs-lookup"><span data-stu-id="2cdda-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="2cdda-170">Pour restaurer les données utilisateur, à partir de la ligne de commande, tapez:</span><span class="sxs-lookup"><span data-stu-id="2cdda-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="2cdda-171">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2cdda-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="2cdda-172">Redémarrez les services Lync en entrant:</span><span class="sxs-lookup"><span data-stu-id="2cdda-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="2cdda-173">Restaurez les données d’informations de géolocalisation dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="2cdda-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="2cdda-174">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2cdda-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="2cdda-175">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2cdda-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="2cdda-176">Si vous avez déployé Response Group sur ce pool ou Server Standard Edition Server, restaurez les données de configuration du groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="2cdda-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="2cdda-177">Pour plus d’informations, consultez la rubrique [restauration des paramètres du groupe de réponses dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2cdda-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="2cdda-178">Si vous restaurez un serveur principal qui inclut l’archivage ou la surveillance de bases de données, restaurez les données d’archivage ou de contrôle à l’aide d’un outil de gestion SQL Server, tel que SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2cdda-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="2cdda-179">Pour plus d’informations, reportez-vous à la rubrique [restauration de données d’analyse ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="2cdda-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

