---
title: 'Lync Server 2013: planification de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planification de la découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-16_

La découverte automatique a été introduite pour Lync Server dans la mise à jour cumulative pour Lync Server 2010: novembre 2011. L’objectif principal de cette implémentation initiale de la découverte automatique était d’offrir à Lync mobile la possibilité de rechercher le service de mobilité (MCX). Le service de découverte automatique de Lync Server 2013 est désormais un service utilisé par tous les clients pour localiser les services serveur et utilisateur. Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les directeurs et les serveurs frontaux.

<div>


> [!TIP]  
> Pour plus d’informations techniques sur la découverte automatique et la façon de communiquer avec les clients, voir <A href="lync-server-2013-understanding-autodiscover.md">comprendre la découverte automatique dans Lync Server 2013</A>.<BR>La mobilité reste un scénario distinct et les services de mobilité nécessitent toujours une planification particulière. Pour plus d’informations, consultez <A href="lync-server-2013-planning-for-mobility.md">planification de la mobilité dans Lync Server 2013</A>.



</div>

Lorsque la découverte automatique a été introduite dans Lync Server 2010, il y a eu des compromis à mettre en place pour implémenter un service qui nécessitait des changements de certificats potentiels pour les déploiements de serveur existants. La découverte automatique peut être utilisée via le port TCP 443 pour HTTPs ou sur le port TCP 80 pour HTTP. S’il s’agit d’une décision d’utiliser HTTPs, les certificats des proxys inversés, des directeurs et des serveurs frontaux nécessaires doivent être réémis pour `lyncdiscover.<domain>` pouvoir `lyncdiscoverinternal.<domain>` accueillir les enregistrements DNS et obligatoires. Si la décision consistait à utiliser HTTP, le réémission de certificats peut être évité en utilisant des enregistrements DNS CNAMe (ou alias) pour utiliser les noms existants sur les certificats. L’utilisation de HTTP signifie que les communications initiales n’ont pas été chiffrées.

Dans la mesure où Lync Server 2013 utilise la découverte automatique pour tous les clients, le scénario principal consiste à utiliser HTTPs en exclusivité et à créer des certificats avec lyncdiscover. \<Domain\> dans le cadre de la configuration de proxys inverse, de directeurs et de serveurs frontaux. Si vous implémentez la découverte automatique dans un déploiement mis à niveau à partir de Lync Server 2010, il est possible que vous souhaitiez utiliser HTTP pour éviter de réémettre des certificats. Les instructions pour ces deux scénarios sont fournies dans les sections suivantes.

<div>


> [!IMPORTANT]  
> La liste autre nom de l’objet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un <EM>lyncdiscover.&lt; entrée&gt; sipdomain</EM> pour chaque domaine SIP au sein de votre organisation. Pour plus d’informations sur les autres entrées de nom de l’objet requises pour les directeurs, serveurs frontaux et proxys inversés, voir <A href="lync-server-2013-certificate-summary-autodiscover.md">synthèse des certificats-découverte automatique dans Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé du certificat-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Résumé du port-découverte automatique dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [DNS Summary-découverte automatique dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Domaines hybrides et fractionnés-découverte automatique dans Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

