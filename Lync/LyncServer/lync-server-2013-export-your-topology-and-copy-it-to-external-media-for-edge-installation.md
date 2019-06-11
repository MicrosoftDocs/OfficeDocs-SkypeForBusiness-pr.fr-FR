---
title: Exportation de la topologie et copie vers le support externe de l’installation Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdd947287ec5b7fef90d27df6df2dd256481000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="36f16-102">Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge</span><span class="sxs-lookup"><span data-stu-id="36f16-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36f16-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="36f16-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="36f16-104">Après avoir publié votre topologie, l’Assistant Déploiement de Lync Server a besoin d’accéder aux données du magasin central de gestion pour démarrer le processus de déploiement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="36f16-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="36f16-105">Dans le réseau interne, les données sont disponibles directement à partir des serveurs, mais les serveurs Edge qui ne se trouvent pas dans le domaine interne ne peuvent pas accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="36f16-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="36f16-106">Pour que les données de la configuration topologique soient disponibles pour le déploiement d’un serveur de périphérie, vous devez exporter les données de topologie vers un fichier et les copier sur un média externe (par exemple, un lecteur USB ou un partage réseau disponible à partir du serveur Edge) avant d’exécuter Lync Server DEP. Assistant loyment sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="36f16-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="36f16-107">Suivez la procédure ci-dessous pour rendre vos données de configuration topologique disponibles sur le serveur Edge que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="36f16-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="36f16-108">Après l’installation de Lync Server 2013 sur un serveur Edge, vous gérez le serveur Edge à l’aide des outils d’administration du réseau interne, qui répliquent automatiquement la configuration sur les serveurs de périphérie de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="36f16-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="36f16-109">La seule exception est d’affecter et d’installer des certificats, et d’arrêter et de démarrer des services, qui doivent être effectuées sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="36f16-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="36f16-110">Pour rendre vos données de topologie disponibles sur un serveur Edge à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="36f16-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="36f16-111">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="36f16-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="36f16-112">Dans Lync Server Management Shell, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="36f16-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="36f16-113">Copiez le fichier exporté sur le média externe (par exemple, un lecteur USB ou un partage réseau accessible à partir du serveur Edge lors du déploiement).</span><span class="sxs-lookup"><span data-stu-id="36f16-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

