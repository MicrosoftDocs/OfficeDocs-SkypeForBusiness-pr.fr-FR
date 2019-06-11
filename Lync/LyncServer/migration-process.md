---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processus de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une migration côte à côte. Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.

<div>

## <a name="side-by-side-migration"></a>Migration côte à côte

Dans presque chaque migration, utilisez le chemin de migration côte à côte. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Lync Server 2010, puis transférez les opérations sur le nouveau serveur. S’il est nécessaire de revenir à Lync Server 2010, vous ne pouvez pas déplacer les opérations vers les serveurs d’origine. Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.

</div>

<div>

## <a name="coexistence-testing"></a>Tests de coexistence

Après avoir déployé Lync Server 2013 en parallèle avec Lync Server 2010, le déploiement représente un état de test de coexistence de Lync Server 2013 et de Lync Server 2010. Dans cet État, il est important de tester et de veiller à ce que les services soient démarrés, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires. Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement. En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant un certain temps pour garantir que la compatibilité et les fonctionnalités de l’application fonctionnent correctement. Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les applications et pools hérités de Lync Server 2010 sont obsolètes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

