---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="1c845-102">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="1c845-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c845-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1c845-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1c845-104">Si vous avez déployé le serveur d’archivage et le serveur de surveillance sur votre serveur Office Communications Server 2007 R2, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après la migration de vos pools front-end.</span><span class="sxs-lookup"><span data-stu-id="1c845-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="1c845-105">En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’y ajouter l’archivage et la surveillance de votre pool de pilotes avant de procéder à la migration.</span><span class="sxs-lookup"><span data-stu-id="1c845-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="1c845-106">Si vous voulez utiliser les fonctionnalités d’archivage et de surveillance pendant la phase de migration et de coexistence, gardez à l’esprit les points suivants :</span><span class="sxs-lookup"><span data-stu-id="1c845-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="1c845-107">L’archivage de données et le contrôle des données ne sont pas déplacés vers le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c845-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="1c845-108">Les données que vous sauvegardez avant de désactiver l’environnement hérité seront votre historique d’activités dans Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1c845-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="1c845-109">La version R2 d’Office Communications Server 2007 R2 du serveur d’archivage et de surveillance Server peut être associée uniquement à un pool frontal d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1c845-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="1c845-110">Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles de serveur, mais les services intégrés au pool de serveurs front end 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c845-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="1c845-111">Pendant la période de coexistence des déploiements d’anciens et de Lync Server 2013, la version R2 d’Office Communications Server 2007 R2 du serveur d’archivage et de la surveillance du serveur collecte des données pour les utilisateurs hébergés sur des pools Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1c845-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="1c845-112">La version 2013 de Lync Server du serveur d’archivage et de surveillance du serveur de surveillance collecte des données pour les utilisateurs hébergés sur les pools 2013 du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="1c845-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c845-113">Pendant la phase de migration lorsque vous utilisez toujours votre serveur de périphérie antérieur avec le nouveau pool de pilotes Lync Server 2013, la version R2 d’Office Communications Server 2007 R2 du serveur d’archivage continue de rassembler les données pour les utilisateurs hébergés sur Office Communications Server 2007 Les pools R2 et la version 2013 du serveur d’archivage de Lync Server regroupent les données des utilisateurs hébergés sur les pools 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c845-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="1c845-114">Si vous utilisez une solution tierce d’archivage et de surveillance conjointement avec le serveur d’archivage et le serveur de surveillance, contactez votre revendeur sur le moment et la façon dont vous devez intégrer la solution tierce à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c845-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

