---
title: 'Lync Server 2013 : configuration des plateformes système pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac0a0e39a65b32b42398aab832e7010573534807
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497551"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="12a5b-102">Configuration des plateformes système pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12a5b-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12a5b-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="12a5b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="12a5b-104">Avant de commencer à déployer l’archivage, vous devez installer le système d’exploitation requis et tout autre logiciel prérequis sur du matériel conforme à la configuration requise :</span><span class="sxs-lookup"><span data-stu-id="12a5b-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="12a5b-105">Plateforme Lync Server **2013**     Les déploiements Lync Server 2013 n’ont pas de serveurs d’archivage.</span><span class="sxs-lookup"><span data-stu-id="12a5b-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="12a5b-106">Aucune plateforme système séparée n’est donc nécessaire pour héberger l’archivage.</span><span class="sxs-lookup"><span data-stu-id="12a5b-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="12a5b-107">Plateforme de stockage de **données**     Dans Lync Server 2013, vous pouvez stocker des données à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="12a5b-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="12a5b-108">Intégration de Microsoft **Exchange**     Si vous souhaitez stocker les données d’archivage Lync Server 2013 à l’aide de votre déploiement Exchange 2013, au lieu de configurer une base de données distincte pour le stockage des données d’archivage, votre déploiement Exchange doit exécuter Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12a5b-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="12a5b-109">Pour plus d’informations sur la configuration des plateformes système pour Exchange 2013, voir la documentation du produit Exchange.</span><span class="sxs-lookup"><span data-stu-id="12a5b-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="12a5b-110">**SQL Server**     Si vous souhaitez utiliser une base de données SQL Server distincte pour le stockage des données d’archivage, au lieu ou en plus de l’utilisation de l’intégration de Microsoft Exchange, vous devez configurer la plateforme système pour la base de données avant le déploiement de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="12a5b-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="12a5b-111">La configuration requise de la plateforme système varie selon que vous utilisez Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="12a5b-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="12a5b-112">Pour plus d’informations sur la configuration des plateformes système pour ces bases de données, reportez-vous à la documentation du produit Microsoft SQL Server 2008 R2 et Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="12a5b-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="12a5b-113">Plateforme de serveur de **fichiers**     Lync Server 2013 stocke les fichiers d’archivage Lync Server dans le même emplacement que celui que vous spécifiez pour le stockage des fichiers lorsque vous configurez vos serveurs frontaux ou serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12a5b-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="12a5b-114">Vous ne pouvez pas spécifier d’emplacement séparé pour le stockage des fichiers d’archivage, aucune plateforme système séparée n’est donc nécessaire.</span><span class="sxs-lookup"><span data-stu-id="12a5b-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="12a5b-115">Si vous utilisez l’intégration de Microsoft Exchange, Exchange 2013 les fichiers pour les communications Lync archivées sont stockés sur les serveurs Exchange 2013 pour les utilisateurs hébergés sur ces serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="12a5b-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

