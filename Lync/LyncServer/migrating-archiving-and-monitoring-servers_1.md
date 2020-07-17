---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="48733-102">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="48733-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48733-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="48733-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="48733-104">Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre Office Communications Server 2007 R2, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après avoir migré vos pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="48733-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="48733-105">Toutefois, si les fonctionnalités d’archivage et de surveillance sont critiques pour votre organisation, nous vous recommandons d’ajouter l’archivage et la surveillance à votre pool pilote avant la migration pour que la fonctionnalité soit disponible pendant le processus de migration.</span><span class="sxs-lookup"><span data-stu-id="48733-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="48733-106">Si vous voulez que les fonctionnalités d’archivage et de surveillance soient disponibles au cours de la phase de migration et de coexistence, gardez les éléments suivants à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="48733-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="48733-107">Les données d’archivage et les données de surveillance ne sont pas déplacées vers le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48733-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="48733-108">Les données que vous sauvegardez avant la mise hors service de l’environnement hérité seront votre historique des activités dans Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="48733-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="48733-109">La version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance ne peut être associée qu’à un pool frontal Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="48733-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="48733-110">Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48733-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="48733-111">Pendant la coexistence de vos déploiements hérités et Lync Server 2013, la version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="48733-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="48733-112">La version Lync Server 2013 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48733-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48733-113">Pendant la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Office Communications Server 2007 R2 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur des pools Lync Server 2007 et la version Lync Server 2013 du serveur d’archivage recueille des données pour les utilisateurs hébergés sur les pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48733-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="48733-114">Si vous utilisez une solution d’archivage et de surveillance tierce en association avec le serveur d’archivage et le serveur de surveillance, demandez à votre fournisseur quand et comment vous devez intégrer la solution tierce à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48733-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

