---
title: 'Lync Server 2013 : exécution de transactions de synthèse'
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
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Exécution de transactions de synthèse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

Les transactions synthétiques sont généralement effectuées de deux manières. Vous pouvez utiliser les applets de CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de bureaux d’enregistrement. Ces utilisateurs de test sont une paire d’utilisateurs préconfigurés pour une utilisation avec des transactions synthétiques. (En général, il s’agit des comptes de test et non des comptes appartenant aux utilisateurs réels.) Avec les utilisateurs test configurés pour un pool, vous pouvez exécuter une transaction synthétique sur le pool sans avoir à spécifier les identités (et fournir les informations d’identification pour) pour les comptes d’utilisateurs impliqués dans le test.

Vous pouvez ou non exécuter une transaction synthétique en utilisant des comptes d’utilisateurs réels. Par exemple, si deux utilisateurs ne peuvent pas échanger de messages instantanés, vous pouvez exécuter une transaction de synthèse à l’aide de ces deux comptes d’utilisateur (plutôt que de deux comptes de test), puis essayer de diagnostiquer et résoudre le problème. Si vous décidez d’effectuer une transaction synthétique à l’aide de comptes d’utilisateurs réels, vous devez fournir les noms de connexion et les mots de passe pour chaque utilisateur.

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher dans Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

