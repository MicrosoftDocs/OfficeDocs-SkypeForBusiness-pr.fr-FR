---
title: 'Lync Server 2013 : test du service de réplication'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="d852a-102">Test du service de réplication dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d852a-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d852a-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="d852a-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d852a-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="d852a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d852a-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="d852a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d852a-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="d852a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d852a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d852a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d852a-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="d852a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d852a-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d852a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d852a-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="d852a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="d852a-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d852a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d852a-112">Description</span><span class="sxs-lookup"><span data-stu-id="d852a-112">Description</span></span>

<span data-ttu-id="d852a-113">L’applet de commande **test-CsReplica** vérifie que le service de réplication Lync Server 2013 est en cours d’exécution sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d852a-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="d852a-114">L’applet de commande **test-CsReplica** effectue les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d852a-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="d852a-115">vérification de l’état des services de l’agent duplicateur et de l’agent de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="d852a-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="d852a-116">vérification que les ports requis ont été ouverts dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="d852a-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="d852a-117">vérification de l’existence des groupes de sécurité Active Directory et ordinateur local nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d852a-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="d852a-118">Notez que cette applet de commande doit être exécutée localement.</span><span class="sxs-lookup"><span data-stu-id="d852a-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="d852a-119">Autrement dit, il doit être exécuté sur le même ordinateur que le service de réplication.</span><span class="sxs-lookup"><span data-stu-id="d852a-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="d852a-120">Il n’existe aucune option permettant d’exécuter la cmdlet **test-CsReplica** sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="d852a-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d852a-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="d852a-121">Running the test</span></span>

<span data-ttu-id="d852a-122">La commande présentée dans l’exemple 1 teste le service de réplication Lync Server 2013 sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d852a-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="d852a-123">Dans cet exemple, le paramètre Verbose est utilisé pour garantir que les informations relatives au test, y compris la réussite ou l’échec du test et l’emplacement du rapport généré par le test, sont affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="d852a-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="d852a-124">L’exemple 2 est une variante de la commande présentée dans l’exemple 1.</span><span class="sxs-lookup"><span data-stu-id="d852a-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="d852a-125">Dans ce cas, le paramètre Report est inclus pour spécifier un chemin d’accès et un nom de dossier pour le rapport généré par le test.</span><span class="sxs-lookup"><span data-stu-id="d852a-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="d852a-126">Si vous ne spécifiez pas un chemin de rapport, un nom généré automatiquement lui est attribué tel que :</span><span class="sxs-lookup"><span data-stu-id="d852a-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="d852a-127">C :\\Users\\Administrator.\\litwareinc\\AppData\\local\\Temp\\1 test-CS-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="d852a-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d852a-128">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="d852a-128">Determining success or failure</span></span>

<span data-ttu-id="d852a-129">Insérez le corps de la section ici.</span><span class="sxs-lookup"><span data-stu-id="d852a-129">Insert section body here.</span></span>

<span data-ttu-id="d852a-130">VERBOSe : création d’un fichier journal « C\\:\\Users\\testing\\\\AppData\\local Temp test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. Xml ».</span><span class="sxs-lookup"><span data-stu-id="d852a-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d852a-131">VERBOSe : création d’un fichier journal « C\\:\\Users\\testing\\\\AppData\\local Temp test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. Xml ».</span><span class="sxs-lookup"><span data-stu-id="d852a-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d852a-132">VERBOSe : le traitement de « test-CsReplica » s’est terminé avec succès.</span><span class="sxs-lookup"><span data-stu-id="d852a-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="d852a-133">VERBOSe : des résultats détaillés sont disponibles à l’adresse\\«\\C\\:\\Users testing AppData Local\\Temp\\test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. Xml ».</span><span class="sxs-lookup"><span data-stu-id="d852a-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d852a-134">VERBOSe : création d’un fichier journal</span><span class="sxs-lookup"><span data-stu-id="d852a-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="d852a-135">"C :\\\\Users\\testing\\AppData\\local\\Temp\\2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="d852a-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d852a-136">d3bd0e4a083. Xml».</span><span class="sxs-lookup"><span data-stu-id="d852a-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="d852a-137">VERBOSe : création d’un fichier journal</span><span class="sxs-lookup"><span data-stu-id="d852a-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="d852a-138">"C :\\\\Users\\testing\\AppData\\local\\Temp\\2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="d852a-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d852a-139">d3bd0e4a083. html».</span><span class="sxs-lookup"><span data-stu-id="d852a-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="d852a-140">AVERTISSEMENT : échec de test-CsReplica.</span><span class="sxs-lookup"><span data-stu-id="d852a-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="d852a-141">AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse</span><span class="sxs-lookup"><span data-stu-id="d852a-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="d852a-142">"C :\\\\Users\\testing\\AppData\\local\\Temp\\2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="d852a-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d852a-143">d3bd0e4a083. html».</span><span class="sxs-lookup"><span data-stu-id="d852a-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="d852a-144">Test-CsReplica : échec de l’exécution de la commande : l’accès au Registre demandé n’est pas</span><span class="sxs-lookup"><span data-stu-id="d852a-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="d852a-145">permis.</span><span class="sxs-lookup"><span data-stu-id="d852a-145">allowed.</span></span>

