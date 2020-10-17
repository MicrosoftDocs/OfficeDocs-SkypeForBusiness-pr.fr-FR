---
title: 'Lync Server 2013 : planification de la découverte automatique'
description: 'Lync Server 2013 : planification de la découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544630"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planification de la découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-16_

La découverte automatique a été introduite pour Lync Server dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011. L’objectif principal de cette implémentation initiale de la découverte automatique était de permettre à Lync mobile de localiser le service de mobilité (MCX). Le service de découverte automatique dans Lync Server 2013 est désormais un service utilisé par tous les clients pour localiser les services de serveur et d’utilisateurs. Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les directeurs et les serveurs frontaux.

<div>


> [!TIP]  
> Pour une compréhension plus technique de la découverte automatique et des informations communiquées aux clients, voir <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.<BR>La mobilité est toujours un scénario distinct et les services de mobilité nécessitent toujours une planification particulière. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.



</div>

Lorsque la découverte automatique a été introduite dans Lync Server 2010, il y a eu des compromis à effectuer afin d’implémenter un service nécessitant des modifications de certificat potentielles pour les déploiements de serveurs existants. La découverte automatique peut être utilisée via le port TCP 443 pour HTTPs ou via le port TCP 80 pour HTTP. Si la décision a été prise pour utiliser le protocole HTTPs, les certificats sur les proxys inverses, les directeurs et les serveurs frontaux devaient être réémiss afin de prendre en charge les `lyncdiscover.<domain>` enregistrements requis et `lyncdiscoverinternal.<domain>` DNS. Si la décision consistait à utiliser le protocole HTTP, la réémission de certificats pourrait être évitée en utilisant des enregistrements DNS CNAMe (ou alias) pour utiliser des noms existants sur les certificats. L’utilisation du protocole HTTP signifie que les communications initiales n’étaient pas chiffrées.

Étant donné que Lync Server 2013 utilise la découverte automatique pour tous les clients, le scénario principal consiste à utiliser exclusivement HTTPs et à créer des certificats avec lyncdiscover.\<domain\> dans le cadre de la configuration de proxys inverses, de directeurs et de serveurs frontaux. Si vous implémentez la découverte automatique dans un déploiement mis à niveau à partir de Lync Server 2010, vous pouvez utiliser le protocole HTTP pour éviter de réémettre des certificats. Les instructions pour les deux scénarios sont fournies dans les sections suivantes.

<div>


> [!IMPORTANT]  
> La liste des autres noms de sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un <EM>lyncdiscover. &lt; entrée &gt; sipdomain</EM> pour chaque domaine SIP au sein de votre organisation. Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, voir <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover dans Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Résumé des ports-découverte automatique dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Résumé des enregistrements DNS-découverte automatique dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Découverte automatique de domaine hybride et fractionné dans Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

