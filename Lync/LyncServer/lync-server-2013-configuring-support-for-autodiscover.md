---
title: 'Lync Server 2013 : configuration de la prise en charge de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3893ddd2282fd6abdfff716207f99102d09fac31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507541"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configuration de la prise en charge du service de découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-21_

Le **service de découverte automatique** des services Web Lync Server est d’abord apparu dans la mise à jour cumulative lync Server 2010 : novembre 2011. Cette mise à jour est accompagnée de la version initiale des clients mobiles Lync. Le service de découverte automatique exposait les services de mobilité, appelé service MCX.

Le service de découverte automatique agit en tant qu’emplacement unique pour tous les clients afin de demander des informations sur les services et les fonctionnalités disponibles, ainsi que sur la façon de contacter les services, soit par un nom de domaine complet, soit par une référence Web Uniform Resource Locator. La découverte automatique expose un certain nombre de fonctionnalités, et chaque client effectue des demandes en fonction des fonctionnalités que le client peut utiliser. Par exemple, un client de bureau Lync 2013 utilisera autodiscvoer pour déterminer les services Web externes, mais n’utilisera pas les services de mobilité (MCX). Pour définir correctement et permettre à vos clients d’utiliser les fonctionnalités disponibles, les scénarios qui permettent à un client de trouver et d’utiliser efficacement des entrées de découverte automatique doivent être définis. Pour utiliser autodoscover, votre déploiement nécessite qu’un proxy inverse publie les services Web Lync Server, que les enregistrements DNS soient configurés pour résoudre les requêtes DNS pour le service de découverte automatique Lync Server et les services Web Lync Server, et que les services de certificats soient correctement configurés pour votre scénario spécifique.

<div>


> [!TIP]  
> Pour obtenir des informations techniques sur les éléments inclus dans la demande/réponse de découverte automatique, voir <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover dans Lync Server 2013</A>.



</div>

Les informations et les tableaux suivants définissent, par scénario, les configurations (le cas échéant) que vous devez implémenter pour fournir l’utilisation complète et efficace du service de découverte automatique. Les informations contenues dans les rubriques suivantes sont propres à Microsoft Lync Server 2013. Si vous recherchez des instructions sur la planification de la mobilité pour Lync Server 2010, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) . Pour déployer la mobilité pour Lync Server 2010, reportez-vous à [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de DNS pour la découverte automatique dans Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configuration de certificats pour la découverte automatique dans Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configuration d’un proxy inverse pour la découverte automatique dans Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configuration de la découverte automatique dans Lync Server 2013 pour les déploiements hybrides](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

