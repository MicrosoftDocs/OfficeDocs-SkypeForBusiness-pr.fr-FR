---
title: 'Lync Server 2013 : vue d’ensemble de la jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Vue d’ensemble de la jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le déploiement d’une jonction SIP peut contribuer grandement à simplifier les télécommunications de votre organisation et à préparer celle-ci en vue des dernières améliorations apportées aux communications en temps réel. L’un des principaux avantages qu’offre le déploiement d’une jonction SIP est que vous pouvez consolider les connexions de votre organisation vers le réseau téléphonique commuté (PSTN) sur le site central, contrairement à la jonction TDM, qui nécessite une jonction séparée pour chaque site de succursale vers le site central.

<div>

## <a name="sip-trunking-in-lync-server"></a>Jonction SIP dans Lync Server

Les fonctionnalités de jonction SIP de Lync Server 2013 permettent les opérations suivantes :

  - Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou un appel longue distance au format E.164 qui aboutit sur le réseau PSTN en tant que service du fournisseur de service correspondant.

  - Chaque abonné PSTN peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) associé à cet utilisateur.

</div>

<div>

## <a name="cost-savings"></a>Économies

Les économies associées à la jonction SIP peuvent être substantielles :

  - Les appels longue distance coûtent en général moins cher via une jonction SIP.

  - Vous pouvez réduire les coûts de gestion et la complexité du déploiement.

  - Les coûts d’accès de base (Basic rate interface, BRI) et d’accès primaire (Primary Rate Interface, PRI) sont éliminés si vous connectez une jonction SIP directement à votre fournisseur de services de téléphonie Internet pour un coût nettement plus bas. Avec une jonction TDM, les fournisseurs de service facturent les appels à la minute. Le coût d’une jonction SIP peut être basé sur l’utilisation de la bande passante, que vous pouvez acheter en plus petites tranches plus économiques. (Le coût réel dépend du modèle de service du fournisseur de services de téléphonie Internet que vous choisissez.)

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Jonction SIP comparée à l’hébergement d’une passerelle PSTN ou d’un PBX IP

Étant donné que les jonctions SIP se connectent directement à votre fournisseur de service, vous pouvez éliminer les passerelles PSTN et éviter le coût et la complexité de leur gestion. L’utilisation d’une jonction SIP peut se traduire par des économies substantielles, car les tâches de maintenance et d’administration sont réduites.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Services VoIP étendus

Bénéficier de fonctionnalités vocales est souvent la principale motivation pour déployer une jonction SIP, mais la prise en charge de fonctionnalités vocales n’est que la première étape. Avec la jonction SIP, vous pouvez étendre les fonctionnalités VoIP et activer Lync Server 2013 pour offrir un ensemble de services plus riche. Par exemple :

  - La détection de présence améliorée pour les appareils qui n’exécutent pas Lync Server 2013 peut offrir une meilleure intégration avec les téléphones mobiles, ce qui vous permet de savoir quand un utilisateur est sur un téléphone mobile.

  - Le service d’appels d’urgence E9-1-1 permet aux services de secours qui répondent aux appels d’urgence de déterminer l’emplacement de la personne qui appelle à partir de son numéro de téléphone.

<div>


> [!NOTE]  
> Contactez votre fournisseur de services de téléphonie Internet pour savoir quels services il prend en charge et peut activer pour votre organisation.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

