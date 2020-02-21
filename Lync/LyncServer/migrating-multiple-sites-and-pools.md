---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e104160d7bb770e91f21cda32e43c83356df98a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools. Le processus de migration de plusieurs pools de Lync Server 2010 vers Lync Server 2013 nécessite les considérations suivantes :

1.  Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013, ainsi qu’une méthodologie pour la validation de la fonctionnalité des utilisateurs. Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Lync Server 2013.

2.  Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.

3.  Après avoir effectué la transition des itinéraires fédérés des serveurs Edge Lync Server 2010 vers les serveurs Edge de Lync Server 2013, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.

4.  Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Lync Server 2010 est vide.

5.  Après avoir vérifié que le pool Lync Server 2010 est vide, vous pouvez désactiver le pool.
    
    Pour plus d’informations sur la façon de désactiver le pool et les serveurs Lync Server 2010 hérités, voir [phase 8 : retirer les pools hérités](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

