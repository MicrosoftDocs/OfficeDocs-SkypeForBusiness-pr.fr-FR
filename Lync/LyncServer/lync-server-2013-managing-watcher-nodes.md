---
title: 'Lync Server 2013 : gestion des nœuds observateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6422754da81aa17d6a746f6539258b3f6ae0d2c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gestion des nœuds observateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, les administrateurs peuvent utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : d’une part, l’activation et la désactivation du nœud observateur et, d’autre part, la configuration du nœud observateur pour utiliser des URL internes ou externes lors de l’exécution de ses tests.

Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Cependant, il peut arriver que vous deviez suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions sont vouées à l’échec. Si vous souhaitez désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur atl-watcher- 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche ainsi l’ordinateur d’exécuter automatiquement des transactions synthétiques. Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ni les fichiers système de Lync Server 2013.



</div>

Par défaut, les nœuds observateur utilisent les URL externes d’une organisation dans le cadre de leurs tests. Cependant, les nœuds observateur peuvent également être configurés de manière à utiliser les URL internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur de manière à utiliser des URL internes à la place d’URL externes, affectez à la propriété UseInternalWebUrls la valeur True ($True) :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Si vous affectez à cette propriété la valeur par défaut, à savoir False ($False), l’observateur utilise alors les URL externes :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

