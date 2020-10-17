---
title: 'Lync Server 2013 : validation des conférences audio/vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503701"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="bc3a6-102">Validation des conférences audio/vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc3a6-102">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc3a6-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bc3a6-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc3a6-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="bc3a6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bc3a6-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="bc3a6-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc3a6-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="bc3a6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bc3a6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc3a6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc3a6-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="bc3a6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bc3a6-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bc3a6-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsAVConference.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="bc3a6-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bc3a6-112">Description</span><span class="sxs-lookup"><span data-stu-id="bc3a6-112">Description</span></span>

<span data-ttu-id="bc3a6-113">L’applet de commande Test-CsAVConference vérifie si deux utilisateurs de test peuvent participer à une conférence audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="bc3a6-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="bc3a6-114">Quand l’applet de commande est exécutée, les deux utilisateurs sont connectés au système.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="bc3a6-115">Une fois qu’ils ont été correctement connectés, le premier utilisateur crée une conférence A/V, puis attend que le deuxième utilisateur rejoigne la Conférence.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="bc3a6-116">Après un bref échange de données, la conférence est supprimée et les deux utilisateurs de test sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="bc3a6-117">Notez que Test-CsAVConference n’effectue pas de conférence A/V réelle entre les deux utilisateurs test.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="bc3a6-118">Au lieu de cela, l’applet de commande vérifie que les deux utilisateurs peuvent effectuer toutes les connexions nécessaires pour mener une telle conférence.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="bc3a6-119">Vous trouverez d’autres exemples pour cette commande à la rubrique [test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="bc3a6-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bc3a6-120">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="bc3a6-120">Running the test</span></span>

<span data-ttu-id="bc3a6-121">La cmdlet Test-CsAVConference peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="bc3a6-122">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="bc3a6-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="bc3a6-124">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bc3a6-125">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsqu’ils appellent test-CsAVConference :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="bc3a6-126">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="bc3a6-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bc3a6-127">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="bc3a6-127">Determining Success or Failure</span></span>

<span data-ttu-id="bc3a6-128">Si les utilisateurs spécifiés peuvent réussir une conférence A/V, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="bc3a6-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bc3a6-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bc3a6-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="bc3a6-130">Result : Success</span></span>

<span data-ttu-id="bc3a6-131">Latence : 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="bc3a6-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="bc3a6-132">«</span><span class="sxs-lookup"><span data-stu-id="bc3a6-132">Error :</span></span>

<span data-ttu-id="bc3a6-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="bc3a6-133">Diagnosis :</span></span>

<span data-ttu-id="bc3a6-134">Si les utilisateurs ne peuvent pas terminer la Conférence, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bc3a6-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bc3a6-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="bc3a6-136">Result : Failure</span></span>

<span data-ttu-id="bc3a6-137">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bc3a6-137">Latency : 00:00:00</span></span>

<span data-ttu-id="bc3a6-138">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="bc3a6-138">Error : 404, Not Found</span></span>

<span data-ttu-id="bc3a6-139">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="bc3a6-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="bc3a6-140">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="bc3a6-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="bc3a6-141">présent.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-141">exist.</span></span>

<span data-ttu-id="bc3a6-142">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="bc3a6-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="bc3a6-143">Par exemple, la sortie précédente indique que le test a échoué car au moins l’un des deux comptes d’utilisateur n’était pas valide, car le compte n’existe pas ou parce que le compte n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="bc3a6-144">Vous pouvez vérifier l’existence des deux comptes de test et savoir s’ils ont été activés pour Lync Server, en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="bc3a6-145">Si Test-CsAVConference échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="bc3a6-146">Lorsque le paramètre Verbose est inclus Test-CsAVConference renvoie un compte pas à pas de chaque action effectuée lorsqu’il a vérifié que les utilisateurs spécifiés sont en mesure de participer à une conférence AV.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="bc3a6-147">Par exemple, supposons que votre test échoue et que vous recevez le diagnostic suivant :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="bc3a6-148">ErrorCode = 1008, source = accessproxy. litwareinc. com, Reason = impossible de résoudre l’enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="bc3a6-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="bc3a6-149">Si vous réexécutez le test à l’aide du paramètre Verbose, les informations pas à pas renvoyées incluent une sortie semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="bc3a6-150">VERBOSe : activité « enregistrer » démarrée.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="bc3a6-151">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-151">Sending Registration request:</span></span>

<span data-ttu-id="bc3a6-152">Nom de domaine complet cible = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bc3a6-153">Adresse SIP de l’utilisateur = sip :davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="bc3a6-154">Port de serveur d’inscriptions = 5061.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="bc3a6-155">Le type d’authentification « approuvé » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="bc3a6-156">Activité « Register » démarrée.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-156">'Register' activity started.</span></span>

<span data-ttu-id="bc3a6-157">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-157">Sending Registration request:</span></span>

<span data-ttu-id="bc3a6-158">Nom de domaine complet cible = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bc3a6-159">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc3a6-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="bc3a6-160">Port de serveur d’inscriptions = 5061.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="bc3a6-161">Le type d’authentification « approuvé » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="bc3a6-162">Une exception’le point de terminaison n’a pas pu s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="bc3a6-163">Voir le code d’ErrorCode pour des raisons spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="bc3a6-164">s’est produite pendant le flux de travail</span><span class="sxs-lookup"><span data-stu-id="bc3a6-164">occurred during Workflow</span></span>

<span data-ttu-id="bc3a6-165">La dernière ligne de cette sortie indique que l’utilisateur sip :kenmyer@litwareinc.com n’a pas pu s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="bc3a6-166">Cela signifie que vous devez vérifier que l’adresse SIP sip :kenmyer@litwareinc.com est valide et que l’utilisateur associé est activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bc3a6-167">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="bc3a6-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="bc3a6-168">Voici quelques raisons courantes pour lesquelles Test-CsAVConference peut échouer :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="bc3a6-169">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="bc3a6-170">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="bc3a6-171">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="bc3a6-172">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="bc3a6-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="bc3a6-173">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc3a6-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

