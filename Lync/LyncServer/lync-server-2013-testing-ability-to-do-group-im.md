---
title: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecb197f7ce8acbd4639be9ee20b93e6008922f3c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="dbb77-102">Test de la fonctionnalité de groupe de messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbb77-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbb77-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="dbb77-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbb77-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="dbb77-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dbb77-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="dbb77-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb77-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="dbb77-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dbb77-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbb77-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb77-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="dbb77-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dbb77-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbb77-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dbb77-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="dbb77-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="dbb77-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="dbb77-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dbb77-112">Description</span><span class="sxs-lookup"><span data-stu-id="dbb77-112">Description</span></span>

<span data-ttu-id="dbb77-113">L’applet de commande test-CsGroupIM vérifie que les utilisateurs de votre organisation peuvent effectuer des sessions de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="dbb77-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="dbb77-114">Lorsque vous exécutez la cmdlet Test-CsGroupIM, l’applet de commande tente de se connecter à une paire d’utilisateurs test à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbb77-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="dbb77-115">Si l’opération réussit, Test-CsGroupIM crée une nouvelle conférence à l’aide du premier utilisateur test, puis invite le deuxième utilisateur à participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dbb77-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="dbb77-116">Après un échange de messages, les deux utilisateurs sont déconnectés du système.</span><span class="sxs-lookup"><span data-stu-id="dbb77-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="dbb77-117">Notez que tout cela se produit sans aucune interaction de l’utilisateur et sans affecter les utilisateurs réels.</span><span class="sxs-lookup"><span data-stu-id="dbb77-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="dbb77-118">Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel qui possède un compte de serveur Lync réel.</span><span class="sxs-lookup"><span data-stu-id="dbb77-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="dbb77-119">Dans ce cas, le test sera effectué sans interrompre les activités de l’utilisateur réel Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="dbb77-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="dbb77-120">Par exemple, même si le compte de test Ken Myer se déconnecte du système Ken Myer, l’utilisateur restera connecté.</span><span class="sxs-lookup"><span data-stu-id="dbb77-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="dbb77-121">De même, le véritable Ken Myer ne reçoit pas d’invitation à participer à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="dbb77-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="dbb77-122">Cette invitation sera envoyée au compte de test et acceptée par ce dernier.</span><span class="sxs-lookup"><span data-stu-id="dbb77-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="dbb77-123">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="dbb77-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dbb77-124">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="dbb77-124">Running the test</span></span>

<span data-ttu-id="dbb77-125">La cmdlet Test-CsGroupIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbb77-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="dbb77-126">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="dbb77-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="dbb77-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dbb77-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="dbb77-128">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets qui contiennent le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="dbb77-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="dbb77-129">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsGroupIM :</span><span class="sxs-lookup"><span data-stu-id="dbb77-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="dbb77-130">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="dbb77-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dbb77-131">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="dbb77-131">Determining Success or Failure</span></span>

<span data-ttu-id="dbb77-132">Si les deux utilisateurs peuvent effectuer une session de messagerie instantanée de groupe, vous recevrez une sortie semblable à celle-ci avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="dbb77-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="dbb77-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dbb77-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dbb77-134">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="dbb77-134">Result : Success</span></span>

<span data-ttu-id="dbb77-135">Latence : 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="dbb77-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="dbb77-136">«</span><span class="sxs-lookup"><span data-stu-id="dbb77-136">Error :</span></span>

<span data-ttu-id="dbb77-137">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="dbb77-137">Diagnosis :</span></span>

<span data-ttu-id="dbb77-138">Si les deux utilisateurs ne peuvent pas effectuer la session de messagerie instantanée, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="dbb77-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dbb77-139">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dbb77-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dbb77-140">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="dbb77-140">Result : Failure</span></span>

<span data-ttu-id="dbb77-141">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dbb77-141">Latency : 00:00:00</span></span>

<span data-ttu-id="dbb77-142">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="dbb77-142">Error : 404, Not Found</span></span>

<span data-ttu-id="dbb77-143">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="dbb77-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="dbb77-144">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="dbb77-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="dbb77-145">présent.</span><span class="sxs-lookup"><span data-stu-id="dbb77-145">exist.</span></span>

<span data-ttu-id="dbb77-146">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="dbb77-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="dbb77-147">La sortie précédente indique que le test a échoué car au moins l’un des comptes de test n’était pas valide, car le compte n’existe pas ou parce que l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbb77-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="dbb77-148">Vous pouvez vérifier que le compte existe et que le compte a été activé pour nm-OCS-14-3e en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="dbb77-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="dbb77-149">Si test-CsGroupIM échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="dbb77-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="dbb77-150">Lorsque le paramètre Verbose est inclus, test-CsGroupIM renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité des utilisateurs spécifiés à participer à une session de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="dbb77-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="dbb77-151">Par exemple, si votre test échoue et que vous êtes informé qu’un ou plusieurs comptes d’utilisateur ne sont pas valides, vous pouvez réexécuter le test à l’aide du paramètre Verbose et déterminer le compte d’utilisateur qui n’est pas valide :</span><span class="sxs-lookup"><span data-stu-id="dbb77-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="dbb77-152">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="dbb77-152">Sending Registration request:</span></span>

 <span data-ttu-id="dbb77-153">Nom de domaine complet cible = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dbb77-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="dbb77-154">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dbb77-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="dbb77-155">Port d’inscription = 5061</span><span class="sxs-lookup"><span data-stu-id="dbb77-155">Register Port    = 5061</span></span>

<span data-ttu-id="dbb77-156">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="dbb77-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="dbb77-157">Une exception’l’ouverture de session a été refusée.</span><span class="sxs-lookup"><span data-stu-id="dbb77-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="dbb77-158">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif.</span><span class="sxs-lookup"><span data-stu-id="dbb77-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="dbb77-159">Comme vous pouvez le voir, dans cet exemple, l’utilisateur disposant de l’adresse SIP sip :kenmyer@litwareinc.com n’a pas pu se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbb77-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dbb77-160">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="dbb77-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="dbb77-161">Voici quelques-unes des causes courantes de l’échec de test-CsGroupIM :</span><span class="sxs-lookup"><span data-stu-id="dbb77-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="dbb77-162">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="dbb77-162">You specified an incorrect user account.</span></span> <span data-ttu-id="dbb77-163">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="dbb77-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="dbb77-164">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbb77-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="dbb77-165">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="dbb77-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="dbb77-166">Get-CsUser "sip :kenmyer@litwareinc.com" | Select-Object Enabled</span><span class="sxs-lookup"><span data-stu-id="dbb77-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="dbb77-167">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbb77-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="dbb77-168">Le service de messagerie instantanée n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="dbb77-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="dbb77-169">Avec Lync Server, vous pouvez configurer le système de sorte que la messagerie instantanée ne soit pas disponible si la base de données d’archivage est inaccessible.</span><span class="sxs-lookup"><span data-stu-id="dbb77-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="dbb77-170">Vous pouvez vérifier qu’en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="dbb77-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="dbb77-171">Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="dbb77-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="dbb77-172">Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="dbb77-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="dbb77-173">Le serveur d’archivage n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="dbb77-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="dbb77-174">Vous pouvez récupérer le nom de domaine complet de vos serveurs d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="dbb77-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="dbb77-175">Vous pouvez ensuite exécuter la commande ping sur le serveur approprié pour vérifier qu’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="dbb77-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="dbb77-176">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dbb77-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

