---
title: 'Lync Server 2013 : vue d’ensemble du déploiement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d5fd5de9a72002d6ee8bd58ef5367b96634b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="7c335-102">Vue d’ensemble du déploiement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c335-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c335-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="7c335-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="7c335-104">La différence principale entre Lync Server 2013 Enterprise Edition et Lync Server 2013 Standard Edition réside dans le fait que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7c335-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="7c335-105">Pour la haute disponibilité, vous devez déployer plusieurs serveurs frontaux dans un pool, puis mettre en miroir le serveur exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c335-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="7c335-106">Avec Enterprise Edition, vous pouvez choisir de colocaliser ou de définir un serveur de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="7c335-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="7c335-107">Le serveur de surveillance et le serveur d’archivage peuvent utiliser un serveur autonome exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c335-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="7c335-108">Ou, les instances de SQL Server peuvent être exécutées sur le serveur de base de données pour les pools et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7c335-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="7c335-109">Les serveurs exécutant Lync Server 2013 Standard Edition sont conçus pour des organisations de plus petite taille et des emplacements distants, qui sont retirés géographiquement du déploiement principal de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="7c335-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="7c335-110">Deux serveurs Standard Edition Server réunis pour le basculement en cas de catastrophe peuvent prendre en charge jusqu’à 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7c335-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="7c335-111">Vous ne pouvez pas regrouper les serveurs Standard Edition comme vous pouvez les serveurs frontaux dans Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7c335-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="7c335-112">De plus, la base de données SQL Server utilisée par Standard Edition est un serveur colocalisé exécutant SQL Server Express qui est conçu pour gérer les charges de travail de serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7c335-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="7c335-113">Cela ne signifie pas que tous les rôles doivent résider sur un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7c335-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="7c335-114">Vous pouvez avoir des serveurs de médiation autonomes et des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="7c335-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="7c335-115">La base de données SQL Server pour le magasin central de gestion et pour les besoins de Lync Server 2013 doit résider sur le serveur Standard Edition colocalisé avec le serveur exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c335-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="7c335-116">Le serveur de surveillance et le serveur d’archivage utilisent un serveur autonome avec la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c335-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

