---
title: 'Lync Server 2013: configurer un service d’information d’emplacement secondaire'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8219aa234330120e6462a600b9c2c27b4b11c100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Configurer un service d’information d’emplacement secondaire dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

Lync Server 2013 fournit une interface de service Web que vous pouvez utiliser pour faire pointer le service d’information d’emplacement vers une base de données de source d’emplacement secondaire (SLS). L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL. S’il s’agit d’une base de données d’emplacement et d’une base de données d’emplacement secondaire configurées, le service des informations d’emplacement interroge d’abord la base de données de localisation, et si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client vers la base de données SLS. Si l’emplacement existe dans le dossier SLS, le service d’information sur l’emplacement est alors renvoyé à l’emplacement du client.

Pour plus d’informations, consultez la documentation de Lync Server Management Shell pour l’applet de commande suivante:

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Pour configurer la base de données de l’emplacement secondaire

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

