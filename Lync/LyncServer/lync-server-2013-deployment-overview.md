---
title: 'Lync Server 2013 : Vue d’ensemble du déploiement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="cb245-102">Vue d’ensemble du déploiement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb245-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb245-103">_**Dernière modification de la rubrique:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="cb245-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="cb245-104">La principale différence entre Lync Server 2013 Enterprise Edition et Lync Server 2013 Standard Edition est que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans l’édition Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb245-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="cb245-105">Pour une disponibilité élevée, vous devez déployer plusieurs serveurs frontaux vers un pool, puis vous pouvez mettre en miroir le serveur exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb245-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="cb245-106">Avec Enterprise Edition, vous pouvez choisir de collocate ou de définir un serveur de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="cb245-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="cb245-107">Le serveur de surveillance et l’archivage serveur peuvent utiliser un serveur autonome exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb245-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="cb245-108">Des instances de SQL Server peuvent être exécutées sur le serveur de base de données pour les serveurs frontaux et les pools.</span><span class="sxs-lookup"><span data-stu-id="cb245-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="cb245-109">Les serveurs exécutant Lync Server 2013 Standard Edition sont destinés aux organisations plus petites et aux emplacements distants, qui sont retirés géographiquement du déploiement principal de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cb245-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="cb245-110">Deux serveurs Standard Edition Server associés à une reprise en cas de sinistre peuvent prendre en charge jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cb245-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="cb245-111">Vous ne pouvez pas mettre en réserve les serveurs Standard Edition tels que vous pouvez disposer de serveurs frontaux dans l’édition Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb245-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="cb245-112">Par ailleurs, la base de données SQL Server utilisée par Standard Edition est un serveur colocalisé exécutant SQL Server Express conçu pour gérer les charges de travail des serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cb245-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="cb245-113">Ce n’est pas dire que tous les rôles doivent résider sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cb245-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="cb245-114">Vous pouvez disposer de serveurs de médiation autonomes et de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cb245-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="cb245-115">La base de données SQL Server du magasin de gestion central et aux fins de Lync Server 2013 doit résider sur un serveur Standard Edition Server en tant que serveur exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb245-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="cb245-116">Le serveur de surveillance et le serveur d’archivage utilisent un serveur autonome avec la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb245-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

