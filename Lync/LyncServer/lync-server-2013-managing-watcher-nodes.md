---
title: 'Lync Server 2013: gestion des nœuds d’observateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gestion des nœuds d’observation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-20_

Outre la modification des transactions synthétiques exécutées sur un nœud d’observation, les administrateurs peuvent également utiliser l’applet de connexion **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes: l’activation et la désactivation du nœud Watcher et configuration du nœud d’observation pour utiliser des URL internes ou des URL externes lors de l’exécution de ses tests.

Par défaut, les nœuds observateurs sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Néanmoins, il est possible que vous deviez suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, il est garanti que les transactions échouent. Si vous voulez désactiver temporairement un nœud FileSystemWatcher, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Cette commande désactive l’exécution de transactions synthétiques dans le nœud d’observation, ATL-Watcher-001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateurs. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :<BR>Remove-CsWatcherNodeConfiguration-Identity "atl-watcher-001.litwareinc.com"<BR>Cette commande supprime tous les paramètres de configuration de nœud d’observation de l’ordinateur spécifié, ce qui empêche l’ordinateur d’exécuter automatiquement des transactions de synthèse. Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ou les fichiers système de Lync Server 2013.



</div>

Par défaut, les nœuds d’observation utilisent les URL externes d’une organisation lors de ses tests. Toutefois, les nœuds d’observation peuvent également être configurés pour utiliser les URL internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud FileSystemWatcher de manière à utiliser des URL internes au lieu d’URL externes, définissez la propriété UseInternalWebUrls sur true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Si vous rétablissez cette propriété sur la valeur par défaut false ($False), l’observateur utilise alors les URL externes:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

