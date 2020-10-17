---
title: 'Lync Server 2013 : configuration technique requise pour le serveur de conversation permanente'
description: 'Lync Server 2013 : configuration technique requise pour le serveur de conversation permanente.'
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
ms.openlocfilehash: 905563f31de36d41a48aea5fb8db3cfde9cb2434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550330"
---
# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="fd45d-103">Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd45d-103">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd45d-104">_**Dernière modification de la rubrique :** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="fd45d-104">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="fd45d-105">Chaque ordinateur qui héberge le serveur de conversation permanente doit avoir accès à une topologie Lync Server 2013 existante avec les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="fd45d-105">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="fd45d-106">**Lync server 2013, serveur frontal.**   Le serveur frontal est la base du routage SIP (Session Initiation Protocol), qui rend possible la communication entre les ordinateurs exécutant le serveur de conversation permanente et la fonctionnalité de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="fd45d-106">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="fd45d-107">Avant de commencer à déployer le serveur de conversation permanente, vérifiez le déploiement de Lync Server 2013, Standard Edition ou d’un pool frontal Lync Server et de tous les autres ordinateurs internes exécutant Lync Server, selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fd45d-107">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="fd45d-108">Les sections suivantes décrivent les conditions requises spécifiques pour le serveur de conversation permanente et la base de données qui stocke les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="fd45d-108">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="fd45d-109">Configuration requise pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fd45d-109">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="fd45d-110">Pour plus d’informations sur le matériel recommandé pour le déploiement de Lync Server et la dernière version du serveur de conversation permanente, voir [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fd45d-110">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="fd45d-111">Pour plus d’informations sur le serveur et les outils pris en charge par le système d’exploitation pour Lync Server et le serveur de conversation permanente, voir [serveur et outils pris en charge dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fd45d-111">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="fd45d-112">Pour plus d’informations sur les logiciels supplémentaires requis pour le déploiement du serveur de conversation permanente, consultez le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fd45d-112">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="fd45d-113">Configuration logicielle requise pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fd45d-113">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd45d-114">Logiciels</span><span class="sxs-lookup"><span data-stu-id="fd45d-114">Software</span></span></th>
<th><span data-ttu-id="fd45d-115">Description</span><span class="sxs-lookup"><span data-stu-id="fd45d-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd45d-116">Message Queuing</span><span class="sxs-lookup"><span data-stu-id="fd45d-116">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="fd45d-117">Utilisé par le serveur de conversation permanente et le service de conformité de conversation permanente, s’il est déployé.</span><span class="sxs-lookup"><span data-stu-id="fd45d-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="fd45d-118">Configuration requise pour la base de données de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fd45d-118">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="fd45d-119">Le serveur de conversation permanente utilise la base de données de conversation permanente pour stocker les données d’historique, de configuration et de mise en service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd45d-119">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="fd45d-120">Il utilise éventuellement la base de données de conformité de la conversation permanente pour stocker les données de conformité.</span><span class="sxs-lookup"><span data-stu-id="fd45d-120">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd45d-121">La base de données de conversation permanente (MGC) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur des serveurs SQL différents.</span><span class="sxs-lookup"><span data-stu-id="fd45d-121">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="fd45d-122">Pour préparer une plateforme de serveur de base de données, assurez-vous que chaque ordinateur répond à la configuration matérielle requise, puis installez les logiciels prérequis.</span><span class="sxs-lookup"><span data-stu-id="fd45d-122">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="fd45d-123">La plateforme de serveur pour les serveurs de bases de données de conversation permanente nécessite le même matériel que le serveur de base de données principal Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd45d-123">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="fd45d-124">Pour plus d’informations, reportez-vous à la rubrique [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fd45d-124">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="fd45d-125">Sur le serveur de base de données, assurez-vous que l’une des applications logicielles suivantes est installée :</span><span class="sxs-lookup"><span data-stu-id="fd45d-125">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="fd45d-126">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fd45d-126">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="fd45d-127">Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir « installer SQL Server 2012 » à l’adresse suivante [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559) :.</span><span class="sxs-lookup"><span data-stu-id="fd45d-127">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="fd45d-128">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fd45d-128">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="fd45d-129">Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, voir « installation de SQL Server (SQL Server 2008 R2) » à l’adresse [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702) .</span><span class="sxs-lookup"><span data-stu-id="fd45d-129">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="fd45d-130">Conditions requises pour les certificats de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fd45d-130">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="fd45d-131">Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fd45d-131">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

