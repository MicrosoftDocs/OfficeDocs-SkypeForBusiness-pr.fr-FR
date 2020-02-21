---
title: 'Lync Server 2013 : configuration d’un service d’informations d’emplacement secondaire'
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
ms.openlocfilehash: 0a13e99aa7f9e3da9ddd04f5c8e7763c7de1481a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="303f3-102">Configurer un service d’informations d’emplacement secondaire dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="303f3-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="303f3-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="303f3-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="303f3-104">Lync Server 2013 fournit une interface de service Web que vous pouvez utiliser pour pointer le service informations d’emplacement vers une base de données de source d’emplacement secondaire.</span><span class="sxs-lookup"><span data-stu-id="303f3-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="303f3-105">L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL du service informations sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="303f3-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="303f3-106">Si une base de données d’emplacements et une base de données d’emplacements secondaires sont configurées, le service d’informations d’emplacement interroge d’abord la base de données d’emplacements et, si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client à la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="303f3-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="303f3-107">Si l’emplacement existe dans le contrat SLS, le service d’informations sur l’emplacement renvoie l’emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="303f3-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="303f3-108">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="303f3-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="303f3-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="303f3-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="303f3-110">Pour configurer la base de données d’emplacements secondaires</span><span class="sxs-lookup"><span data-stu-id="303f3-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="303f3-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="303f3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="303f3-112">Exécutez l’applet de commande suivante pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="303f3-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

