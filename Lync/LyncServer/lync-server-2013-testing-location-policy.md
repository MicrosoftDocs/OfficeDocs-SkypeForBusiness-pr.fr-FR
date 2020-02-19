---
title: 'Lync Server 2013 : test de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2d08cdd1db5607b8565cd6b1cf0317b9db26de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="9617d-102">Test de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9617d-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9617d-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9617d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9617d-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="9617d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9617d-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="9617d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9617d-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="9617d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9617d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9617d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9617d-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="9617d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9617d-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9617d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9617d-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="9617d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="9617d-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9617d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9617d-112">Description</span><span class="sxs-lookup"><span data-stu-id="9617d-112">Description</span></span>

<span data-ttu-id="9617d-113">L’applet de commande test-CsLocationPolicy vérifie qu’une stratégie d’emplacement est attribuée à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9617d-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="9617d-114">La stratégie d’emplacement est utilisée pour appliquer des paramètres liés à la fonctionnalité E9-1-1 et la position du client.</span><span class="sxs-lookup"><span data-stu-id="9617d-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="9617d-115">La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si la réponse est « oui », quel est le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9617d-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="9617d-116">Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro qui constitue un appel d’urgence (911 aux États-Unis), si la sécurité de l’entreprise doit être automatiquement notifiée et comment l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="9617d-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="9617d-117">Vous pouvez tester les stratégies d’emplacement sur les utilisateurs ou les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="9617d-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="9617d-118">Si vous effectuez un test sur un sous-réseau (en spécifiant la valeur pour le paramètre de sous-réseau), l’applet de commande essaiera de résoudre la stratégie d’emplacement pour ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="9617d-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="9617d-119">Si aucune stratégie d’emplacement n’a été assignée au sous-réseau, c’est la stratégie d’emplacement de l’utilisateur configuré qui sera récupérée.</span><span class="sxs-lookup"><span data-stu-id="9617d-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="9617d-120">Si la stratégie de sous-réseau est récupérée, la sortie inclut une valeur LocationPolicyTagID qui commence par Subnet-TagId.</span><span class="sxs-lookup"><span data-stu-id="9617d-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="9617d-121">Si la stratégie d’emplacement pour le sous-réseau n’a pas été récupérée, LocationPolicyTagID commencera par l’identifiant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9617d-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9617d-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="9617d-122">Running the test</span></span>

<span data-ttu-id="9617d-123">La cmdlet Test-CsLocationPolicy peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9617d-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9617d-124">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="9617d-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9617d-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9617d-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9617d-126">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="9617d-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="9617d-127">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsLocationPolicy :</span><span class="sxs-lookup"><span data-stu-id="9617d-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9617d-128">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="9617d-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9617d-129">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="9617d-129">Determining success or failure</span></span>

<span data-ttu-id="9617d-130">Si l’utilisateur spécifié possède une stratégie d’emplacement valide, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="9617d-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9617d-131">EnhancedEmergencyServicesEnabled : true</span><span class="sxs-lookup"><span data-stu-id="9617d-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="9617d-132">LocationPolicyTagID : User-TagId</span><span class="sxs-lookup"><span data-stu-id="9617d-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="9617d-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9617d-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9617d-134">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="9617d-134">Result : Success</span></span>

<span data-ttu-id="9617d-135">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="9617d-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="9617d-136">«</span><span class="sxs-lookup"><span data-stu-id="9617d-136">Error :</span></span>

<span data-ttu-id="9617d-137">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9617d-137">Diagnosis :</span></span>

<span data-ttu-id="9617d-138">S’il n’est pas possible de trouver une stratégie d’emplacement valide pour l’utilisateur spécifié, result est affiché en tant que Failure et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="9617d-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9617d-139">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9617d-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9617d-140">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="9617d-140">Result : Failure</span></span>

<span data-ttu-id="9617d-141">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9617d-141">Latency : 00:00:00</span></span>

<span data-ttu-id="9617d-142">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="9617d-142">Error : 404, Not Found</span></span>

<span data-ttu-id="9617d-143">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="9617d-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="9617d-144">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="9617d-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="9617d-145">présent.</span><span class="sxs-lookup"><span data-stu-id="9617d-145">exist.</span></span>

<span data-ttu-id="9617d-146">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="9617d-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9617d-147">La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’est pas valide : le compte n’existe pas ou l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9617d-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="9617d-148">Vous pouvez vérifier la validité d’un compte et déterminer si ce compte a été activé pour nm-OCS-14-3e, en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9617d-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="9617d-149">Si test-CsLocationPolicy échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="9617d-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9617d-150">Lorsque le paramètre Verbose est inclus, test-CsLocationPolicy renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9617d-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="9617d-151">Par exemple, cette sortie indique que Lync Server n’a pas pu se connecter à l’utilisateur test, probablement parce qu’un mot de passe incorrect a été fourni :</span><span class="sxs-lookup"><span data-stu-id="9617d-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="9617d-152">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="9617d-152">Sending Registration request :</span></span>

<span data-ttu-id="9617d-153">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9617d-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="9617d-154">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9617d-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="9617d-155">Port de serveur d’inscriptions = 5061</span><span class="sxs-lookup"><span data-stu-id="9617d-155">Registrar Port = 5061</span></span>

<span data-ttu-id="9617d-156">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9617d-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="9617d-157">Accès à l’inscription sur SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="9617d-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9617d-158">Activité « Register » terminée dans le « 0,0601795 » secondes.</span><span class="sxs-lookup"><span data-stu-id="9617d-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="9617d-159">Une exception’l’ouverture de session a été refusée.</span><span class="sxs-lookup"><span data-stu-id="9617d-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="9617d-160">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. '</span><span class="sxs-lookup"><span data-stu-id="9617d-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="9617d-161">s’est produite pendant le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="9617d-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9617d-162">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="9617d-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="9617d-163">Voici quelques-unes des causes courantes de l’échec de test-CsLocationPolicy :</span><span class="sxs-lookup"><span data-stu-id="9617d-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="9617d-164">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="9617d-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="9617d-165">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9617d-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9617d-166">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9617d-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9617d-167">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9617d-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9617d-168">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9617d-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

