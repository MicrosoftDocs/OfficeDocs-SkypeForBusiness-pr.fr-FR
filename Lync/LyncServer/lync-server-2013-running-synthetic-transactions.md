---
title: 'Lync Server 2013 : exécution de transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 448e96c03b554970b1ee92166908965ee2a6629c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Exécution de transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

Les transactions synthétiques sont généralement menées de deux manières. Vous pouvez utiliser les applets de commande CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de serveurs d’inscriptions. Ces utilisateurs de test sont une paire d’utilisateurs qui ont été préconfigurés pour être utilisés avec des transactions synthétiques. (En général, il s’agit de comptes de test et non de comptes qui appartiennent à des utilisateurs réels.) Lorsque les utilisateurs de test sont configurés pour un pool, vous pouvez exécuter une transaction synthétique sur ce pool sans avoir à spécifier les identités des comptes d’utilisateurs impliqués dans le test (et fournir les informations d’identification).

Ou, vous pouvez exécuter une transaction synthétique à l’aide de comptes d’utilisateur réels. Par exemple, si deux utilisateurs ne peuvent pas échanger des messages instantanés, vous pouvez exécuter une transaction synthétique en utilisant ces deux comptes d’utilisateur (au lieu d’une paire de comptes de test), puis essayer de diagnostiquer et résoudre le problème. Si vous décidez d’effectuer une transaction synthétique à l’aide de comptes d’utilisateur réels, vous devez fournir les noms de connexion et les mots de passe de chaque utilisateur.

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des utilisateurs test de nœud observateur et des paramètres de configuration dans Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

