---
title: Restauration d’un serveur principal en miroir d’Enterprise Edition-miroir
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="64f0c-102">Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-Mirror</span><span class="sxs-lookup"><span data-stu-id="64f0c-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f0c-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="64f0c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="64f0c-104">Si vous disposez d’un serveur principal Enterprise Edition dans une configuration en miroir et que le miroir échoue uniquement, suivez les procédures décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="64f0c-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="64f0c-105">En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="64f0c-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="64f0c-106">En cas d’échec du serveur principal, voir [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="64f0c-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="64f0c-107">En cas d’échec de la base de données qui héberge la Banque d’administration centrale, voir [restauration du serveur qui héberge le magasin de gestion central dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="64f0c-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="64f0c-108">Si un serveur membre Enterprise Edition qui n’est pas le serveur principal ne fonctionne pas, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="64f0c-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="64f0c-109">Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="64f0c-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="64f0c-110">Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration.</span><span class="sxs-lookup"><span data-stu-id="64f0c-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="64f0c-111">Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="64f0c-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="64f0c-112">Pour restaurer la base de données miroir du serveur principal Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="64f0c-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="64f0c-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="64f0c-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="64f0c-114">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="64f0c-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="64f0c-115">Désinstaller la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="64f0c-115">Uninstall mirroring.</span></span> <span data-ttu-id="64f0c-116">Tout d’abord, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="64f0c-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="64f0c-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="64f0c-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="64f0c-118">Procédez de la sorte pour tous les types de bases de données sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="64f0c-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="64f0c-119">Créez un serveur propre ou nouveau doté du même nom de domaine complet (DB1.contoso.com) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="64f0c-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="64f0c-120">Ce serveur va fonctionner en tant que nouveau miroir.</span><span class="sxs-lookup"><span data-stu-id="64f0c-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="64f0c-121">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="64f0c-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="64f0c-122">Installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.</span><span class="sxs-lookup"><span data-stu-id="64f0c-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="64f0c-123">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="64f0c-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="64f0c-124">Utilisez le générateur de topologie pour installer la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="64f0c-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="64f0c-125">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="64f0c-125">Perform the following:</span></span>
    
      - <span data-ttu-id="64f0c-126">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64f0c-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="64f0c-127">Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topology**, puis cliquez sur **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="64f0c-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="64f0c-128">Suivez l’Assistant d' **installation de base de données** .</span><span class="sxs-lookup"><span data-stu-id="64f0c-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="64f0c-129">Dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.</span><span class="sxs-lookup"><span data-stu-id="64f0c-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="64f0c-130">Suivez les instructions de l’Assistant jusqu’à ce qu’une invite de **création de base de données miroir** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64f0c-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="64f0c-131">Sélectionnez la base de données que vous voulez installer et suivez ce processus.</span><span class="sxs-lookup"><span data-stu-id="64f0c-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="64f0c-132">Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de applet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="64f0c-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="64f0c-133">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="64f0c-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

