---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processus de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-24_

La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une procédure de migration côte à côte. Cette rubrique décrit la raison pour laquelle vous devez utiliser la migration côte à côte et inclut également des informations sur la coexistence.

<div>

## <a name="side-by-side-migration"></a>Migration côte à côte

Dans presque chaque migration, utilisez le chemin de migration côte à côte. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 ainsi qu’un serveur correspondant exécutant Office Communications Server 2007 R2, puis vous transférez des opérations vers le nouveau serveur. S’il est nécessaire de revenir à la version R2 d’Office Communications Server 2007, vous ne pouvez pas déplacer les opérations vers les serveurs d’origine. Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.

</div>

<div>

## <a name="coexistence-testing"></a>Tests de coexistence

Après avoir déployé Lync Server 2013 en parallèle avec Office Communications Server 2007 R2, la topologie correspond à un état de test de coexistence de Lync Server 2013 et d’Office Communications Server 2007 R2. Dans cet État, il est important de tester et de garantir le bon fonctionnement des services, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires. Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement. En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps pour garantir que la compatibilité et les fonctionnalités de l’application fonctionnent correctement. Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les applications et pools hérités d’Office Communications Server 2007 R2 sont obsolètes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

