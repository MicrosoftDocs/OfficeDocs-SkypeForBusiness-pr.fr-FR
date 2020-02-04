---
title: 'Lync Server 2013 : test du service de réplicas'
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
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="40064-102">Test du service de réplication dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40064-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40064-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="40064-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40064-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="40064-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="40064-105">Jour</span><span class="sxs-lookup"><span data-stu-id="40064-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40064-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="40064-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="40064-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40064-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40064-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="40064-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="40064-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="40064-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="40064-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="40064-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="40064-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="40064-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="40064-112">Description</span><span class="sxs-lookup"><span data-stu-id="40064-112">Description</span></span>

<span data-ttu-id="40064-113">L’applet de **contrôle test-CsReplica** vérifie que le service de réplica Lync Server 2013 est en cours d’exécution sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="40064-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="40064-114">L’applet de **contrôle test-CsReplica** effectue les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="40064-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="40064-115">vérification de l’état des services de l’agent de réplicateur et de l’agent d’enregistrement centralisé</span><span class="sxs-lookup"><span data-stu-id="40064-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="40064-116">vérification de l’ouverture des ports requis dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="40064-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="40064-117">Il existe des groupes de sécurité de l’ordinateur local et actif nécessaires.</span><span class="sxs-lookup"><span data-stu-id="40064-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="40064-118">Notez que cette applet de cmdlet doit être exécutée localement.</span><span class="sxs-lookup"><span data-stu-id="40064-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="40064-119">C’est-à-dire qu’il doit être exécuté sur le même ordinateur que le service de réplication exécuté.</span><span class="sxs-lookup"><span data-stu-id="40064-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="40064-120">Il n’existe aucune option pour exécuter l’applet de commande **test-CsReplica** sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="40064-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="40064-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="40064-121">Running the test</span></span>

<span data-ttu-id="40064-122">La commande décrite dans l’exemple 1 teste le service de réplica de Lync Server 2013 sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="40064-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="40064-123">Dans cet exemple, le paramètre Verbose est utilisé pour garantir que les informations relatives au test, y compris l’échec éventuel ou le succès du test, ainsi que l’emplacement du rapport généré par le test, s’affichent à l’écran.</span><span class="sxs-lookup"><span data-stu-id="40064-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="40064-124">L’exemple 2 est une variante de la commande décrite dans l’exemple 1.</span><span class="sxs-lookup"><span data-stu-id="40064-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="40064-125">Dans ce cas, le paramètre de rapport est inclus pour spécifier un chemin d’accès et un nom de dossier pour le rapport généré par le test.</span><span class="sxs-lookup"><span data-stu-id="40064-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="40064-126">Si vous ne spécifiez pas de chemin d’accès au rapport, un nom généré automatiquement semblable à ce qui suit s’affiche :</span><span class="sxs-lookup"><span data-stu-id="40064-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="40064-127">C :\\utilisateurs\\administrateur. litwareinc\\AppData\\local\\Temp\\1\\test-CS-réplique-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="40064-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="40064-128">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="40064-128">Determining success or failure</span></span>

<span data-ttu-id="40064-129">Insérez le corps de la section ici.</span><span class="sxs-lookup"><span data-stu-id="40064-129">Insert section body here.</span></span>

<span data-ttu-id="40064-130">DÉTAILLÉ : création d’un nouveau fichier journal "C\\:\\les\\utilisateurs\\testent AppData Local\\Temp\\test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="40064-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="40064-131">DÉTAILLÉ : création d’un nouveau fichier journal "C\\:\\les\\utilisateurs\\testent AppData Local\\Temp\\test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="40064-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="40064-132">DÉTAILLÉ : le traitement de « test-CsReplica » s’est terminé correctement.</span><span class="sxs-lookup"><span data-stu-id="40064-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="40064-133">DÉTAILLÉ : des résultats détaillés sont disponibles à l’adresse «\\C\\:\\utilisateurs\\test\\de\\AppData Local Temp test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. Xml ».</span><span class="sxs-lookup"><span data-stu-id="40064-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="40064-134">DÉTAILLÉ : création d’un fichier journal</span><span class="sxs-lookup"><span data-stu-id="40064-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="40064-135">"C :\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="40064-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="40064-136">d3bd0e4a083. Xml».</span><span class="sxs-lookup"><span data-stu-id="40064-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="40064-137">DÉTAILLÉ : création d’un fichier journal</span><span class="sxs-lookup"><span data-stu-id="40064-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="40064-138">"C :\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="40064-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="40064-139">d3bd0e4a083. html».</span><span class="sxs-lookup"><span data-stu-id="40064-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="40064-140">AVERTISSEMENT : test-CsReplica a échoué.</span><span class="sxs-lookup"><span data-stu-id="40064-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="40064-141">AVERTISSEMENT : des résultats détaillés sont disponibles à l’adresse suivante :</span><span class="sxs-lookup"><span data-stu-id="40064-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="40064-142">"C :\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e</span><span class="sxs-lookup"><span data-stu-id="40064-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="40064-143">d3bd0e4a083. html».</span><span class="sxs-lookup"><span data-stu-id="40064-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="40064-144">Test-CsReplica : échec de l’exécution de la commande : l’accès au Registre demandé n’est pas</span><span class="sxs-lookup"><span data-stu-id="40064-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="40064-145">acceptés.</span><span class="sxs-lookup"><span data-stu-id="40064-145">allowed.</span></span>

