---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9339784e33920910471c25163875881d391ef9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processus de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

La procédure de migration recommandée et prise en charge pour Lync Server 2013 est une migration côte à côte. Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et fournit également des informations sur les tests de coexistence.

<div>

## <a name="side-by-side-migration"></a>Migration côte à côte

Il est recommandé d’appliquer la migration côte à côte dans pratiquement toutes les migrations. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Lync Server 2010, puis transférez des opérations vers le nouveau serveur. S’il s’avère nécessaire de restaurer Lync Server 2010, vous ne pouvez basculer les opérations vers les serveurs d’origine. Sachez que dans cette situation, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.

</div>

<div>

## <a name="coexistence-testing"></a>Test de coexistence

Une fois que vous avez déployé Lync Server 2013 en parallèle avec Lync Server 2010, le déploiement représente un état de test de coexistence de Lync Server 2013 et Lync Server 2010. Dans cet État, il est important de tester et de vérifier que les services sont démarrés, que chaque site peut être administré et que les clients peuvent communiquer avec les utilisateurs actuels et hérités. Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement. En règle générale, la phase de test de coexistence existe tout au long du test pilote de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant une période de temps pour garantir le bon fonctionnement de la compatibilité et des fonctions des applications. Une fois le test pilote effectué, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools hérités et les applications de Lync Server 2010 sont supprimés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

