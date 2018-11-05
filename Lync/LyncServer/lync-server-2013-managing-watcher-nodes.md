---
title: Gestion des nœuds observateurs
TOCTitle: Gestion des nœuds observateurs
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49891374
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des nœuds observateurs

 

_**Dernière rubrique modifiée :** 2012-10-20_

En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, les administrateurs peuvent utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : d’une part, l’activation et la désactivation du nœud observateur et, d’autre part, la configuration du nœud observateur pour utiliser des URL internes ou externes lors de l’exécution de ses tests.

Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées. Cependant, il peut arriver que vous deviez suspendre ces transactions. Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques. Sans connectivité réseau, ces transactions sont vouées à l’échec. Si vous souhaitez désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur atl-watcher- 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

> [!NOTE]  
> La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande <strong>Remove-CsWatcherNodeConfiguration</strong> :<br />
Remove-CsWatcherNodeConfiguration –Identity &quot;atl-watcher-001.litwareinc.com&quot;<br />
Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche ainsi l’ordinateur d’exécuter automatiquement des transactions synthétiques. Toutefois, la commande ne désinstalle ni les fichiers de l’agent System Center ni les fichiers système Lync Server 2013.

Par défaut, les nœuds observateur utilisent les URL externes d’une organisation dans le cadre de leurs tests. Cependant, les nœuds observateur peuvent également être configurés de manière à utiliser les URL internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur de manière à utiliser des URL internes à la place d’URL externes, affectez à la propriété UseInternalWebUrls la valeur True ($True) :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Si vous affectez à cette propriété la valeur par défaut, à savoir False ($False), l’observateur utilise alors les URL externes :

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

