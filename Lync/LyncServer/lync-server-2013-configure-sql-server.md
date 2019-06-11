---
title: 'Lync Server 2013 : Configuration de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da3cea6019b6314eccb2968f9b05ef44e7de75e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="01c1a-102">Configuration de SQL Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01c1a-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01c1a-103">_**Dernière modification de la rubrique:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="01c1a-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="01c1a-104">Pour chaque base de données que vous déployez, vous pouvez utiliser une instance SQL Server unique pour toutes les bases de données pour votre déploiement Lync Server 2013 qui peut être colocalisé sur un serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="01c1a-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="01c1a-105">Pour plus d’informations sur la colocalisation de la base de données, consultez [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md)</span><span class="sxs-lookup"><span data-stu-id="01c1a-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="01c1a-106">Par ailleurs, chaque instance SQL Server doit être installée et disponible avant d’exécuter les étapes du générateur de topologie qui configurent les bases de données ou de créer manuellement les bases de données avec des cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01c1a-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="01c1a-107">Pour plus d’informations sur la prise en charge de SQL Server, voir [Configuration matérielle pour Lync Server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="01c1a-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="01c1a-108">Pour installer Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="01c1a-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="01c1a-109">Pour plus d’informations, consultez la documentation Microsoft <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>SQL Server 2012 à l’adresse suivante:.</span><span class="sxs-lookup"><span data-stu-id="01c1a-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

