---
title: Considérations relatives à la coexistence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b31b8f3e534fc7b060f194f84310050a0386d8c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Considérations relatives à la coexistence

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Après la migration, seul un pool de serveurs Lync Server 2013, persistent chat existe et vous pouvez mettre hors service votre déploiement hérité.

Avant la fin de la migration et avant que vous n’ayez désactivé entièrement votre déploiement actuel du serveur de conversation de groupe, vous pouvez avoir l’un des déploiements suivants :

  - Lync Server 2013, pool de serveurs de conversation permanente, qui doit être hébergé sur un pool Lync Server 2013.

  - Lync Server 2010, pool de conversation de groupe, qui doit être hébergé sur un pool Lync Server 2010.

  - Pool de conversation de groupe Office Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.

Ces déploiements peuvent exister côte à côte. Toutefois, les catégories, les salles et les compléments d’un déploiement n’interagissent pas avec ceux du déploiement associé.

À l’aide de la configuration manuelle, un client hérité (client de conversation de groupe) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, Group chat ou Lync Server 2013.

Le Lync 2013 (client) ne peut interagir qu’avec le pool de serveurs Lync Server 2013, persistent chat, pas avec les pools de serveurs de conversation de groupe hérités. Pour utiliser la conversation permanente dans un Lync 2013 (client), l’utilisateur doit être hébergé sur Lync 2013 et activé par la stratégie.

</div>

<span> </span>

</div>

</div>

</div>