<span data-ttu-id="40064-146">À la ligne : 1 car : 1</span><span class="sxs-lookup"><span data-stu-id="40064-146">At line:1 char:1</span></span>

<span data-ttu-id="40064-147">\+Test-CsReplica-verbose</span><span class="sxs-lookup"><span data-stu-id="40064-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="40064-148">\+CategoryInfo : InvalidOperation : ( :) \[Test-CsReplica\], sécurité</span><span class="sxs-lookup"><span data-stu-id="40064-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="40064-149">Sauf</span><span class="sxs-lookup"><span data-stu-id="40064-149">Exception</span></span>

<span data-ttu-id="40064-150">\+FullyQualifiedErrorId : ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="40064-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="40064-151">Management. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="40064-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="40064-152">PS C :\\tests\\des utilisateurs\></span><span class="sxs-lookup"><span data-stu-id="40064-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="40064-153">PS C :\\\> test\\des utilisateurs-CsUcwaConference-TargetFqdn "LyncTest. selfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="40064-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="40064-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="40064-154">icrosoft.com"</span></span>

<span data-ttu-id="40064-155">AVERTISSEMENT : impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni</span><span class="sxs-lookup"><span data-stu-id="40064-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="40064-156">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="40064-156">domain name (FQDN).</span></span> <span data-ttu-id="40064-157">Utilisation du numéro de port de bureau par défaut.</span><span class="sxs-lookup"><span data-stu-id="40064-157">Using default Registrar port number.</span></span> <span data-ttu-id="40064-158">Sauf</span><span class="sxs-lookup"><span data-stu-id="40064-158">Exception:</span></span>

<span data-ttu-id="40064-159">System. InvalidOperationException : aucun cluster correspondant détecté dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="40064-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="40064-160">dès</span><span class="sxs-lookup"><span data-stu-id="40064-160">at</span></span>

<span data-ttu-id="40064-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="40064-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="40064-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="40064-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="40064-163">Test-CsUcwaConference : il n’y a aucun utilisateur de test affecté à</span><span class="sxs-lookup"><span data-stu-id="40064-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="40064-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="40064-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="40064-165">Vérifiez la configuration de l’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="40064-165">Verify test user configuration.</span></span>

<span data-ttu-id="40064-166">À la ligne : 1 car : 1</span><span class="sxs-lookup"><span data-stu-id="40064-166">At line:1 char:1</span></span>

<span data-ttu-id="40064-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="40064-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="40064-168">\+CategoryInfo : ResourceUnavailable : ( :) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="40064-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="40064-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="40064-169">, InvalidOperationException</span></span>

<span data-ttu-id="40064-170">\+FullyQualifiedErrorId : NotFoundTestUsers, Microsoft. RTC. Management. synthé</span><span class="sxs-lookup"><span data-stu-id="40064-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="40064-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="40064-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="40064-172">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="40064-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="40064-173">Voici quelques raisons courantes pour lesquelles **les tests-CsReplica** peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="40064-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="40064-174">Il est possible qu’il y ait un problème plus important avec l’agent réplicateur et les services d’agent de connexion centralisés</span><span class="sxs-lookup"><span data-stu-id="40064-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="40064-175">Il est possible que les ports requis ne soient pas ouverts dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="40064-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="40064-176">Le groupe de sécurité des ordinateurs Active Directory et local requis n’existe pas</span><span class="sxs-lookup"><span data-stu-id="40064-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

