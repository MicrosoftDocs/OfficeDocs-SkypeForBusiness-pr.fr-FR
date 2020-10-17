---
title: 'Lync Server 2013 : configurer SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2bdac9841e908910697068460a6b7e42075e7e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535111"
---
# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="7fe76-102">Configurer SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe76-102">Configure SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe76-103">_**Dernière modification de la rubrique :** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="7fe76-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="7fe76-104">Pour chaque base de données que vous déployez, vous pouvez utiliser une seule instance SQL Server pour toutes les bases de données de votre déploiement Lync Server 2013 qui peuvent être colocalisées sur un serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="7fe76-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="7fe76-105">Pour plus d’informations sur la colocalisation des bases de données, voir [Supported Server colocalisation in Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7fe76-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="7fe76-106">En outre, chaque instance SQL Server doit être installée et disponible avant d’effectuer les étapes dans le générateur de topologies qui configurent les bases de données ou de créer manuellement les bases de données avec des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fe76-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7fe76-107">Pour plus d’informations sur la prise en charge de SQL Server, consultez la rubrique [Hardware Setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7fe76-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="7fe76-108">Pour installer Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="7fe76-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="7fe76-109">Consultez la documentation de Microsoft SQL Server 2012 à l’adresse suivante : <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx> .</span><span class="sxs-lookup"><span data-stu-id="7fe76-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

