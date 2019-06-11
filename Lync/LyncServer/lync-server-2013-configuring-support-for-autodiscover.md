---
title: 'Lync Server 2013: configuration de la prise en charge de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configuration de la prise en charge de la découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-21_

Le **service de découverte automatique** des services Web de Lync Server est d’abord apparu dans la mise à jour cumulative de lync Server 2010:2011 novembre. Cette mise à jour a été accompagnée de la version initiale des clients mobiles Lync. Le service de découverte automatique a exposé les services de mobilité, connus sous le nom de service MCX.

Le service de découverte automatique joue le rôle d’emplacement unique pour tous les clients afin de demander des informations sur les services et les fonctionnalités disponibles, et sur la manière de contacter les bureaux de vente, soit par un nom de domaine complet, soit par une référence de localisateur de ressources Web uniformes. La fonction de découverte automatique expose plusieurs fonctionnalités et chaque client effectue des requêtes en fonction des fonctionnalités que le client peut utiliser. Par exemple, un client de bureau Lync 2013 utilise autodiscvoer pour déterminer les services Web externes, mais n’utilise pas les services de mobilité (MCX). Pour pouvoir définir et permettre à vos clients d’utiliser les fonctionnalités qui leur sont disponibles, les scénarios permettant à un client de rechercher et d’utiliser efficacement des entrées de découverte automatique doivent être définis. Pour utiliser autodoscover, votre déploiement exige qu’un proxy inverse publie les services Web de Lync Server, que les enregistrements DNS sont configurés pour résoudre les requêtes DNS pour le service de découverte automatique de Lync Server et les services Web Lync Server et ces services de certificats sont configurés correctement pour votre scénario spécifique.

<div>


> [!TIP]  
> Pour plus d’informations techniques sur les éléments de la requête/réponse de découverte automatique, voir <A href="lync-server-2013-understanding-autodiscover.md">comprendre la découverte automatique dans Lync Server 2013</A>.



</div>

Les informations et les tableaux suivants définissent, par scénario, les configurations (le cas échéant) que vous devez implémenter afin de fournir une utilisation complète et efficace du service de découverte automatique. Les informations contenues dans les rubriques suivantes sont spécifiques à Microsoft Lync Server 2013. Pour plus d’informations sur la planification de la mobilité pour Lync Server 2010, voir [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113). Pour déployer Mobility pour Lync Server 2010, voir[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

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

