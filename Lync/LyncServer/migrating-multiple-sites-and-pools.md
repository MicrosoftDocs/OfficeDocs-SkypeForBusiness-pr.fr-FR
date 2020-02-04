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
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools. Le processus de migration de plusieurs pools de Lync Server 2010 vers Lync Server 2013 nécessite les éléments suivants :

1.  Après le déploiement d’un pool de pilotes de Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilote qui seront déplacés vers le pool Lync Server 2013 et une méthodologie permettant de valider les fonctionnalités des utilisateurs. Par exemple, après le déplacement d’un utilisateur vers le pool de pilotes, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Lync Server 2013.

2.  Après le déploiement d’un serveur de périphérie dans le pool de pilotes, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.

3.  Après avoir basculé les itinéraires fédérés de Lync Server 2010 Edge Server vers les serveurs de périphérie de Lync Server 2013, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.

4.  Après avoir déplacé tous les utilisateurs et les objets de contact non-utilisateur, vous devez vérifier que le pool Lync Server 2010 est vide.

5.  Après avoir vérifié que le pool Lync Server 2010 est vide, vous pouvez désactiver le pool.
    
    Pour plus d’informations sur la désactivation du pool et des serveurs hérités de Lync Server 2010, voir [phase 8 : désactiver les pools hérités](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

