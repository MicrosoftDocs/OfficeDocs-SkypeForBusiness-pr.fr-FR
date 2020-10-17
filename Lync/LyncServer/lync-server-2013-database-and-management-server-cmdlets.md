---
title: 'Lync Server 2013 : cmdlets de serveur de base de données et de gestion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database and Management Server cmdlets
ms:assetid: b323bd59-8f71-4f03-af94-f3afb8620f4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415671(v=OCS.15)
ms:contentKeyID: 48185174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad071646faa5769abd6d741585eea33c31553c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516531"
---
# <a name="database-and-management-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f3d88-102">Cmdlets de serveur de base de données et de gestion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3d88-102">Database and Management Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3d88-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f3d88-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f3d88-104">Les cmdlets de serveur de base de données et de gestion sont utilisées pour gérer les bases de données principales de Microsoft Lync Server 2013 et vos services de gestion frontaux.</span><span class="sxs-lookup"><span data-stu-id="f3d88-104">The database and Management Server cmdlets are used to manage both your Microsoft Lync Server 2013 back-end databases and your front-end management services.</span></span> <span data-ttu-id="f3d88-105">Vous pouvez utiliser ces applets de commande pour installer ou désinstaller des bases de données utilisées par Lync Server 2013, en plus de la configuration du point de contrôle du service Active Directory pour le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="f3d88-105">You can use these cmdlets to install or uninstall any of the databases used by Lync Server 2013, in addition to configuring the Active Directory service control point for the Central Management store.</span></span>

<div>

## <a name="database-and-management-server-cmdlets"></a><span data-ttu-id="f3d88-106">Applets de commande de base de données et du serveur d’administration</span><span class="sxs-lookup"><span data-stu-id="f3d88-106">Database and Management Server Cmdlets</span></span>

<span data-ttu-id="f3d88-107">La liste suivante indique les applets de commande directement associées à la gestion des bases de données et au serveur d’administration :</span><span class="sxs-lookup"><span data-stu-id="f3d88-107">The following is a list of cmdlets that relate directly to managing databases and the Management Server:</span></span>

<span data-ttu-id="f3d88-108">**Bases de données et serveur d’administration**</span><span class="sxs-lookup"><span data-stu-id="f3d88-108">**Databases and Management Server**</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f3d88-112">[Install-applet csdatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-112">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-113">[Test-applet csdatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-113">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-114">[Uninstall-applet csdatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f3d88-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f3d88-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f3d88-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="f3d88-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f3d88-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f3d88-121">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-121">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f3d88-122">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-122">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f3d88-123">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-123">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f3d88-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3d88-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3d88-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3d88-125">See Also</span></span>


[<span data-ttu-id="f3d88-126">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3d88-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

