---
title: 'Lync Server 2013 : configuration requise pour le serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cedee-102">Configuration requise pour le serveur de chat permanent dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cedee-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cedee-103">_**Dernière modification de la rubrique :** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="cedee-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="cedee-104">Chaque ordinateur qui héberge le serveur Chat permanent doit avoir accès à une topologie Lync Server 2013 existante avec les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="cedee-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="cedee-105">**Serveur frontal Lync Server 2013.**  Le serveur frontal est le serveur principal pour le routage SIP (Session Initiation Protocol), qui permet de communiquer entre les ordinateurs exécutant le serveur Chat permanent et la fonctionnalité de conversation permanente possible.</span><span class="sxs-lookup"><span data-stu-id="cedee-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="cedee-106">Avant de commencer à déployer le serveur de chat permanent, vérifiez le déploiement de Lync Server 2013 Standard Edition ou d’un pool frontal Lync Server et de tout autre ordinateur interne exécutant Lync Server, selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cedee-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="cedee-107">Les sections suivantes décrivent les conditions requises pour le serveur de chat permanent et la base de données qui stocke les données de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="cedee-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="cedee-108">Configuration requise pour le serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="cedee-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="cedee-109">Pour plus d’informations sur le matériel recommandé pour le déploiement de Lync Server et la dernière version de Chat Server, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de support.</span><span class="sxs-lookup"><span data-stu-id="cedee-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cedee-110">Pour plus d’informations sur la prise en charge des systèmes d’exploitation serveur et outils pour Lync Server et serveur de chat permanent, voir [prise en charge du système d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de support technique.</span><span class="sxs-lookup"><span data-stu-id="cedee-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cedee-111">Pour plus d’informations sur les logiciels supplémentaires requis pour le déploiement d’un serveur de chat permanent, voir le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="cedee-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="cedee-112">Conditions préalables pour le logiciel serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="cedee-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cedee-113">Logiciels</span><span class="sxs-lookup"><span data-stu-id="cedee-113">Software</span></span></th>
<th><span data-ttu-id="cedee-114">Description</span><span class="sxs-lookup"><span data-stu-id="cedee-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cedee-115">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="cedee-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="cedee-116">Utilisé par le serveur de chat permanent et le service de conformité des conversations permanentes, s’il est déployé.</span><span class="sxs-lookup"><span data-stu-id="cedee-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="cedee-117">Exigences de base de données serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="cedee-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="cedee-118">Le serveur Chat permanent utilise la base de données de chat permanent pour stocker les données de l’historique des conversations, de la configuration et de la mise en service des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cedee-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="cedee-119">Le cas échéant, elle utilise la base de données de conformité des conversations permanentes pour stocker les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="cedee-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cedee-120">La base de données de chat permanent (MGC) et la base de données de conformité (mgccomp) peuvent être localisées dans la même instance de SQL Server ou sur des serveurs SQL Server différents.</span><span class="sxs-lookup"><span data-stu-id="cedee-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="cedee-121">Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis.</span><span class="sxs-lookup"><span data-stu-id="cedee-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="cedee-122">La plateforme serveur pour les serveurs de base de données de chat permanent nécessite le même matériel que le serveur de base de données principal de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cedee-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="cedee-123">Pour plus d’informations, reportez-vous à la rubrique [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de support.</span><span class="sxs-lookup"><span data-stu-id="cedee-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cedee-124">Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :</span><span class="sxs-lookup"><span data-stu-id="cedee-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="cedee-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="cedee-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="cedee-126">Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir installer SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span><span class="sxs-lookup"><span data-stu-id="cedee-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="cedee-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="cedee-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="cedee-128">Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, voir « installation de SQL Server (SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)) » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cedee-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="cedee-129">Conditions requises pour le certificat serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="cedee-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="cedee-130">Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cedee-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

