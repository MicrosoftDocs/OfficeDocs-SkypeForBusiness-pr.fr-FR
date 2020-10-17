---
title: 'Lync Server 2013 : considérations relatives à la migration et à la coexistence pour IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f091b12b12913af107991c86b87d1d738bf88bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513611"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Considérations relatives à la migration et à la coexistence pour IPv6 dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-14_

IP version 6 (IPv6) n’est pas pris en charge sur Lync Server 2010 ou Office Communications Server. À des fins de test pilote, vous pouvez tester la coexistence de Lync Server 2010 et Lync Server 2013 à double pile. Nous vous recommandons de mettre à niveau tous les pools d’un site central donné vers Lync Server 2013 avant d’activer IPv6 (réseau à double pile) pour tous les pools. Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.

Les scénarios suivants sont pris en charge pendant la migration et la coexistence :

  - Lync Server 2013, Lync Server 2010 et les pools Office Communications Server 2007 R2 en mode IPv4, qui coexistent avec Lync Server 2013 en mode double pile.

  - Pool Lync Server 2013 en mode IPv6 uniquement, si le pool IPv6 uniquement est mis en silo.

</div>

<span> </span>

</div>

</div>

</div>

