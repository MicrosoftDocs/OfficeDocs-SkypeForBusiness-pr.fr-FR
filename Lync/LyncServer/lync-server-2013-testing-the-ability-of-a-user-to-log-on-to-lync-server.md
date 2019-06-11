---
title: 'Lync Server 2013: test de la possibilité de connexion d’un utilisateur à Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="22c1c-102">Test de la capacité d’un utilisateur à se connecter à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22c1c-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22c1c-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="22c1c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22c1c-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="22c1c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="22c1c-105">Jour</span><span class="sxs-lookup"><span data-stu-id="22c1c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22c1c-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="22c1c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="22c1c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22c1c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22c1c-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="22c1c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="22c1c-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="22c1c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="22c1c-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="22c1c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="22c1c-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="22c1c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="22c1c-112">Description</span><span class="sxs-lookup"><span data-stu-id="22c1c-112">Description</span></span>

<span data-ttu-id="22c1c-113">L’applet de contrôle test-CsRegistration vous permet de vérifier que les utilisateurs de votre organisation peuvent se connecter au serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="22c1c-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="22c1c-114">Lorsque vous exécutez test-CsRegistration, l’applet de connexion tente de se connecter à un utilisateur de test sur Lync Server, puis, si elle est réussie, déconnecte l’utilisateur de test du système.</span><span class="sxs-lookup"><span data-stu-id="22c1c-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="22c1c-115">Tout cela se produit sans aucune interaction de l’utilisateur, sans affecter les utilisateurs réels.</span><span class="sxs-lookup"><span data-stu-id="22c1c-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="22c1c-116">Par exemple, supposons que le compte de test sip:kenmyer@litwareinc.com correspond à un utilisateur réel possédant un compte de serveur Lync réel.</span><span class="sxs-lookup"><span data-stu-id="22c1c-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="22c1c-117">Dans ce cas, le test sera mené sans interruption pour le véritable Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="22c1c-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="22c1c-118">Lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée.</span><span class="sxs-lookup"><span data-stu-id="22c1c-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="22c1c-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="22c1c-119">Running the test</span></span>

<span data-ttu-id="22c1c-120">Vous pouvez exécuter l’applet de contrôle test-CsRegistration à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22c1c-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="22c1c-121">Pour effectuer cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool d’inscriptions du serveur Lync testé.</span><span class="sxs-lookup"><span data-stu-id="22c1c-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="22c1c-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22c1c-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="22c1c-123">Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="22c1c-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="22c1c-124">Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="22c1c-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="22c1c-125">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="22c1c-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="22c1c-126">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="22c1c-126">Determining success or failure</span></span>

<span data-ttu-id="22c1c-127">Si l’utilisateur spécifié peut se connecter à (et se déconnecter de) Lync Server, vous recevrez une sortie semblable à ce qui suit avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="22c1c-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="22c1c-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22c1c-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="22c1c-129">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="22c1c-129">Result : Success</span></span>

<span data-ttu-id="22c1c-130">Latence: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="22c1c-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="22c1c-131">Error</span><span class="sxs-lookup"><span data-stu-id="22c1c-131">Error :</span></span>

<span data-ttu-id="22c1c-132">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="22c1c-132">Diagnosis :</span></span>

<span data-ttu-id="22c1c-133">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="22c1c-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="22c1c-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22c1c-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="22c1c-135">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="22c1c-135">Result : Failure</span></span>

<span data-ttu-id="22c1c-136">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="22c1c-136">Latency : 00:00:00</span></span>

<span data-ttu-id="22c1c-137">Erreur: 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="22c1c-137">Error : 404, Not Found</span></span>

<span data-ttu-id="22c1c-138">Diagnostic: codeerreur = 1003, source = ATL-CS-001. litwareinc. com, Reason = utilisateur</span><span class="sxs-lookup"><span data-stu-id="22c1c-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="22c1c-139">existe pas</span><span class="sxs-lookup"><span data-stu-id="22c1c-139">not exist</span></span>

<span data-ttu-id="22c1c-140">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="22c1c-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="22c1c-141">Par exemple, l’état précédent de sortie a échoué en raison de l’échec de la recherche de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="22c1c-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="22c1c-142">Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur a activé cette adresse SIP pour Lync Server) en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="22c1c-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="22c1c-143">Si test-CsRegistration échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:</span><span class="sxs-lookup"><span data-stu-id="22c1c-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="22c1c-144">Lorsque le paramètre Verbose est inclus, test-CsRegistration renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22c1c-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="22c1c-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22c1c-145">For example:</span></span>

<span data-ttu-id="22c1c-146">DÉTAILLÉ: activité de’Register’démarrée.</span><span class="sxs-lookup"><span data-stu-id="22c1c-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="22c1c-147">Envoi de la demande d’inscription:</span><span class="sxs-lookup"><span data-stu-id="22c1c-147">Sending Registration request:</span></span>

<span data-ttu-id="22c1c-148">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22c1c-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="22c1c-149">Adresse SIP de l’utilisateur = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22c1c-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="22c1c-150">Port du Bureau d’enregistrement = 5061.</span><span class="sxs-lookup"><span data-stu-id="22c1c-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="22c1c-151">Le type d’authentification «approuvé» est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="22c1c-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="22c1c-152">Exception: le point de terminaison ne peut pas s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="22c1c-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="22c1c-153">Voir le code d’erreur pour une raison précise qu’il s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="22c1c-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="22c1c-154">Pile d’appels d’exception: Microsoft. RTC. signalisation. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="22c1c-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="22c1c-155">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="22c1c-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="22c1c-156">Voici quelques raisons courantes pour lesquelles les tests-CsRegistration peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="22c1c-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="22c1c-157">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="22c1c-157">You specified an incorrect user account.</span></span> <span data-ttu-id="22c1c-158">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="22c1c-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="22c1c-159">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22c1c-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="22c1c-160">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="22c1c-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="22c1c-161">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22c1c-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="22c1c-162">Vous avez spécifié un pool d’inscriptions incorrect.</span><span class="sxs-lookup"><span data-stu-id="22c1c-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="22c1c-163">Vous pouvez renvoyer les noms de domaine complets de vos pools de bureaux d’enregistrement à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="22c1c-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="22c1c-164">Le pool d’inscriptions n’est pas disponible pour le moment.</span><span class="sxs-lookup"><span data-stu-id="22c1c-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="22c1c-165">Essayez d’utiliser la commande ping du pool pour voir s’il répond:</span><span class="sxs-lookup"><span data-stu-id="22c1c-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

