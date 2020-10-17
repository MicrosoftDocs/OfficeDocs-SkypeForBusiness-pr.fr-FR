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
ms.openlocfilehash: 94c1e056200a7fc1afec930b7548cfd018c1aa9d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524801"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="945b4-102">Gestion des nœuds observateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="945b4-102">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="945b4-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="945b4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="945b4-104">En plus de modifier les transactions synthétiques qui sont exécutées sur un nœud observateur, les administrateurs peuvent utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : d’une part, l’activation et la désactivation du nœud observateur et, d’autre part, la configuration du nœud observateur pour utiliser des URL internes ou externes lors de l’exécution de ses tests.</span><span class="sxs-lookup"><span data-stu-id="945b4-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="945b4-105">Par défaut, les nœuds observateur sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées.</span><span class="sxs-lookup"><span data-stu-id="945b4-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="945b4-106">Cependant, il peut arriver que vous deviez suspendre ces transactions.</span><span class="sxs-lookup"><span data-stu-id="945b4-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="945b4-107">Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="945b4-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="945b4-108">Sans connectivité réseau, ces transactions sont vouées à l’échec.</span><span class="sxs-lookup"><span data-stu-id="945b4-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="945b4-109">Si vous souhaitez désactiver temporairement un nœud observateur, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="945b4-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="945b4-p102">Cette commande désactive l’exécution des transactions synthétiques sur le nœud observateur atl-watcher- 001.litwareinc.com. Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="945b4-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="945b4-112">La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateur.</span><span class="sxs-lookup"><span data-stu-id="945b4-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="945b4-113">Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :</span><span class="sxs-lookup"><span data-stu-id="945b4-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="945b4-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="945b4-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="945b4-115">Cette commande supprime tous les paramètres de configuration du nœud observateur de l’ordinateur spécifié, ce qui empêche ainsi l’ordinateur d’exécuter automatiquement des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="945b4-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="945b4-116">Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ni les fichiers système de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="945b4-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="945b4-p105">Par défaut, les nœuds observateur utilisent les URL externes d’une organisation dans le cadre de leurs tests. Cependant, les nœuds observateur peuvent également être configurés de manière à utiliser les URL internes de l’organisation. Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre. Pour configurer un nœud observateur de manière à utiliser des URL internes à la place d’URL externes, affectez à la propriété UseInternalWebUrls la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="945b4-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="945b4-121">Si vous affectez à cette propriété la valeur par défaut, à savoir False ($False), l’observateur utilise alors les URL externes :</span><span class="sxs-lookup"><span data-stu-id="945b4-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

