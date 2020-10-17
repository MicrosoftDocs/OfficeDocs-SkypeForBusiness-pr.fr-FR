---
title: 'Lync Server 2013 : publication de votre topologie'
description: 'Lync Server 2013 : Publiez votre topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571750"
---
# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="57207-103">Publier votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57207-103">Publish your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57207-104">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="57207-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="57207-105">Chaque fois que vous utilisez le générateur de topologies pour créer votre topologie, vous devez publier la topologie dans une base de données du magasin central de gestion afin que les données puissent être utilisées pour déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57207-105">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="57207-106">Procédez comme suit pour publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="57207-106">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="57207-107">Pour publier la topologie</span><span class="sxs-lookup"><span data-stu-id="57207-107">To publish the topology</span></span>

1.  <span data-ttu-id="57207-108">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="57207-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="57207-109">Dans le générateur de topologies, dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync 2013**, puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="57207-109">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="57207-110">Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="57207-110">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="57207-111">Dans la page **Le Générateur de topologie a trouvé un magasin central de gestion**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="57207-111">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="57207-112">Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="57207-112">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="57207-113">Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57207-113">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="57207-114">Pour afficher le journal, cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="57207-114">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="57207-115">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="57207-115">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="57207-116">S’il s’agit d’une nouvelle installation d’un serveur Edge ou d’un pool de serveurs Edge, vous devez exporter la configuration du serveur Edge à partir d’un serveur frontal existant, d’un pool frontal ou d’un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="57207-116">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="57207-117">Pour exporter la configuration, reportez-vous à la rubrique <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export Your Lync Server 2013 Topology et copy it to External Media for Edge installation</A>.</span><span class="sxs-lookup"><span data-stu-id="57207-117">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="57207-118">Vous allez importer le fichier de configuration à partir du média externe ou du partage réseau pendant la phase de configuration et de déploiement des serveurs Edge via l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57207-118">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="57207-119">Une fois que les serveurs Edge sont opérationnels et que la base de données de magasin de gestion de la configuration locale est répliquée avec le déploiement interne, les mises à jour suivantes de la configuration Lync Server 2013 seront publiées et répliquées sur les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="57207-119">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

