---
title: Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37cfbf02d379a3003338d4eabc7a5ca3c4b49f15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498691"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="43bb1-102">Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43bb1-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43bb1-103">_**Dernière modification de la rubrique :** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="43bb1-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="43bb1-104">Une fois que vous avez configuré l’infrastructure système et le matériel, vous devez installer les systèmes d’exploitation Windows appropriés et leurs mises à jour, ainsi que les logiciels supplémentaires prérequis sur chaque serveur que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="43bb1-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="43bb1-105">Cela inclut chaque rôle serveur Lync Server 2013 et tous les serveurs ou serveurs d’infrastructure supplémentaires exécutant SQL Server qui sont requis pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="43bb1-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="43bb1-106">Cette section décrit l’installation des systèmes d’exploitation et des logiciels prérequis pour les serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="43bb1-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="43bb1-107">Si vous déployez des serveurs Edge pour prendre en charge l’accès des utilisateurs externes, vous devez également installer les systèmes d’exploitation et les logiciels prérequis pour ces serveurs, y compris les serveurs Edge et les serveurs proxy inverses.</span><span class="sxs-lookup"><span data-stu-id="43bb1-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="43bb1-108">Pour plus d’informations sur la préparation des serveurs en vue de la prise en charge de l’accès des utilisateurs externes, voir <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the périmètre Network for Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="43bb1-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="43bb1-109">Installer les systèmes d’exploitation Windows sur les serveurs</span><span class="sxs-lookup"><span data-stu-id="43bb1-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="43bb1-110">Sur chaque serveur que vous déployez, installez le système d’exploitation Windows approprié comme suit :</span><span class="sxs-lookup"><span data-stu-id="43bb1-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="43bb1-111">**Serveurs exécutant Lync Server 2013**     Pour plus d’informations sur la configuration requise du système d’exploitation pour les serveurs exécutant Lync Server 2013, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="43bb1-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="43bb1-112">Serveurs de bases **de données**     Pour plus d’informations sur la configuration requise du système d’exploitation pour les serveurs de bases de données, y compris la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43bb1-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="43bb1-113">Pour SQL Server 2012, reportez-vous à la documentation en ligne de SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43bb1-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="43bb1-114">Si vous installez Lync Server 2013 sur Windows Server &nbsp; 2008 &nbsp; R2 avec SP1, vous devez d’abord installer la mise à jour décrite dans l’article 2646886 de la base de connaissances Microsoft « correctif : corruption de tas survient lorsqu’un module appelle la méthode INSERTENTITYBODY dans IIS 7,5 », at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="43bb1-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="43bb1-115">Vous devez également modifier le registre, comme décrit dans l’article de la base de connaissances, les <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">ID d’événement 32402, 61045 sont consignés dans les serveurs frontaux Lync Server 2013 installés dans Windows Server 2012 R2</A>.</span><span class="sxs-lookup"><span data-stu-id="43bb1-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="43bb1-116">Installer la mise à jour de Windows sur les serveurs</span><span class="sxs-lookup"><span data-stu-id="43bb1-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="43bb1-117">Installez les mises à jour suivantes à partir de Windows Update sur chaque serveur :</span><span class="sxs-lookup"><span data-stu-id="43bb1-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="43bb1-118">**Mise à jour Windows pour les serveurs exécutant Lync Server 2013**     Pour plus d’informations sur les mises à jour de Windows Update requises pour les serveurs Lync Server 2013, reportez-vous à la rubrique [autres logiciels requis pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="43bb1-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="43bb1-119">Serveurs de bases **de données**     Pour plus d’informations sur les mises à jour de Windows Update requises pour les serveurs de bases de données, notamment la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="43bb1-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="43bb1-120">Pour SQL Server 2012, reportez-vous à la documentation en ligne de SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43bb1-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="43bb1-121">Installer les autres logiciels prérequis sur les serveurs</span><span class="sxs-lookup"><span data-stu-id="43bb1-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="43bb1-122">Lync Server 2013 nécessite l’installation des logiciels supplémentaires suivants sur les serveurs :</span><span class="sxs-lookup"><span data-stu-id="43bb1-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="43bb1-123">**Logiciels prérequis pour les serveurs exécutant Lync Server 2013**     Les logiciels supplémentaires requis pour les serveurs exécutant Lync Server 2013 dépendent du rôle serveur en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="43bb1-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="43bb1-124">Pour plus d’informations sur la configuration logicielle requise pour chaque serveur, voir la rubrique relative à la [configuration logicielle requise pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="43bb1-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="43bb1-125">**Windows Identity Foundation**     Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="43bb1-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="43bb1-126">Pour vérifier qu’elle a déjà été installée sur votre ordinateur, accédez au panneau de configuration, cliquez sur **programmes et fonctionnalités**, **afficher les mises à jour installées**et Regardez sous **Microsoft Windows**.</span><span class="sxs-lookup"><span data-stu-id="43bb1-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="43bb1-127">Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="43bb1-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="43bb1-128">**Microsoft .NET Framework 4,5**     L’édition 64 bits de Microsoft .NET Framework 4,5 est requise pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43bb1-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="43bb1-129">**Logiciels prérequis pour les serveurs**     de bases de données Pour plus d’informations sur la mise à jour Windows requise pour les serveurs de bases de données, y compris la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server 2012 à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43bb1-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43bb1-130">Lync Server 2013 installe automatiquement Microsoft SQL Server 2012 Express sur chaque serveur Standard Edition et chaque serveur exécutant Lync Server 2013 sur lequel se trouve le magasin de configurations local.</span><span class="sxs-lookup"><span data-stu-id="43bb1-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="43bb1-131">Exécution du format **Windows Media**     Le runtime de format Windows Media doit être installé sur tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences seront déployées.</span><span class="sxs-lookup"><span data-stu-id="43bb1-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="43bb1-132">Le module d’exécution du format Windows Media est nécessaire pour exécuter les fichiers audio Windows Media (.wma) qui sont lus pour les annonces et la musique par les applications de parcage d’appel, d’annonce et Response Group.</span><span class="sxs-lookup"><span data-stu-id="43bb1-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43bb1-133">Pour Windows Server 2012 et Windows Server 2012 R2, le runtime du format Windows Media s’installe avec Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="43bb1-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43bb1-134">Pour Windows Server &nbsp; 2008 et Windows server &nbsp; 2008 &nbsp; R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="43bb1-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="43bb1-135">Il est recommandé d’installer expérience Bureau Windows avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43bb1-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="43bb1-136">Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, il vous invite à l’installer, puis vous devez redémarrer le serveur pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="43bb1-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

