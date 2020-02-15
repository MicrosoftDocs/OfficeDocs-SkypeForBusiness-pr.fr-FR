---
title: 'Lync Server 2013 : test des appels d’égal à égal PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c172ea79e646e9deec1c56e792d4e7c4df3a26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="def4a-102">Test des appels d’égal à égal RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def4a-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def4a-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="def4a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="def4a-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="def4a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="def4a-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="def4a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def4a-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="def4a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="def4a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="def4a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="def4a-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="def4a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="def4a-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="def4a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="def4a-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsPstnPeerToPeerCall.</span><span class="sxs-lookup"><span data-stu-id="def4a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="def4a-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="def4a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="def4a-112">Description</span><span class="sxs-lookup"><span data-stu-id="def4a-112">Description</span></span>

<span data-ttu-id="def4a-113">L’applet de commande test-CsPstnPeerToPeerCall vérifie la capacité à laquelle une paire d’utilisateurs doit effectuer un appel P2P sur la passerelle PSTN (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="def4a-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="def4a-114">Lorsque vous appelez test-CsPstnPeerToPeerCall, l’applet de commande tente d’abord de se connecter deux utilisateurs de test à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="def4a-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="def4a-115">En supposant que les ouvertures de sessions réussissent, l’utilisateur 1 tentera d’appeler l’utilisateur 2 sur la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="def4a-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="def4a-116">Test-CsPstnPeerToPeerCall effectuera cet appel à l’aide du plan de numérotation, de la stratégie de voix, ainsi que d’autres paramètres de stratégie et de configuration affectés à l’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="def4a-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="def4a-117">Si le test se déroule comme prévu, l’applet de commande vérifie que l’utilisateur 2 a pu répondre à l’appel, puis se déconnecte des deux comptes de test à partir du système.</span><span class="sxs-lookup"><span data-stu-id="def4a-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="def4a-118">Test-CsPstnPeerToPeerCall effectue un appel téléphonique réel, qui vérifie qu’une connexion peut être établie et qui transmet également des codes DTMF sur le réseau pour déterminer si des médias peuvent être envoyés via la connexion.</span><span class="sxs-lookup"><span data-stu-id="def4a-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="def4a-119">L’appel est traité par l’applet de commande elle-même et aucune interruption manuelle de l’appel n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="def4a-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="def4a-120">(Autrement dit, personne ne doit répondre, puis raccrocher le téléphone qui a été appelé.)</span><span class="sxs-lookup"><span data-stu-id="def4a-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="def4a-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="def4a-121">Running the test</span></span>

<span data-ttu-id="def4a-122">La cmdlet Test-CsPstnPeerToPeerCall peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="def4a-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="def4a-123">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="def4a-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="def4a-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="def4a-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="def4a-125">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="def4a-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="def4a-126">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsPstnPeerToPeerCall :</span><span class="sxs-lookup"><span data-stu-id="def4a-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="def4a-127">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="def4a-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="def4a-128">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="def4a-128">Determining success or failure</span></span>

<span data-ttu-id="def4a-129">Si les utilisateurs spécifiés peuvent effectuer un appel P2P, vous recevrez un résultat semblable à celui-ci, la propriété Result étant marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="def4a-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="def4a-130">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="def4a-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="def4a-131">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="def4a-131">Result : Success</span></span>

<span data-ttu-id="def4a-132">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="def4a-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="def4a-133">«</span><span class="sxs-lookup"><span data-stu-id="def4a-133">Error :</span></span>

<span data-ttu-id="def4a-134">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="def4a-134">Diagnosis :</span></span>

<span data-ttu-id="def4a-135">Si les utilisateurs spécifiés ne peuvent pas effectuer un appel P2P, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="def4a-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="def4a-136">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="def4a-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="def4a-137">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="def4a-137">Result : Failure</span></span>

<span data-ttu-id="def4a-138">Latence : 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="def4a-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="def4a-139">Erreur : 403, interdit</span><span class="sxs-lookup"><span data-stu-id="def4a-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="def4a-140">Diagnostic : ErrorCode = 12001, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="def4a-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="def4a-141">Raison = la stratégie de l’utilisateur ne contient pas l’utilisation de l’itinéraire téléphonique</span><span class="sxs-lookup"><span data-stu-id="def4a-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="def4a-142">La sortie précédente indique que le test a échoué car la stratégie de voix attribuée à au moins un des utilisateurs spécifiés n’inclut pas d’utilisation téléphonique.</span><span class="sxs-lookup"><span data-stu-id="def4a-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="def4a-143">(Les utilisations téléphoniques lient les stratégies vocales aux itinéraires des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="def4a-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="def4a-144">Sans une stratégie de voix ni un itinéraire des communications vocales, vous ne pouvez pas passer d’appels sur le RTC.)</span><span class="sxs-lookup"><span data-stu-id="def4a-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="def4a-145">Si test-CsPstnPeerToPeerCall échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="def4a-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="def4a-146">Lorsque le paramètre Verbose est inclus, test-CsPstnPeerToPeerCall renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="def4a-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="def4a-147">Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion au réseau téléphonique commuté (RTC) :</span><span class="sxs-lookup"><span data-stu-id="def4a-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="def4a-148">Établissement de l’appel audio vidéo à « SIP : + 12065551219@litwareinc. com ; user = Phone ».</span><span class="sxs-lookup"><span data-stu-id="def4a-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="def4a-149">Une exception’A 404 (introuvable) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="def4a-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="def4a-150">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="def4a-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="def4a-151">Voici quelques-unes des causes courantes de l’échec de test-CsPstnPeerToPeerCall :</span><span class="sxs-lookup"><span data-stu-id="def4a-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="def4a-152">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="def4a-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="def4a-153">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="def4a-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="def4a-154">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="def4a-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="def4a-155">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="def4a-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="def4a-156">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="def4a-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="def4a-157">La stratégie de voix attribuée à l’utilisateur spécifié ne dispose pas d’une utilisation PSTN valide.</span><span class="sxs-lookup"><span data-stu-id="def4a-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="def4a-158">Vous pouvez déterminer la stratégie de voix qui est affectée à un utilisateur à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="def4a-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="def4a-159">Vous pouvez ensuite déterminer les utilisations PSTN (le cas échéant) qui sont affectées à cette stratégie à l’aide d’une commande semblable à la suivante, qui récupère des informations sur la stratégie de voix par utilisateur RedmondVoicePolicy :</span><span class="sxs-lookup"><span data-stu-id="def4a-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

