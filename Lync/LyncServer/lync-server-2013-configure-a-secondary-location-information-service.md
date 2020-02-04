---
title: 'Lync Server 2013 : configurer un service d’information d’emplacement secondaire'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="fae84-102">Configurer un service d’information d’emplacement secondaire dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae84-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae84-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="fae84-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="fae84-104">Lync Server 2013 fournit une interface de service Web que vous pouvez utiliser pour faire pointer le service d’information d’emplacement vers une base de données de source d’emplacement secondaire (SLS).</span><span class="sxs-lookup"><span data-stu-id="fae84-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="fae84-105">L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL.</span><span class="sxs-lookup"><span data-stu-id="fae84-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="fae84-106">S’il s’agit d’une base de données d’emplacement et d’une base de données d’emplacement secondaire configurées, le service des informations d’emplacement interroge d’abord la base de données de localisation, et si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client vers la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="fae84-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="fae84-107">Si l’emplacement existe dans le dossier SLS, le service d’information sur l’emplacement est alors renvoyé à l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="fae84-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="fae84-108">Pour plus d’informations, consultez la documentation de Lync Server Management Shell pour l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fae84-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="fae84-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="fae84-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="fae84-110">Pour configurer la base de données de l’emplacement secondaire</span><span class="sxs-lookup"><span data-stu-id="fae84-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="fae84-111">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fae84-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fae84-112">Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="fae84-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

