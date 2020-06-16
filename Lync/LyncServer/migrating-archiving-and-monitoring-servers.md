---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba86de15ea86844b677db1abb0f47f7e1995c7e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="a4a1a-102">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="a4a1a-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4a1a-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a4a1a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a4a1a-104">Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement Lync Server 2010, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après avoir migré vos pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="a4a1a-105">Toutefois, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool de pilotes Lync Server 2013 avant de procéder à la migration afin que la fonctionnalité soit disponible pendant le processus de migration.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="a4a1a-106">Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="a4a1a-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="a4a1a-107">Les données d’archivage et les données de surveillance ne sont pas déplacées vers le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a4a1a-108">Les données que vous sauvegardez avant de désaffecter l’environnement hérité correspondent à votre historique d’activité dans l’environnement Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="a4a1a-109">La version Lync Server 2010 du serveur d’archivage et du serveur de surveillance ne peut être associée qu’à un pool frontal Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="a4a1a-110">Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="a4a1a-111">Pendant la coexistence de vos déploiements hérités et Lync Server 2013, la version Lync Server 2010 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="a4a1a-112">L’archivage et la surveillance dans Lync Server 2013 recueillent des données pour les utilisateurs hébergés sur des pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4a1a-113">Pendant la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Lync Server 2010 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur Lync Server 2010 pools et archivage dans Lync Server 2013 recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="a4a1a-114">Si vous utilisez une solution d’archivage et de surveillance tierce en association avec l’archivage et la surveillance dans Lync Server 2013, consultez votre fournisseur quand et comment intégrer la solution tierce à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a1a-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

