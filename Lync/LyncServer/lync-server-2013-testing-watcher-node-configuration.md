---
title: 'Lync Server 2013 : test de la configuration du nœud observateur'
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
ms.openlocfilehash: a52b251f238b8d79602e5fe1bf2803902cbae23f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503811"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="8e7e0-102">Test de la configuration du nœud observateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e7e0-102">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e7e0-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="8e7e0-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e7e0-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="8e7e0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8e7e0-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="8e7e0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e7e0-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="8e7e0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8e7e0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e7e0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e7e0-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="8e7e0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8e7e0-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8e7e0-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet cswatchernodeconfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="8e7e0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="8e7e0-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8e7e0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8e7e0-112">Description</span><span class="sxs-lookup"><span data-stu-id="8e7e0-112">Description</span></span>

<span data-ttu-id="8e7e0-113">Si vous utilisez Microsoft System Center Operations Manager pour analyser Lync Server 2013, vous avez la possibilité de configurer les « nœuds observateur » : ordinateurs qui exécutent régulièrement et automatiquement des transactions synthétiques pour vérifier que Lync Server fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="8e7e0-114">Les nœuds observateurs sont affectés à des pools et sont gérés à l’aide des applets de commande **applet cswatchernodeconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8e7e0-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="8e7e0-115">Notez que vous n’avez pas besoin d’installer des nœuds observateur si vous utilisez System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="8e7e0-116">Vous pouvez toujours surveiller votre système sans utiliser de nœuds observateur.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="8e7e0-117">La seule différence réside dans le fait que les transactions synthétiques que vous souhaitez exécuter doivent être appelées manuellement au lieu d’être appelées automatiquement par Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="8e7e0-118">L’applet de commande **test-applet cswatchernodeconfiguration** vous permet de vérifier qu’un nœud observateur a été correctement configuré et qu’il est affecté à un pool Lync Server 2013 valide.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="8e7e0-119">Notez que la cmdlet **test-applet cswatchernodeconfiguration** doit être exécutée sur le nœud observateur lui-même.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="8e7e0-120">L’applet de commande ne peut pas être exécutée sur des ordinateurs distants.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8e7e0-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="8e7e0-121">Running the test</span></span>

<span data-ttu-id="8e7e0-122">La commande suivante vérifie les paramètres de configuration de chaque nœud observateur utilisé dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8e7e0-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="8e7e0-123">Determining success or failure</span></span>

<span data-ttu-id="8e7e0-124">L’exemple de sortie réussi suivant illustre un système avec quatre serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="8e7e0-125">Validation du pool cible atl-cs-001.litwareinc.com par rapport à la topologie.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="8e7e0-126">Opération réussie : le pool cible atl-cs-001.litwareinc.com existe dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="8e7e0-127">Opération réussie : le rôle serveur d’inscriptions atl-cs-001.litwareinc.com a été installé sur le pool cible.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="8e7e0-128">Opération réussie : la version du pool cible atl-cs-001.litwareinc.com est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="8e7e0-129">Opération réussie : le numéro de port du pool cible 5061 atl-cs-001.litwareinc.com est correct.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="8e7e0-130">La vérification des pools manquants dans la configuration du nœud observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="8e7e0-131">Si une erreur est détectée, elle est imprimée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="8e7e0-132">La vérification des pools manquants dans la configuration du nœud observateur est terminée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="8e7e0-133">La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="8e7e0-134">Si une erreur est détectée, elle est imprimée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="8e7e0-135">La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est terminée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="8e7e0-136">Le type d’authentification détecté est Negotiate.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="8e7e0-137">Existence de la validation des informations d’identification de l’utilisateur test SIP : user1@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="8e7e0-138">Existence de la validation des informations d’identification de l’utilisateur test SIP : user2@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="8e7e0-139">La vérification des pools manquants dans la configuration du nœud observateur est démarrée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="8e7e0-140">Si une erreur est détectée, elle est imprimée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="8e7e0-141">AVERTISSEMENT : le pool atl-cs-001.litwareinc.com possède un serveur d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="8e7e0-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="8e7e0-142">rôle installé, mais aucun utilisateur de test n’est configuré pour lui.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="8e7e0-143">La vérification des pools manquants dans la configuration du nœud observateur est terminée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="8e7e0-144">La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est</span><span class="sxs-lookup"><span data-stu-id="8e7e0-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="8e7e0-145">début.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-145">started.</span></span> <span data-ttu-id="8e7e0-146">Si une erreur est détectée, elle est imprimée.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="8e7e0-147">Test-CsWatcherNodeConfiguration : impossible de trouver la clé de registre d’intégrité dans</span><span class="sxs-lookup"><span data-stu-id="8e7e0-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="8e7e0-148">Logiciels \\ Microsoft \\ communications en temps réel.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="8e7e0-149">Assurez-vous que le nœud observateur. msi est</span><span class="sxs-lookup"><span data-stu-id="8e7e0-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="8e7e0-150">installé correctement.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8e7e0-151">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="8e7e0-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="8e7e0-152">Voici quelques-unes des causes courantes de l’échec **de test-applet cswatchernodeconfiguration** :</span><span class="sxs-lookup"><span data-stu-id="8e7e0-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="8e7e0-153">Le nœud observateur n’est pas installé correctement.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="8e7e0-154">Aucun utilisateur de test n’est configuré.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e7e0-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e7e0-155">See Also</span></span>


[<span data-ttu-id="8e7e0-156">Get-applet cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="8e7e0-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="8e7e0-157">New-applet cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="8e7e0-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="8e7e0-158">Remove-applet cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="8e7e0-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="8e7e0-159">Set-applet cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="8e7e0-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

