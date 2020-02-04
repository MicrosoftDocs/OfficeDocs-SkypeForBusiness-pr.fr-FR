---
title: 'Lync Server 2013 : le test de la fonctionnalité de messagerie instantanée de groupe'
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
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="96096-102">Possibilité de test de faire des conversations de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96096-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96096-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="96096-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96096-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="96096-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="96096-105">Jour</span><span class="sxs-lookup"><span data-stu-id="96096-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96096-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="96096-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="96096-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96096-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96096-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="96096-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="96096-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="96096-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="96096-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="96096-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="96096-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="96096-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="96096-112">Description</span><span class="sxs-lookup"><span data-stu-id="96096-112">Description</span></span>

<span data-ttu-id="96096-113">L’applet de contrôle test-CsGroupIM vérifie que les utilisateurs de votre organisation peuvent organiser des sessions de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="96096-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="96096-114">Lorsque vous exécutez test-CsGroupIM, l’applet de connexion tente de se connecter à un couple d’utilisateurs de test sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96096-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="96096-115">En cas de succès, test-CsGroupIM crée une nouvelle conférence à l’aide du premier utilisateur de test, puis invite le second utilisateur à rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="96096-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="96096-116">Après un échange de messages, les deux utilisateurs sont alors déconnectés du système.</span><span class="sxs-lookup"><span data-stu-id="96096-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="96096-117">Notez que tout cela se produit sans aucune interaction utilisateur, sans affecter les utilisateurs réels.</span><span class="sxs-lookup"><span data-stu-id="96096-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="96096-118">Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel possédant un compte de serveur Lync réel.</span><span class="sxs-lookup"><span data-stu-id="96096-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="96096-119">Dans ce cas, le test sera mené sans interruption pour le véritable Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="96096-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="96096-120">Par exemple, même lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée.</span><span class="sxs-lookup"><span data-stu-id="96096-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="96096-121">De même, le véritable Ken Myer ne recevra pas d’invitation à rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="96096-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="96096-122">Cette invitation sera envoyée au compte de test et acceptée par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="96096-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="96096-123">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="96096-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="96096-124">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="96096-124">Running the test</span></span>

<span data-ttu-id="96096-125">L’applet de contrôle test-CsGroupIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96096-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="96096-126">Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="96096-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="96096-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="96096-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="96096-128">Pour exécuter cette vérification à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="96096-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="96096-129">Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsGroupIM :</span><span class="sxs-lookup"><span data-stu-id="96096-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="96096-130">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="96096-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="96096-131">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="96096-131">Determining Success or Failure</span></span>

<span data-ttu-id="96096-132">Si les deux utilisateurs peuvent terminer une session de messagerie instantanée de groupe, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie :**</span><span class="sxs-lookup"><span data-stu-id="96096-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="96096-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96096-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96096-134">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="96096-134">Result : Success</span></span>

<span data-ttu-id="96096-135">Latence : 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="96096-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="96096-136">Error</span><span class="sxs-lookup"><span data-stu-id="96096-136">Error :</span></span>

<span data-ttu-id="96096-137">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="96096-137">Diagnosis :</span></span>

<span data-ttu-id="96096-138">Si les deux utilisateurs ne peuvent pas mettre fin à la session de messagerie instantanée, le résultat s’affichera en panne et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="96096-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="96096-139">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96096-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96096-140">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="96096-140">Result : Failure</span></span>

<span data-ttu-id="96096-141">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="96096-141">Latency : 00:00:00</span></span>

<span data-ttu-id="96096-142">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="96096-142">Error : 404, Not Found</span></span>

<span data-ttu-id="96096-143">Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="96096-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="96096-144">Raison = URI de destination non activé pour le SIP ou non</span><span class="sxs-lookup"><span data-stu-id="96096-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="96096-145">Il.</span><span class="sxs-lookup"><span data-stu-id="96096-145">exist.</span></span>

<span data-ttu-id="96096-146">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="96096-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="96096-147">La sortie précédente indique que le test a échoué car au moins un des comptes de test n’est pas valide, car le compte n’existe pas ou parce que l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96096-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="96096-148">Vous pouvez vérifier que le compte existe et que le compte a été activé pour nm-OCS-14-3e en exécutant une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="96096-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="96096-149">Si test-CsGroupIM échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="96096-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="96096-150">Lorsque le paramètre Verbose est inclus, test-CsGroupIM renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité des utilisateurs spécifiés à participer à une session de messagerie instantanée de groupe.</span><span class="sxs-lookup"><span data-stu-id="96096-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="96096-151">Par exemple, si vous constatez qu’un ou plusieurs comptes d’utilisateur ne sont pas valides, vous pouvez réexécuter le test en utilisant le paramètre Verbose et déterminer le compte d’utilisateur qui n’est pas valide :</span><span class="sxs-lookup"><span data-stu-id="96096-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="96096-152">Envoi de la demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="96096-152">Sending Registration request:</span></span>

 <span data-ttu-id="96096-153">Nom de domaine complet cible = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96096-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="96096-154">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96096-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="96096-155">Register port = 5061</span><span class="sxs-lookup"><span data-stu-id="96096-155">Register Port    = 5061</span></span>

<span data-ttu-id="96096-156">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="96096-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="96096-157">Une exception’la connexion a été refusée.</span><span class="sxs-lookup"><span data-stu-id="96096-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="96096-158">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif'</span><span class="sxs-lookup"><span data-stu-id="96096-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="96096-159">Comme vous pouvez le voir dans cet exemple, l’utilisateur qui dispose de l’adresse SIP sip :kenmyer@litwareinc.com n’a pas réussi à se connecter.</span><span class="sxs-lookup"><span data-stu-id="96096-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="96096-160">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="96096-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="96096-161">Voici quelques raisons courantes pour lesquelles les tests-CsGroupIM peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="96096-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="96096-162">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="96096-162">You specified an incorrect user account.</span></span> <span data-ttu-id="96096-163">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="96096-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="96096-164">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96096-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="96096-165">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="96096-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="96096-166">Get-CsUser "sip :kenmyer@litwareinc.com" | Option Sélectionner un objet activée</span><span class="sxs-lookup"><span data-stu-id="96096-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="96096-167">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96096-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="96096-168">Le service de messagerie instantanée n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="96096-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="96096-169">Lync Server vous permet de configurer le système de sorte que la messagerie instantanée ne soit pas disponible si vous n’êtes pas en mesure d’accéder à la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="96096-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="96096-170">Vous pouvez vérifier qu’en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="96096-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="96096-171">Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="96096-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="96096-172">Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="96096-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="96096-173">Le serveur d’archivage n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="96096-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="96096-174">Vous pouvez récupérer le nom de domaine complet (FQDN) de vos serveurs d’archivage à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="96096-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="96096-175">Vous pouvez ensuite exécuter une commande ping sur le serveur approprié pour vérifier qu’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="96096-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="96096-176">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="96096-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

