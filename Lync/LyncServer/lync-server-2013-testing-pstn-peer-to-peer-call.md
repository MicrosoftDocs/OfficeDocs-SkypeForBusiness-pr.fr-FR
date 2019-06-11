---
title: 'Lync Server 2013: test de l’appel d’égal à égal PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="82f28-102">Test de l’appel d’égal à égal RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82f28-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82f28-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="82f28-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82f28-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="82f28-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="82f28-105">Jour</span><span class="sxs-lookup"><span data-stu-id="82f28-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82f28-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="82f28-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="82f28-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82f28-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82f28-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="82f28-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="82f28-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="82f28-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="82f28-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsPstnPeerToPeerCall.</span><span class="sxs-lookup"><span data-stu-id="82f28-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="82f28-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82f28-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="82f28-112">Description</span><span class="sxs-lookup"><span data-stu-id="82f28-112">Description</span></span>

<span data-ttu-id="82f28-113">L’applet de contrôle test-CsPstnPeerToPeerCall vérifie la possibilité pour une paire d’utilisateurs d’effectuer un appel d’égal à égal sur la passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="82f28-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="82f28-114">Lorsque vous appelez test-CsPstnPeerToPeerCall, l’applet de connexion tente d’abord de se connecter à deux utilisateurs de test sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f28-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="82f28-115">En supposant que les ouvertures de session aboutissent, l’applet de connexion a alors une tentative d’appel de la part de l’utilisateur 2 par le biais de la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="82f28-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="82f28-116">Test-CsPstnPeerToPeerCall effectue l’appel à l’aide du plan de numérotation, de la stratégie vocale et d’autres paramètres de stratégie et de configuration attribués à l’utilisateur de test.</span><span class="sxs-lookup"><span data-stu-id="82f28-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="82f28-117">Si le test s’exécute comme prévu, l’applet de connexion vérifie que l’utilisateur 2 a pu répondre à l’appel, puis déconnecte les deux comptes de test du système.</span><span class="sxs-lookup"><span data-stu-id="82f28-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="82f28-118">Test-CsPstnPeerToPeerCall effectue un appel téléphonique réel et vérifie qu’il est possible d’établir une connexion et qu’elle transmet également des codes DTMF sur le réseau pour déterminer si le média peut être envoyé sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="82f28-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="82f28-119">L’appel est alors reçu par l’applet de demande et aucune terminaison manuelle de l’appel n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="82f28-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="82f28-120">(Autrement dit, personne ne doit répondre et raccrocher le téléphone appelé.)</span><span class="sxs-lookup"><span data-stu-id="82f28-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="82f28-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="82f28-121">Running the test</span></span>

<span data-ttu-id="82f28-122">L’applet de contrôle test-CsPstnPeerToPeerCall peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f28-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="82f28-123">Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="82f28-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="82f28-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="82f28-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="82f28-125">Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="82f28-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="82f28-126">Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsPstnPeerToPeerCall:</span><span class="sxs-lookup"><span data-stu-id="82f28-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="82f28-127">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="82f28-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="82f28-128">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="82f28-128">Determining success or failure</span></span>

<span data-ttu-id="82f28-129">Si les utilisateurs spécifiés peuvent effectuer un appel d’égal à égal, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="82f28-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="82f28-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="82f28-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="82f28-131">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="82f28-131">Result : Success</span></span>

<span data-ttu-id="82f28-132">Latence: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="82f28-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="82f28-133">Error</span><span class="sxs-lookup"><span data-stu-id="82f28-133">Error :</span></span>

<span data-ttu-id="82f28-134">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="82f28-134">Diagnosis :</span></span>

<span data-ttu-id="82f28-135">Si les utilisateurs spécifiés ne parviennent pas à effectuer un appel d’égal à égal, le résultat est affiché en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="82f28-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="82f28-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="82f28-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="82f28-137">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="82f28-137">Result : Failure</span></span>

<span data-ttu-id="82f28-138">Latence: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="82f28-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="82f28-139">Erreur: 403, interdit</span><span class="sxs-lookup"><span data-stu-id="82f28-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="82f28-140">Diagnostic: codeerreur = 12001, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="82f28-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="82f28-141">Raison = la stratégie utilisateur ne contient pas l’utilisation de l’itinéraire du téléphone</span><span class="sxs-lookup"><span data-stu-id="82f28-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="82f28-142">La sortie précédente indique que le test a échoué, car la stratégie vocale affectée à au moins un des utilisateurs spécifiés n’inclut pas une utilisation du téléphone.</span><span class="sxs-lookup"><span data-stu-id="82f28-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="82f28-143">(Les utilisations du téléphone lient les politiques vocales aux itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="82f28-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="82f28-144">Sans qu’il s’agissait d’une stratégie vocale et d’un itinéraire vocal correspondant, vous ne pouvez pas passer d’appels sur PSTN.)</span><span class="sxs-lookup"><span data-stu-id="82f28-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="82f28-145">Si test-CsPstnPeerToPeerCall échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:</span><span class="sxs-lookup"><span data-stu-id="82f28-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="82f28-146">Lorsque le paramètre Verbose est inclus, test-CsPstnPeerToPeerCall renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f28-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="82f28-147">Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion avec le RTC:</span><span class="sxs-lookup"><span data-stu-id="82f28-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="82f28-148">Etablissement d’un appel vidéo audio sur’SIP: +12065551219@litwareinc.com; utilisateur = téléphone'.</span><span class="sxs-lookup"><span data-stu-id="82f28-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="82f28-149">Une exception «une 404 (non trouvée) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="82f28-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="82f28-150">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="82f28-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="82f28-151">Voici quelques raisons courantes pour lesquelles les tests-CsPstnPeerToPeerCall peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="82f28-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="82f28-152">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="82f28-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="82f28-153">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="82f28-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="82f28-154">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f28-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="82f28-155">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="82f28-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="82f28-156">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82f28-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="82f28-157">La stratégie vocale attribuée à l’utilisateur spécifié ne dispose pas d’une utilisation PSTN valide.</span><span class="sxs-lookup"><span data-stu-id="82f28-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="82f28-158">Vous pouvez déterminer la politique vocale affectée à un utilisateur à l’aide d’une commande similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="82f28-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="82f28-159">Vous pouvez ensuite déterminer les utilisations RTC qui sont affectées à cette stratégie à l’aide d’une commande similaire à ce qui suit, qui extrait des informations sur le RedmondVoicePolicy de stratégie vocale par utilisateur:</span><span class="sxs-lookup"><span data-stu-id="82f28-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

