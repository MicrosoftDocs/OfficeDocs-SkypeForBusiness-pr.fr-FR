---
title: 'Lync Server 2013 : restauration d’un serveur Standard Edition Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bffde0a5b6047aeb2eabe38ee10c6b313ff1f01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="6d5db-102">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d5db-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d5db-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6d5db-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6d5db-104">Si un serveur Standard Edition Server qui n’héberge pas le magasin central de gestion échoue, suivez les procédures décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="6d5db-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="6d5db-105">Si le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="6d5db-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6d5db-106">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="6d5db-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="6d5db-107">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="6d5db-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="6d5db-108">Vous pouvez créer la copie image après avoir installé le système d’exploitation et SQL Server, puis restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="6d5db-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="6d5db-109">Pour restaurer un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6d5db-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="6d5db-110">Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="6d5db-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d5db-111">Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="6d5db-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="6d5db-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, ouvrez une session sur le serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="6d5db-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="6d5db-113">Restaurez le magasin de fichiers en copiant le magasin de fichiers approprié à partir de $Backup vers l’emplacement du magasin de fichiers sur le serveur et partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="6d5db-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6d5db-114">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="6d5db-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="6d5db-115">Exécutez le générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="6d5db-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="6d5db-116">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6d5db-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="6d5db-117">Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d5db-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="6d5db-p103">Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="6d5db-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="6d5db-120">Accédez au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="6d5db-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="6d5db-121">Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d5db-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="6d5db-122">Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="6d5db-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="6d5db-123">Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d5db-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="6d5db-124">Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.</span><span class="sxs-lookup"><span data-stu-id="6d5db-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="6d5db-125">Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6d5db-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="6d5db-126">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement relative au rôle serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="6d5db-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="6d5db-127">Restaurez les données utilisateur en effectuant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="6d5db-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="6d5db-128">Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="6d5db-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="6d5db-129">Avant de restaurer les données utilisateur, vous devez arrêter Lync services.</span><span class="sxs-lookup"><span data-stu-id="6d5db-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="6d5db-130">Pour ce faire, tapez :</span><span class="sxs-lookup"><span data-stu-id="6d5db-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="6d5db-131">Pour restaurer les données utilisateur, à la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="6d5db-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="6d5db-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6d5db-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="6d5db-133">Redémarrez Lync services en tapant :</span><span class="sxs-lookup"><span data-stu-id="6d5db-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="6d5db-134">Si vous avez déployé Response Group sur ce serveur Standard Edition, restaurez les données de configuration Response Group.</span><span class="sxs-lookup"><span data-stu-id="6d5db-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="6d5db-135">Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6d5db-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="6d5db-136">Si vous avez déployé une conversation permanente sur ce serveur Standard Edition, restaurez la base de données de conversation permanente (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="6d5db-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="6d5db-137">Si vous avez utilisé la sauvegarde SQL Server pour sauvegarder la base de données de conversation permanente, utilisez les procédures de restauration SQL Server pour la restaurer.</span><span class="sxs-lookup"><span data-stu-id="6d5db-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="6d5db-138">Si vous avez utilisé la cmdlet Export-applet cspersistentchatdata pour la sauvegarder, utilisez l’applet de commande Import-applet cspersistentchatdata pour la restaurer.</span><span class="sxs-lookup"><span data-stu-id="6d5db-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

