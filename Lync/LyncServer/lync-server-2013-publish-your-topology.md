---
title: 'Lync Server 2013 : Publication de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="23813-102">Publication de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23813-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23813-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="23813-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="23813-104">Chaque fois que vous utilisez le générateur de topologie pour générer votre topologie, vous devez publier la topologie sur une base de données dans la Banque centrale de gestion pour que les données puissent être utilisées pour le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23813-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="23813-105">Utilisez la procédure suivante pour publier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="23813-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="23813-106">Pour publier la topologie</span><span class="sxs-lookup"><span data-stu-id="23813-106">To publish the topology</span></span>

1.  <span data-ttu-id="23813-107">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23813-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="23813-108">Dans le générateur de topologie, dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync 2013**, puis cliquez sur **topologie de publication**.</span><span class="sxs-lookup"><span data-stu-id="23813-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="23813-109">Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="23813-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="23813-110">Dans le **Générateur de topologie a détecté une page CMS Store** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="23813-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="23813-111">Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="23813-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="23813-112">Lorsque l’état indique la création réussie de la base de données, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="23813-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="23813-113">Pour afficher le journal, cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="23813-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="23813-114">Pour fermer l’Assistant, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="23813-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="23813-115">S’il s’agit d’une nouvelle installation d’un serveur de périphérie ou d’un pool de périphériques, vous devez exporter la configuration de serveur Edge à partir d’un serveur frontal, d’un pool frontal ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="23813-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="23813-116">Pour exporter la configuration, reportez-vous à la section <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export de votre topologie Lync Server 2013 et copiez-la sur du média externe pour l’installation Edge</A>.</span><span class="sxs-lookup"><span data-stu-id="23813-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="23813-117">Dans le cadre de l’installation et du déploiement, vous allez importer le fichier de configuration à partir du média externe ou du partage réseau via l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23813-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="23813-118">Une fois les serveurs Edge opérationnels et la base de données du magasin de gestion des configurations locales répliquant le déploiement interne, les mises à jour ultérieures apportées à la configuration de Lync Server 2013 seront publiées et répliquées sur les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="23813-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

