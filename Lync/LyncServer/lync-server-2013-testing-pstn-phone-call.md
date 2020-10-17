---
title: 'Lync Server 2013 : test de l’appel téléphonique RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc46703118d27533ac2afd2b4b448ad9516bdd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503971"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="db869-102">Test de l’appel téléphonique RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db869-102">Testing PSTN phone call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db869-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="db869-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db869-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="db869-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="db869-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="db869-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db869-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="db869-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="db869-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db869-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db869-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="db869-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="db869-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="db869-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="db869-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="db869-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="db869-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="db869-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="db869-112">Description</span><span class="sxs-lookup"><span data-stu-id="db869-112">Description</span></span>

<span data-ttu-id="db869-113">L’applet de commande Test-CsPstnOutboundCall teste la capacité d’un utilisateur à appeler un numéro de téléphone situé sur le RTC.</span><span class="sxs-lookup"><span data-stu-id="db869-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="db869-114">Lors de l’exécution de test-CsPstnOutboundCall, la cmdlet tente d’abord de connecter l’utilisateur de test à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db869-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="db869-115">Si l’ouverture de session réussit, l’applet de commande tente alors d’effectuer un appel téléphonique via la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="db869-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="db869-116">Cet appel téléphonique sera effectué à l’aide du plan de numérotation, de la stratégie de voix, ainsi que d’autres stratégies et paramètres affectés au compte de test.</span><span class="sxs-lookup"><span data-stu-id="db869-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="db869-117">Lorsque l’appel reçoit une réponse, l’applet de commande envoie des codes DTMF (Dual-Tone Multi-Frequency) sur le réseau pour vérifier la connectivité multimédia.</span><span class="sxs-lookup"><span data-stu-id="db869-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="db869-118">Lors de la réalisation d’un test, Test-CsPstnOutboundCall passe un appel téléphonique réel : le téléphone cible retentit et doit être décroché pour que le test réussisse.</span><span class="sxs-lookup"><span data-stu-id="db869-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="db869-119">Par ailleurs, cet appel doit être conclu manuellement par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="db869-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="db869-120">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="db869-120">Running the test</span></span>

<span data-ttu-id="db869-121">L’applet de commande Test-CsPstnOutboundCall peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db869-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="db869-122">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool Lync Server testé et le numéro de téléphone PSTN appelé.</span><span class="sxs-lookup"><span data-stu-id="db869-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="db869-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="db869-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="db869-124">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="db869-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="db869-125">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsPstnOutboundCall :</span><span class="sxs-lookup"><span data-stu-id="db869-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="db869-126">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="db869-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="db869-127">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="db869-127">Determining success or failure</span></span>

<span data-ttu-id="db869-128">Si l’utilisateur spécifié peut passer l’appel et si l’appel reçoit une réponse, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="db869-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="db869-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db869-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db869-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="db869-130">Result : Success</span></span>

<span data-ttu-id="db869-131">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="db869-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="db869-132">«</span><span class="sxs-lookup"><span data-stu-id="db869-132">Error :</span></span>

<span data-ttu-id="db869-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="db869-133">Diagnosis :</span></span>

<span data-ttu-id="db869-134">Si l’utilisateur spécifié ne peut pas passer l’appel ou si l’appel n’a pas reçu de réponse, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="db869-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="db869-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db869-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db869-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="db869-136">Result : Failure</span></span>

<span data-ttu-id="db869-137">Latence : 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="db869-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="db869-138">Erreur : 403, interdit</span><span class="sxs-lookup"><span data-stu-id="db869-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="db869-139">Diagnostic : ErrorCode = 12001, source = ATL-CS-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="db869-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="db869-140">La stratégie ne contient pas d’utilisation de l’itinéraire téléphonique</span><span class="sxs-lookup"><span data-stu-id="db869-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="db869-141">La sortie précédente indique que le test a échoué car la stratégie de voix attribuée à l’utilisateur spécifié n’inclut pas d’utilisation téléphonique.</span><span class="sxs-lookup"><span data-stu-id="db869-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="db869-142">(Les utilisations téléphoniques lient les stratégies vocales aux itinéraires des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="db869-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="db869-143">Sans une stratégie de voix et un itinéraire de communications vocales correspondant, vous ne pouvez pas effectuer d’appels sur le réseau téléphonique commuté (RTC).)</span><span class="sxs-lookup"><span data-stu-id="db869-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="db869-144">Si Test-CsPstnOutboundCall échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="db869-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="db869-145">Lorsque le paramètre Verbose est inclus, Test-CsPstnOutboundCall renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db869-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="db869-146">Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion au réseau téléphonique commuté (RTC) :</span><span class="sxs-lookup"><span data-stu-id="db869-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="db869-147">Établissement de l’appel audio vidéo à « SIP : + 12065551219@litwareinc. com ; user = Phone ».</span><span class="sxs-lookup"><span data-stu-id="db869-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="db869-148">Une exception’A 404 (introuvable) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="db869-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="db869-149">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="db869-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="db869-150">Voici quelques raisons courantes pour lesquelles Test-CsPstnOutboundCall peut échouer :</span><span class="sxs-lookup"><span data-stu-id="db869-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="db869-151">Vous avez spécifié un compte d’utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="db869-151">You specified an invalid user account.</span></span> <span data-ttu-id="db869-152">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="db869-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="db869-153">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db869-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="db869-154">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="db869-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="db869-155">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db869-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="db869-156">La stratégie de voix attribuée à l’utilisateur spécifié ne dispose pas d’une utilisation PSTN valide.</span><span class="sxs-lookup"><span data-stu-id="db869-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="db869-157">Vous pouvez déterminer la stratégie de voix qui est affectée à un utilisateur à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="db869-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="db869-158">Vous pouvez ensuite déterminer les utilisations PSTN (le cas échéant) qui sont affectées à cette stratégie à l’aide d’une commande semblable à la suivante, qui récupère des informations sur la stratégie de voix par utilisateur RedmondVoicePolicy :</span><span class="sxs-lookup"><span data-stu-id="db869-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

