---
title: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée de groupe'
description: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée de groupe.'
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
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560810"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="9ccc0-103">Test de la fonctionnalité de groupe de messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ccc0-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ccc0-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9ccc0-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ccc0-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="9ccc0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ccc0-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="9ccc0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ccc0-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="9ccc0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ccc0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ccc0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ccc0-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="9ccc0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ccc0-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ccc0-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="9ccc0-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ccc0-113">Description</span><span class="sxs-lookup"><span data-stu-id="9ccc0-113">Description</span></span>

<span data-ttu-id="9ccc0-114">L’applet de commande Test-CsGroupIM vérifie que les utilisateurs de votre organisation peuvent effectuer des sessions de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="9ccc0-115">Lorsque vous exécutez la cmdlet Test-CsGroupIM, l’applet de commande tente de se connecter à une paire d’utilisateurs test à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="9ccc0-116">Si l’opération réussit, Test-CsGroupIM crée une nouvelle conférence à l’aide du premier utilisateur test, puis invite le deuxième utilisateur à participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="9ccc0-117">Après un échange de messages, les deux utilisateurs sont déconnectés du système.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="9ccc0-118">Notez que tout cela se produit sans aucune interaction de l’utilisateur et sans affecter les utilisateurs réels.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="9ccc0-119">Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel qui possède un compte de serveur Lync réel.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="9ccc0-120">Dans ce cas, le test sera effectué sans interrompre les activités de l’utilisateur réel Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="9ccc0-121">Par exemple, même si le compte de test Ken Myer se déconnecte du système Ken Myer, l’utilisateur restera connecté.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="9ccc0-122">De même, le véritable Ken Myer ne reçoit pas d’invitation à participer à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="9ccc0-123">Cette invitation sera envoyée au compte de test et acceptée par ce dernier.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="9ccc0-124">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="9ccc0-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ccc0-125">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="9ccc0-125">Running the test</span></span>

<span data-ttu-id="9ccc0-126">La cmdlet Test-CsGroupIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="9ccc0-127">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9ccc0-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9ccc0-129">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets qui contiennent le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="9ccc0-130">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsGroupIM :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="9ccc0-131">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="9ccc0-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ccc0-132">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="9ccc0-132">Determining Success or Failure</span></span>

<span data-ttu-id="9ccc0-133">Si les deux utilisateurs peuvent effectuer une session de messagerie instantanée de groupe, vous recevrez une sortie semblable à celle-ci avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="9ccc0-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9ccc0-134">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ccc0-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ccc0-135">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="9ccc0-135">Result : Success</span></span>

<span data-ttu-id="9ccc0-136">Latence : 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="9ccc0-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="9ccc0-137">«</span><span class="sxs-lookup"><span data-stu-id="9ccc0-137">Error :</span></span>

<span data-ttu-id="9ccc0-138">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9ccc0-138">Diagnosis :</span></span>

<span data-ttu-id="9ccc0-139">Si les deux utilisateurs ne peuvent pas effectuer la session de messagerie instantanée, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9ccc0-140">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ccc0-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ccc0-141">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="9ccc0-141">Result : Failure</span></span>

<span data-ttu-id="9ccc0-142">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9ccc0-142">Latency : 00:00:00</span></span>

<span data-ttu-id="9ccc0-143">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="9ccc0-143">Error : 404, Not Found</span></span>

<span data-ttu-id="9ccc0-144">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="9ccc0-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="9ccc0-145">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="9ccc0-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="9ccc0-146">présent.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-146">exist.</span></span>

<span data-ttu-id="9ccc0-147">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="9ccc0-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9ccc0-148">La sortie précédente indique que le test a échoué car au moins l’un des comptes de test n’était pas valide, car le compte n’existe pas ou parce que l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="9ccc0-149">Vous pouvez vérifier que le compte existe et que le compte a été activé pour nm-OCS-14-3e en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="9ccc0-150">Si Test-CsGroupIM échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9ccc0-151">Lorsque le paramètre Verbose est inclus, Test-CsGroupIM renvoie un compte pas à pas de chaque action effectuée lorsqu’il a vérifié que les utilisateurs spécifiés peuvent participer à une session de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="9ccc0-152">Par exemple, si votre test échoue et que vous êtes informé qu’un ou plusieurs comptes d’utilisateur ne sont pas valides, vous pouvez réexécuter le test à l’aide du paramètre Verbose et déterminer le compte d’utilisateur qui n’est pas valide :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="9ccc0-153">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-153">Sending Registration request:</span></span>

 <span data-ttu-id="9ccc0-154">Nom de domaine complet cible = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ccc0-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="9ccc0-155">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ccc0-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="9ccc0-156">Port d’inscription = 5061</span><span class="sxs-lookup"><span data-stu-id="9ccc0-156">Register Port    = 5061</span></span>

<span data-ttu-id="9ccc0-157">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="9ccc0-158">Une exception’l’ouverture de session a été refusée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="9ccc0-159">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="9ccc0-160">Comme vous pouvez le voir, dans cet exemple, l’utilisateur disposant de l’adresse SIP sip :kenmyer@litwareinc.com n’a pas pu se connecter.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ccc0-161">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="9ccc0-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ccc0-162">Voici quelques raisons courantes pour lesquelles Test-CsGroupIM peut échouer :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="9ccc0-163">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-163">You specified an incorrect user account.</span></span> <span data-ttu-id="9ccc0-164">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9ccc0-165">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9ccc0-166">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="9ccc0-167">Get-CsUser « sip :kenmyer@litwareinc.com » | Select-Object activé</span><span class="sxs-lookup"><span data-stu-id="9ccc0-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="9ccc0-168">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="9ccc0-169">Le service de messagerie instantanée n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="9ccc0-170">Avec Lync Server, vous pouvez configurer le système de sorte que la messagerie instantanée ne soit pas disponible si la base de données d’archivage est inaccessible.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="9ccc0-171">Vous pouvez vérifier qu’en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="9ccc0-172">Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="9ccc0-173">Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="9ccc0-174">Le serveur d’archivage n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="9ccc0-175">Vous pouvez récupérer le nom de domaine complet de vos serveurs d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="9ccc0-176">Vous pouvez ensuite exécuter la commande ping sur le serveur approprié pour vérifier qu’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="9ccc0-177">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

