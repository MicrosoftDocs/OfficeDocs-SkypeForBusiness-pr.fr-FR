---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf8de79830dab0b85bd5346da24cf3c4222ed696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-26_

Lync Server 2013 prend en charge les déploiements multisites et à plusieurs pools. Le processus de migration de plusieurs pools à partir d’Office Communications Server 2007 R2 vers Lync Server 2013 requiert les considérations suivantes :

1.  Après avoir déployé un pool pilote Lync Server 2013, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Lync Server 2013, ainsi qu’une méthodologie pour la validation de la fonctionnalité des utilisateurs.

2.  Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Lync Server 2013.

3.  Après avoir effectué la transition des itinéraires fédérés des serveurs Edge Office Communications Server 2007 R2 vers les serveurs Edge de Lync Server 2013 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Lync Server 2013.

4.  Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool Office Communications Server 2007 R2 est vide.

5.  Après avoir vérifié que le pool Office Communications Server 2007 R2 est vide, vous pouvez désactiver le pool.
    
    Pour plus d’informations sur la façon de désactiver le pool et les serveurs Office Communications Server 2007 R2 hérités, voir [phase 10 : decommission Legacy site](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

