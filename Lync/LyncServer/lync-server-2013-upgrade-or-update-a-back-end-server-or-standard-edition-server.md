---
title: Mettre à niveau ou mettre à jour un serveur principal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213a945d27c2c5d0ee2135fd0d96bbe1c29c1971
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="575aa-102">Mise à niveau ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="575aa-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="575aa-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="575aa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="575aa-104">Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="575aa-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="575aa-p101">Si un serveur principal est arrêté durant au moins 30 minutes lors de sa mise à niveau, les utilisateurs peuvent être placés en mode Résilience. Lorsque la mise à mise à niveau est terminée et que les serveurs principaux sont encore connectés aux serveurs frontaux du pool, les utilisateurs repassent en fonctionnalité complète. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne seront pas affectés.</span><span class="sxs-lookup"><span data-stu-id="575aa-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="575aa-108">Pour mettre à jour un serveur principal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="575aa-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="575aa-109">Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="575aa-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="575aa-110">Téléchargez la mise à jour et extrayez-la sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="575aa-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="575aa-111">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="575aa-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="575aa-p102">Arrêtez les services Lync Server. À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="575aa-p102">Stop Lync Server services. At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="575aa-p103">Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="575aa-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="575aa-116">Fermez toutes les fenêtres Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="575aa-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="575aa-117">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="575aa-117">Install the update.</span></span>

8.  <span data-ttu-id="575aa-118">Démarrez Lync Server Management Shell : Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="575aa-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="575aa-p104">Arrêtez de nouveau les services Lync Server pour rattraper les assemblys mis dans le Global Assembly Cache (GAC). À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="575aa-p104">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies. At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="575aa-p105">Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="575aa-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="575aa-123">Appliquez les modifications apportées par LyncServerUpdateInstaller.exe sur les bases de données SQL Server en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="575aa-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="575aa-124">S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de base de données colocalisée sur ce serveur, comme les bases de données d’archivage ou de surveillance, tapez ce qui suit dans la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="575aa-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="575aa-125">S’il s’agit d’un serveur principal Enterprise Edition et qu’il existe des bases de données colocalisées sur ce serveur, tapez ce qui suit dans la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="575aa-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="575aa-126">S’il s’agit d’un serveur Standard Edition, tapez ce qui suit dans la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="575aa-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