<span data-ttu-id="d852a-146">À la ligne : 1 char : 1</span><span class="sxs-lookup"><span data-stu-id="d852a-146">At line:1 char:1</span></span>

<span data-ttu-id="d852a-147">\+Test-CsReplica-verbose</span><span class="sxs-lookup"><span data-stu-id="d852a-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="d852a-148">\+CategoryInfo : InvalidOperation : ( :) \[Test-CsReplica\], sécurité</span><span class="sxs-lookup"><span data-stu-id="d852a-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="d852a-149">Exception</span><span class="sxs-lookup"><span data-stu-id="d852a-149">Exception</span></span>

<span data-ttu-id="d852a-150">\+FullyQualifiedErrorId : ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="d852a-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="d852a-151">Management. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="d852a-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="d852a-152">PS C :\\test\\des utilisateurs\></span><span class="sxs-lookup"><span data-stu-id="d852a-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="d852a-153">PS C :\\test\\des\> utilisateurs test-CsUcwaConference-TargetFqdn "LyncTest. selfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="d852a-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="d852a-154">icrosoft.com»</span><span class="sxs-lookup"><span data-stu-id="d852a-154">icrosoft.com"</span></span>

<span data-ttu-id="d852a-155">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="d852a-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="d852a-156">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d852a-156">domain name (FQDN).</span></span> <span data-ttu-id="d852a-157">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="d852a-157">Using default Registrar port number.</span></span> <span data-ttu-id="d852a-158">Rogation</span><span class="sxs-lookup"><span data-stu-id="d852a-158">Exception:</span></span>

<span data-ttu-id="d852a-159">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="d852a-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="d852a-160">Regardez</span><span class="sxs-lookup"><span data-stu-id="d852a-160">at</span></span>

<span data-ttu-id="d852a-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="d852a-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="d852a-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="d852a-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="d852a-163">Test-CsUcwaConference : aucun utilisateur de test n’est affecté à</span><span class="sxs-lookup"><span data-stu-id="d852a-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="d852a-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="d852a-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="d852a-165">Vérifiez la configuration de l’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="d852a-165">Verify test user configuration.</span></span>

<span data-ttu-id="d852a-166">À la ligne : 1 char : 1</span><span class="sxs-lookup"><span data-stu-id="d852a-166">At line:1 char:1</span></span>

<span data-ttu-id="d852a-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="d852a-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="d852a-168">\+CategoryInfo : ResourceUnavailable : ( :) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="d852a-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="d852a-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="d852a-169">, InvalidOperationException</span></span>

<span data-ttu-id="d852a-170">\+FullyQualifiedErrorId : NotFoundTestUsers, Microsoft. RTC. Management. synthé</span><span class="sxs-lookup"><span data-stu-id="d852a-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="d852a-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="d852a-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d852a-172">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="d852a-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="d852a-173">Voici quelques-unes des causes courantes de l’échec **de test-CsReplica** :</span><span class="sxs-lookup"><span data-stu-id="d852a-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="d852a-174">Il peut y avoir un problème plus important avec l’agent duplicate et les services de l’agent de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="d852a-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="d852a-175">Les ports requis ne sont peut-être pas ouverts dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="d852a-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="d852a-176">Les groupes de sécurité Active Directory et ordinateur local nécessaires ne sont peut-être pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="d852a-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

