---
title: Exportation de votre topologie et copie vers le support externe pour l’installation Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dd461e6a8ce184e5e418feddede258af68d2c25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528371"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="b2a45-102">Exportation de votre topologie Lync Server 2013 et copie vers le support externe pour l’installation Edge</span><span class="sxs-lookup"><span data-stu-id="b2a45-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2a45-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b2a45-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b2a45-104">Une fois que vous avez publié votre topologie, l’Assistant Déploiement de Lync Server a besoin d’accéder aux données du magasin central de gestion afin de démarrer le processus de déploiement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b2a45-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="b2a45-105">Dans le réseau interne, les données sont disponibles directement depuis les serveurs, mais les serveurs Edge ne figurant pas dans le domaine interne ne peuvent pas accéder à ces informations.</span><span class="sxs-lookup"><span data-stu-id="b2a45-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="b2a45-106">Pour que les données de configuration de topologie soient disponibles pour un déploiement de serveur Edge, vous devez exporter les données de topologie vers un fichier et les copier sur un support externe (par exemple, un lecteur USB ou un partage réseau disponible à partir du serveur Edge) avant d’exécuter l’Assistant Déploiement de Lync Server sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b2a45-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="b2a45-107">Utilisez la procédure suivante pour rendre vos données de configuration de topologie accessibles au serveur Edge que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="b2a45-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b2a45-108">Une fois que vous avez installé Lync Server 2013 sur un serveur Edge, vous devez gérer le serveur Edge à l’aide des outils d’administration du réseau interne, qui répliquent automatiquement les serveurs de périphérie de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="b2a45-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="b2a45-109">Les seules exceptions concernent l’attribution et l’installation de certificats, ainsi que l’arrêt et le démarrage des services, qui doivent tous deux être effectués sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b2a45-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="b2a45-110">Pour rendre vos données de topologie accessibles sur un serveur Edge à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b2a45-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="b2a45-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b2a45-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b2a45-112">Dans Lync Server Management Shell, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2a45-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="b2a45-113">Copiez le fichier exporté sur un support externe (par exemple, une clé USB ou un partage réseau disponible depuis le serveur Edge lors du déploiement).</span><span class="sxs-lookup"><span data-stu-id="b2a45-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

