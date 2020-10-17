---
title: 'Lync Server 2013 : colocalisation des serveurs pris en charge pour les composants Edge'
description: 'Lync Server 2013 : colocalisation de serveur prise en charge pour les composants Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556360"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Colocalisation de serveur prise en charge pour les composants Edge dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Le service Edge d’accès, le service Edge de conférence Web, le service Edge A/V et le service proxy XMPP sont colocalisés sur les serveurs Edge. Les serveurs suivants fournissent les fonctions nécessaires à l’accès des utilisateurs externes et doivent être déployés en tant que serveurs dédiés :

  - Serveur Edge

  - Directeur (facultatif)

  - Proxy inverse

<div>


> [!IMPORTANT]  
> Le proxy inverse n’a pas besoin d’être dédié pour servir uniquement Lync Server 2013. Par exemple, vous pouvez fournir des services pour publier les services Web Lync Server et fournir simultanément un site Web publié pour un autre site Web qui n’a aucune incidence sur Lync Server. Si vous disposez déjà d’un serveur proxy inverse dans le réseau de périmètre pour prendre en charge d’autres services, vous pouvez l’utiliser pour Lync Server 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

