---
title: 'Lync Server 2013 : gestion des nœuds d’observateur'
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
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="371e1-102">Gestion des nœuds d’observation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="371e1-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="371e1-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="371e1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="371e1-104">Outre la modification des transactions synthétiques exécutées sur un nœud d’observation, les administrateurs peuvent également utiliser l’applet de connexion **Set-CsWatcherNodeConfiguration** pour effectuer deux autres tâches importantes : l’activation et la désactivation du nœud Watcher et la configuration du nœud d’observation pour utiliser des URL internes ou des URL externes lors de l’exécution de ces tests.</span><span class="sxs-lookup"><span data-stu-id="371e1-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="371e1-105">Par défaut, les nœuds observateurs sont conçus pour exécuter régulièrement toutes leurs transactions synthétiques activées.</span><span class="sxs-lookup"><span data-stu-id="371e1-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="371e1-106">Néanmoins, il est possible que vous deviez suspendre ces transactions.</span><span class="sxs-lookup"><span data-stu-id="371e1-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="371e1-107">Par exemple, si le nœud observateur est temporairement déconnecté du réseau, il est inutile d’exécuter les transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="371e1-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="371e1-108">Sans connectivité réseau, il est garanti que les transactions échouent.</span><span class="sxs-lookup"><span data-stu-id="371e1-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="371e1-109">Si vous voulez désactiver temporairement un nœud FileSystemWatcher, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="371e1-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="371e1-110">Cette commande désactive l’exécution de transactions synthétiques dans le nœud d’observation, ATL-Watcher-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="371e1-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="371e1-111">Pour reprendre l’exécution des transactions synthétiques, affectez à la propriété Enabled la valeur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="371e1-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="371e1-p103">La propriété Enabled peut être utilisée pour activer ou désactiver les nœuds observateurs. Si vous souhaitez supprimer définitivement un nœud observateur, utilisez l’applet de commande <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :</span><span class="sxs-lookup"><span data-stu-id="371e1-p103">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="371e1-114">Remove-CsWatcherNodeConfiguration-Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="371e1-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="371e1-115">Cette commande supprime tous les paramètres de configuration de nœud d’observation de l’ordinateur spécifié, ce qui empêche l’ordinateur d’exécuter automatiquement des transactions de synthèse.</span><span class="sxs-lookup"><span data-stu-id="371e1-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="371e1-116">Toutefois, la commande ne désinstalle pas les fichiers de l’agent System Center ou les fichiers système de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="371e1-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="371e1-117">Par défaut, les nœuds d’observation utilisent les URL externes d’une organisation lors de ses tests.</span><span class="sxs-lookup"><span data-stu-id="371e1-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="371e1-118">Toutefois, les nœuds d’observation peuvent également être configurés pour utiliser les URL internes de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="371e1-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="371e1-119">Cela permet aux administrateurs de vérifier l’accès URL pour les utilisateurs situés à l’intérieur du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="371e1-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="371e1-120">Pour configurer un nœud FileSystemWatcher de manière à utiliser des URL internes au lieu d’URL externes, définissez la propriété UseInternalWebUrls sur true ($True) :</span><span class="sxs-lookup"><span data-stu-id="371e1-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="371e1-121">Si vous rétablissez cette propriété sur la valeur par défaut false ($False), l’observateur utilise alors les URL externes :</span><span class="sxs-lookup"><span data-stu-id="371e1-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

