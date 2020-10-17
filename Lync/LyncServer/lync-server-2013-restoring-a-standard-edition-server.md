---
title: 'Lync Server 2013 : restauration d’un serveur Standard Edition Server'
description: 'Lync Server 2013 : restauration d’un serveur Standard Edition Server.'
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
ms.openlocfilehash: 1d2cd6976324492e0539c47999f78434e1a82706
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542390"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f6c6d-103">Restauration d’un serveur Standard Edition Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6c6d-103">Restoring a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6c6d-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f6c6d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f6c6d-105">Si un serveur Standard Edition Server qui n’héberge pas le magasin central de gestion échoue, suivez les procédures décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-105">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="f6c6d-106">Si le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="f6c6d-106">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f6c6d-107">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-107">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f6c6d-108">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-108">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f6c6d-109">Vous pouvez créer la copie image après avoir installé le système d’exploitation et SQL Server, puis restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-109">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="f6c6d-110">Pour restaurer un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f6c6d-110">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="f6c6d-111">Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-111">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6c6d-112">Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-112">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f6c6d-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, ouvrez une session sur le serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-113">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f6c6d-114">Restaurez le magasin de fichiers en copiant le magasin de fichiers approprié à partir de $Backup vers l’emplacement du magasin de fichiers sur le serveur et partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-114">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6c6d-115">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-115">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="f6c6d-116">Exécutez le générateur de topologie :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-116">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="f6c6d-117">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f6c6d-118">Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-118">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f6c6d-p103">Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="f6c6d-121">Naviguez jusqu’au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server situé lors de l' \\ installation de \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-121">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f6c6d-122">Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-122">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="f6c6d-123">Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-123">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="f6c6d-124">Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-124">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="f6c6d-125">Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-125">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="f6c6d-126">Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-126">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="f6c6d-127">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement relative au rôle serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-127">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="f6c6d-128">Restaurez les données utilisateur en effectuant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-128">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f6c6d-129">Copiez ExportedUserData.zip de $Backup \\ vers un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-129">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f6c6d-130">Avant de restaurer les données utilisateur, vous devez arrêter Lync services.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-130">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f6c6d-131">Pour ce faire, tapez :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-131">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="f6c6d-132">Pour restaurer les données utilisateur, à la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-132">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f6c6d-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-133">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="f6c6d-134">Redémarrez Lync services en tapant :</span><span class="sxs-lookup"><span data-stu-id="f6c6d-134">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="f6c6d-135">Si vous avez déployé Response Group sur ce serveur Standard Edition, restaurez les données de configuration Response Group.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-135">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="f6c6d-136">Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f6c6d-136">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="f6c6d-137">Si vous avez déployé une conversation permanente sur ce serveur Standard Edition, restaurez la base de données de conversation permanente (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="f6c6d-137">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="f6c6d-138">Si vous avez utilisé la sauvegarde SQL Server pour sauvegarder la base de données de conversation permanente, utilisez les procédures de restauration SQL Server pour la restaurer.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-138">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="f6c6d-139">Si vous avez utilisé l’applet de commande Export-CsPersistentChatData pour la sauvegarder, utilisez la Import-CsPersistentChatData pour la restaurer.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-139">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

