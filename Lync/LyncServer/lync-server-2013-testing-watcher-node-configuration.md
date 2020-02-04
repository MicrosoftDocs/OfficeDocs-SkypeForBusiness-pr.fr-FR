---
title: 'Lync Server 2013 : test de la configuration du nœud observateur d’observateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="87c95-102">Test de la configuration du nœud FileSystemWatcher dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c95-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87c95-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="87c95-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87c95-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="87c95-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="87c95-105">Jour</span><span class="sxs-lookup"><span data-stu-id="87c95-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87c95-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="87c95-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="87c95-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87c95-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87c95-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="87c95-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="87c95-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="87c95-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="87c95-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="87c95-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="87c95-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="87c95-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="87c95-112">Description</span><span class="sxs-lookup"><span data-stu-id="87c95-112">Description</span></span>

<span data-ttu-id="87c95-113">Si vous utilisez Microsoft System Center Operations Manager pour contrôler Lync Server 2013, vous avez la possibilité de configurer des « nœuds d’observation » : les ordinateurs qui exécutent de manière régulière et automatique des transactions de synthèse pour vérifier que le serveur Lync fonctionne correctement. devait.</span><span class="sxs-lookup"><span data-stu-id="87c95-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="87c95-114">Les nœuds d’observation sont assignés aux pools et sont gérés à l’aide des cmdlets **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="87c95-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="87c95-115">Notez que vous n’avez pas besoin d’installer de nœuds FileSystemWatcher si vous utilisez System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87c95-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="87c95-116">Vous pouvez toujours surveiller votre système sans utiliser de nœuds FileSystemWatcher.</span><span class="sxs-lookup"><span data-stu-id="87c95-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="87c95-117">La seule différence réside dans le fait que les transactions synthétiques que vous souhaitez exécuter doivent être appelées manuellement au lieu d’être automatiquement appelées par Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87c95-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="87c95-118">L’applet de **contrôle test-CsWatcherNodeConfiguration** vous permet de vérifier qu’un nœud d’observateur a été correctement configuré et qu’il est affecté à un pool Lync Server 2013 valide.</span><span class="sxs-lookup"><span data-stu-id="87c95-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="87c95-119">Notez que l’applet de **contrôle test-CsWatcherNodeConfiguration** doit être exécutée sur le nœud Watcher lui-même.</span><span class="sxs-lookup"><span data-stu-id="87c95-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="87c95-120">L’applet de commande ne peut pas être exécutée sur des ordinateurs distants.</span><span class="sxs-lookup"><span data-stu-id="87c95-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="87c95-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="87c95-121">Running the test</span></span>

<span data-ttu-id="87c95-122">La commande suivante vérifie les paramètres de configuration de chaque nœud FileSystemWatcher utilisé au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="87c95-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="87c95-123">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="87c95-123">Determining success or failure</span></span>

<span data-ttu-id="87c95-124">La sortie d’exemple réussie suivante illustre un système avec quatre serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="87c95-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="87c95-125">Validation de la liste de ressources atl-cs-001.litwareinc.com par rapport à la topologie.</span><span class="sxs-lookup"><span data-stu-id="87c95-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="87c95-126">Réussite : atl-cs-001.litwareinc.com de réserve cible existe dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="87c95-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="87c95-127">Réussite : le rôle de bureau d’enregistrement de la liste de atl-cs-001.litwareinc.com est installé.</span><span class="sxs-lookup"><span data-stu-id="87c95-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="87c95-128">Réussite : la version du pool cible atl-cs-001.litwareinc.com est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="87c95-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="87c95-129">Réussite : le numéro de port pour le pool cible 5061 atl-cs-001.litwareinc.com est correct.</span><span class="sxs-lookup"><span data-stu-id="87c95-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="87c95-130">La vérification de l’absence de pools dans la configuration de nœud d’observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="87c95-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="87c95-131">Si des erreurs sont détectées, elles sont imprimées.</span><span class="sxs-lookup"><span data-stu-id="87c95-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="87c95-132">La vérification de l’absence de pools dans la configuration du nœud d’observation est terminée.</span><span class="sxs-lookup"><span data-stu-id="87c95-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="87c95-133">La recherche de clés de registre de nœud d’observation créées par l’installation du nœud d’observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="87c95-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="87c95-134">Si des erreurs sont détectées, elles sont imprimées.</span><span class="sxs-lookup"><span data-stu-id="87c95-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="87c95-135">La vérification des clés de registre de nœud d’observation créées par l’installation du nœud d’observation est terminée.</span><span class="sxs-lookup"><span data-stu-id="87c95-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="87c95-136">Le type d’authentification détecté est Negotiate.</span><span class="sxs-lookup"><span data-stu-id="87c95-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="87c95-137">Validation réussie de l’existence des informations d’identification de l’utilisateur du test SIP : user1@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="87c95-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="87c95-138">Validation réussie de l’existence des informations d’identification de l’utilisateur du test SIP : user2@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="87c95-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="87c95-139">La vérification de l’absence de pools dans la configuration de nœud d’observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="87c95-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="87c95-140">Si des erreurs sont détectées, elles sont imprimées.</span><span class="sxs-lookup"><span data-stu-id="87c95-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="87c95-141">AVERTISSEMENT : le pool atl-cs-001.litwareinc.com possède le Bureau d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="87c95-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="87c95-142">rôle installé, mais aucun utilisateur de test n’est configuré pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="87c95-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="87c95-143">La vérification de l’absence de pools dans la configuration du nœud d’observation est terminée.</span><span class="sxs-lookup"><span data-stu-id="87c95-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="87c95-144">La vérification des clés de registre de nœud d’observateur créées par l’installation du nœud d’observateur est</span><span class="sxs-lookup"><span data-stu-id="87c95-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="87c95-145">lance.</span><span class="sxs-lookup"><span data-stu-id="87c95-145">started.</span></span> <span data-ttu-id="87c95-146">Si des erreurs sont détectées, elles sont imprimées.</span><span class="sxs-lookup"><span data-stu-id="87c95-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="87c95-147">Test-CsWatcherNodeConfiguration : impossible de trouver la clé de registre d’intégrité dans</span><span class="sxs-lookup"><span data-stu-id="87c95-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="87c95-148">Logiciel\\de\\Communications en temps réel Microsoft en temps réel.</span><span class="sxs-lookup"><span data-stu-id="87c95-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="87c95-149">Vérifiez que le nœud FileSystemWatcher. msi est</span><span class="sxs-lookup"><span data-stu-id="87c95-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="87c95-150">installé correctement.</span><span class="sxs-lookup"><span data-stu-id="87c95-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="87c95-151">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="87c95-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="87c95-152">Voici quelques raisons courantes pour lesquelles **les tests-CsWatcherNodeConfiguration** peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="87c95-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="87c95-153">Le nœud de l’observateur n’est pas correctement installé.</span><span class="sxs-lookup"><span data-stu-id="87c95-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="87c95-154">Aucun utilisateur de test n’est configuré.</span><span class="sxs-lookup"><span data-stu-id="87c95-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87c95-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87c95-155">See Also</span></span>


[<span data-ttu-id="87c95-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="87c95-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="87c95-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="87c95-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="87c95-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="87c95-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="87c95-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="87c95-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

