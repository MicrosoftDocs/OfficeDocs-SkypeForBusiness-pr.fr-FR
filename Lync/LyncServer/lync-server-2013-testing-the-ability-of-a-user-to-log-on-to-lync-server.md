---
title: 'Lync Server 2013 : test de la capacité d’un utilisateur à se connecter à Lync Server'
description: 'Lync Server 2013 : test de la capacité d’un utilisateur à se connecter à Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556210"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="fd615-103">Test de la capacité d’un utilisateur à se connecter à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd615-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd615-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fd615-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd615-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="fd615-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fd615-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="fd615-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd615-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="fd615-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fd615-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd615-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd615-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="fd615-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fd615-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fd615-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fd615-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="fd615-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="fd615-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="fd615-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fd615-113">Description</span><span class="sxs-lookup"><span data-stu-id="fd615-113">Description</span></span>

<span data-ttu-id="fd615-114">L’applet de commande Test-CsRegistration vous permet de vérifier que les utilisateurs de votre organisation peuvent se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd615-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="fd615-115">Lorsque vous exécutez test-CsRegistration, l’applet de commande tente de se connecter à un utilisateur de test sur Lync Server, puis, si elle réussit, déconnecte cet utilisateur de test du système.</span><span class="sxs-lookup"><span data-stu-id="fd615-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="fd615-116">Tout cela se passe sans aucune intervention de l’utilisateur et ce, sans affecter aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd615-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="fd615-117">Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel qui possède un compte de serveur Lync réel.</span><span class="sxs-lookup"><span data-stu-id="fd615-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="fd615-118">Dans ce cas, le test sera effectué sans interrompre les activités de l’utilisateur réel Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fd615-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="fd615-119">Lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée.</span><span class="sxs-lookup"><span data-stu-id="fd615-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fd615-120">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="fd615-120">Running the test</span></span>

<span data-ttu-id="fd615-121">L’applet de commande Test-CsRegistration peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd615-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="fd615-122">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="fd615-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="fd615-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fd615-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="fd615-124">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="fd615-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="fd615-125">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsRegistration :</span><span class="sxs-lookup"><span data-stu-id="fd615-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="fd615-126">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="fd615-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fd615-127">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="fd615-127">Determining success or failure</span></span>

<span data-ttu-id="fd615-128">Si l’utilisateur spécifié peut se connecter à (puis se déconnecter de) Lync Server, vous recevrez un résultat semblable à celui-ci avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="fd615-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fd615-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd615-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd615-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="fd615-130">Result : Success</span></span>

<span data-ttu-id="fd615-131">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="fd615-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="fd615-132">«</span><span class="sxs-lookup"><span data-stu-id="fd615-132">Error :</span></span>

<span data-ttu-id="fd615-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="fd615-133">Diagnosis :</span></span>

<span data-ttu-id="fd615-134">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="fd615-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fd615-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd615-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd615-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="fd615-136">Result : Failure</span></span>

<span data-ttu-id="fd615-137">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fd615-137">Latency : 00:00:00</span></span>

<span data-ttu-id="fd615-138">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="fd615-138">Error : 404, Not Found</span></span>

<span data-ttu-id="fd615-139">Diagnostic : ErrorCode = 1003, source = ATL-CS-001. litwareinc. com, Reason = l’utilisateur ne</span><span class="sxs-lookup"><span data-stu-id="fd615-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="fd615-140">existe pas</span><span class="sxs-lookup"><span data-stu-id="fd615-140">not exist</span></span>

<span data-ttu-id="fd615-141">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="fd615-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="fd615-142">Par exemple, la sortie précédente indique que le test a échoué, car l’utilisateur spécifié est introuvable.</span><span class="sxs-lookup"><span data-stu-id="fd615-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="fd615-143">Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur auquel cette adresse SIP est attribuée est activée pour Lync Server) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fd615-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="fd615-144">Si Test-CsRegistration échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="fd615-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="fd615-145">Lorsque le paramètre Verbose est inclus, Test-CsRegistration renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd615-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="fd615-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fd615-146">For example:</span></span>

<span data-ttu-id="fd615-147">VERBOSe : activité « enregistrer » démarrée.</span><span class="sxs-lookup"><span data-stu-id="fd615-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="fd615-148">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="fd615-148">Sending Registration request:</span></span>

<span data-ttu-id="fd615-149">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd615-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="fd615-150">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd615-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="fd615-151">Port de serveur d’inscriptions = 5061.</span><span class="sxs-lookup"><span data-stu-id="fd615-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="fd615-152">Le type d’authentification « approuvé » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fd615-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="fd615-153">Une exception’le point de terminaison ne peut pas s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="fd615-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="fd615-154">Voir le code d’erreur pour une raison spécifique» s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="fd615-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="fd615-155">Pile des appels d’exception : at Microsoft. RTC. signalisation. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="fd615-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fd615-156">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="fd615-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="fd615-157">Voici quelques raisons courantes pour lesquelles Test-CsRegistration peut échouer :</span><span class="sxs-lookup"><span data-stu-id="fd615-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="fd615-158">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="fd615-158">You specified an incorrect user account.</span></span> <span data-ttu-id="fd615-159">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fd615-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fd615-160">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd615-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="fd615-161">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="fd615-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="fd615-162">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd615-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="fd615-163">Vous avez spécifié un pool de serveurs d’inscriptions incorrect.</span><span class="sxs-lookup"><span data-stu-id="fd615-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="fd615-164">Vous pouvez renvoyer les noms de domaine complets de vos pools de serveurs d’inscriptions à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fd615-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="fd615-165">Le pool de serveurs d’inscriptions n’est pas disponible actuellement.</span><span class="sxs-lookup"><span data-stu-id="fd615-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="fd615-166">Essayez d’exécuter une commande ping sur le pool pour voir s’il répond :</span><span class="sxs-lookup"><span data-stu-id="fd615-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

