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

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Configurer un service d’informations d’emplacement secondaire dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Lync Server 2013 fournit une interface de service Web que vous pouvez utiliser pour pointer le service informations d’emplacement vers une base de données de source d’emplacement secondaire. L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL du service informations sur l’emplacement. Si une base de données d’emplacements et une base de données d’emplacements secondaires sont configurées, le service d’informations d’emplacement interroge d’abord la base de données d’emplacements et, si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client à la base de données SLS. Si l’emplacement existe dans le contrat SLS, le service d’informations sur l’emplacement renvoie l’emplacement au client.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour l’applet de commande suivante :

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Pour configurer la base de données d’emplacements secondaires

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

