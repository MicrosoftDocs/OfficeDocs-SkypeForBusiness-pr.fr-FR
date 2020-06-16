---
title: Processus de migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Processus de migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

La procédure de migration recommandée et prise en charge pour Lync Server 2013 est la procédure de migration côte à côte. Cette rubrique décrit les raisons pour lesquelles il est recommandé d’effectuer une migration côte à côte et inclut également des informations sur la coexistence.

<div>

## <a name="side-by-side-migration"></a>Migration côte à côte

Il est recommandé de pratiquer la migration côte à côte dans pratiquement toutes les migrations. Dans une migration côte à côte, vous déployez un nouveau serveur avec Lync Server 2013 avec un serveur correspondant exécutant Office Communications Server 2007 R2, puis vous transférez des opérations vers le nouveau serveur. S’il s’avère nécessaire de restaurer Office Communications Server 2007 R2, vous ne pouvez basculer les opérations vers les serveurs d’origine. Sachez que dans cette situation, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.

</div>

<div>

## <a name="coexistence-testing"></a>Test de coexistence

Une fois que vous avez déployé Lync Server 2013 en parallèle avec Office Communications Server 2007 R2, la topologie représente un état de test de coexistence de Lync Server 2013 et Office Communications Server 2007 R2. Dans cet état, il est important d’effectuer des tests et de vérifier que les services sont démarrés ; chaque site peut être administré, et les clients peuvent communiquer avec les utilisateurs actuels et hérités. Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement. En règle générale, la phase de test de coexistence existe tout au long du test pilote de Lync Server 2013. Les utilisateurs hérités sont déplacés vers Lync Server 2013 pendant une période de temps pour garantir le bon fonctionnement de la compatibilité et des fonctions des applications. Une fois le test pilote effectué, les utilisateurs et les applications sont déplacés vers la version de production de Lync Server 2013, et les pools hérités et les applications d’Office Communications Server 2007 R2 sont supprimés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

