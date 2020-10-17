---
title: 'Lync Server 2013 : test de l’appel audio/vidéo d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8522a1f3a8aedd44a6d39faa0ba6f59ba773677
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504081"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="c3cc7-102">Test des appels audio/vidéo d’égal à égal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cc7-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3cc7-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c3cc7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3cc7-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="c3cc7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c3cc7-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="c3cc7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3cc7-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="c3cc7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c3cc7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3cc7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3cc7-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="c3cc7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c3cc7-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c3cc7-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="c3cc7-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c3cc7-112">Description</span><span class="sxs-lookup"><span data-stu-id="c3cc7-112">Description</span></span>

<span data-ttu-id="c3cc7-113">Test-CsP2PAV est utilisé pour déterminer si une paire d’utilisateurs de test peut participer à une conversation A/V P2P.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="c3cc7-114">Pour tester ce scénario, la cmdlet démarre en ouvrant une session sur les deux utilisateurs sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="c3cc7-115">Si les deux connexions réussissent, le premier utilisateur invite alors le deuxième à participer à un appel audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="c3cc7-116">Le deuxième utilisateur accepte l’appel, la connexion entre les deux utilisateurs est testée, puis l’appel est mené à son terme et enfin les utilisateurs de test sont déconnectés du système.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="c3cc7-117">Test-CsP2PAV n’effectue pas réellement un appel A/V.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="c3cc7-118">Les informations multimédias ne sont pas échangées entre les utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="c3cc7-119">Au lieu de cela, l’applet de commande vérifie simplement que les connexions appropriées peuvent être établies et que les deux utilisateurs peuvent effectuer un tel appel.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="c3cc7-120">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="c3cc7-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c3cc7-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="c3cc7-121">Running the test</span></span>

<span data-ttu-id="c3cc7-122">La cmdlet Test-CsP2PAV peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="c3cc7-123">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="c3cc7-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c3cc7-125">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c3cc7-126">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsP2PAV :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c3cc7-127">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="c3cc7-127">Determining success or failure</span></span>

<span data-ttu-id="c3cc7-128">Si les deux utilisateurs de test peuvent effectuer un appel A/V P2P, vous recevrez un résultat similaire à celui-ci avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="c3cc7-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c3cc7-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3cc7-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c3cc7-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="c3cc7-130">Result : Success</span></span>

<span data-ttu-id="c3cc7-131">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="c3cc7-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="c3cc7-132">«</span><span class="sxs-lookup"><span data-stu-id="c3cc7-132">Error :</span></span>

<span data-ttu-id="c3cc7-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="c3cc7-133">Diagnosis :</span></span>

<span data-ttu-id="c3cc7-134">Si les utilisateurs test ne peuvent pas effectuer l’appel, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c3cc7-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3cc7-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c3cc7-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="c3cc7-136">Result : Failure</span></span>

<span data-ttu-id="c3cc7-137">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c3cc7-137">Latency : 00:00:00</span></span>

<span data-ttu-id="c3cc7-138">Erreur : 480, temporairement indisponible</span><span class="sxs-lookup"><span data-stu-id="c3cc7-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="c3cc7-139">Diagnostic : ErrorCode = 15030, source = ATL-CS-001. litwareinc. com, Reason = failed</span><span class="sxs-lookup"><span data-stu-id="c3cc7-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="c3cc7-140">pour acheminer vers Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c3cc7-140">to route to Exchange Server</span></span>

<span data-ttu-id="c3cc7-141">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="c3cc7-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="c3cc7-142">Par exemple, la sortie précédente indique que le test a échoué, car le serveur Microsoft Exchange n’a pas pu être contacté.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="c3cc7-143">Ce message d’erreur indique généralement un problème de configuration de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="c3cc7-144">Si Test-CsP2PAV échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="c3cc7-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="c3cc7-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="c3cc7-146">Lorsque le paramètre Verbose est inclus, Test-CsP2PAV renvoie un compte pas à pas de chaque action qu’il a effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="c3cc7-147">Par exemple, supposons que votre test a échoué avec le diagnostic suivant :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="c3cc7-148">ErrorCode = 6003, source = ATL-CS-001. litwareinc. com, Reason = non pris en charge par la requête de boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="c3cc7-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="c3cc7-149">Si vous réexécutez Test-CsP2PAV et incluez le paramètre Verbose, vous obtiendrez un résultat semblable à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="c3cc7-150">VERBOSe : activité « enregistrer » démarrée.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="c3cc7-151">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-151">Sending Registration request:</span></span>

<span data-ttu-id="c3cc7-152">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3cc7-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="c3cc7-153">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3cc7-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="c3cc7-154">Port de serveur d’inscriptions = 5062.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="c3cc7-155">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="c3cc7-156">Une exception’le point de terminaison n’a pas pu s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="c3cc7-157">Voir le code d’ErrorCode pour des raisons spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="c3cc7-158">s’est produite lors de l’exécution de flux de travail Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="c3cc7-159">Bien qu’il ne soit pas immédiatement visible, si vous examinez attentivement la sortie, vous verrez qu’un port de serveur d’inscriptions incorrect (port 5062) a été spécifié.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="c3cc7-160">À son tour, ce qui a provoqué l’échec du test.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c3cc7-161">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="c3cc7-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="c3cc7-162">Voici quelques raisons courantes pour lesquelles Test-CsP2PAV peut échouer :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="c3cc7-163">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="c3cc7-164">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="c3cc7-165">Get-CsUser « sip :kenmyer@litwareinc.com »</span><span class="sxs-lookup"><span data-stu-id="c3cc7-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="c3cc7-166">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="c3cc7-167">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="c3cc7-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="c3cc7-168">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3cc7-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

