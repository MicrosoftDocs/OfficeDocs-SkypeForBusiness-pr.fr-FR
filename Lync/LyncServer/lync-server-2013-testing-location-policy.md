---
title: 'Lync Server 2013 : test de la stratégie d’emplacement'
description: 'Lync Server 2013 : test de la stratégie d’emplacement.'
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
ms.openlocfilehash: 4efc7ac6f3beef875ce1496b19b875ff252b145b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560600"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="43f2d-103">Test de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43f2d-103">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43f2d-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="43f2d-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43f2d-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="43f2d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="43f2d-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="43f2d-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f2d-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="43f2d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="43f2d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43f2d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43f2d-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="43f2d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="43f2d-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="43f2d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="43f2d-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="43f2d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="43f2d-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="43f2d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="43f2d-113">Description</span><span class="sxs-lookup"><span data-stu-id="43f2d-113">Description</span></span>

<span data-ttu-id="43f2d-114">L’applet de commande Test-CsLocationPolicy vérifie qu’une stratégie d’emplacement est attribuée à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43f2d-114">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="43f2d-115">La stratégie d’emplacement est utilisée pour appliquer des paramètres liés à la fonctionnalité E9-1-1 et la position du client.</span><span class="sxs-lookup"><span data-stu-id="43f2d-115">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="43f2d-116">La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si la réponse est « oui », quel est le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="43f2d-116">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="43f2d-117">Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro qui constitue un appel d’urgence (911 aux États-Unis), si la sécurité de l’entreprise doit être automatiquement notifiée et comment l’appel doit être acheminé.</span><span class="sxs-lookup"><span data-stu-id="43f2d-117">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="43f2d-118">Vous pouvez tester les stratégies d’emplacement sur les utilisateurs ou les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="43f2d-118">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="43f2d-119">Si vous effectuez un test sur un sous-réseau (en spécifiant la valeur pour le paramètre de sous-réseau), l’applet de commande essaiera de résoudre la stratégie d’emplacement pour ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="43f2d-119">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="43f2d-120">Si aucune stratégie d’emplacement n’a été assignée au sous-réseau, c’est la stratégie d’emplacement de l’utilisateur configuré qui sera récupérée.</span><span class="sxs-lookup"><span data-stu-id="43f2d-120">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="43f2d-121">Si la stratégie de sous-réseau est récupérée, la sortie inclut une valeur LocationPolicyTagID qui commence par Subnet-TagId.</span><span class="sxs-lookup"><span data-stu-id="43f2d-121">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="43f2d-122">Si la stratégie d’emplacement pour le sous-réseau n’a pas été récupérée, LocationPolicyTagID commencera par l’identifiant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43f2d-122">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="43f2d-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="43f2d-123">Running the test</span></span>

<span data-ttu-id="43f2d-124">L’applet de commande Test-CsLocationPolicy peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43f2d-124">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="43f2d-125">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="43f2d-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="43f2d-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="43f2d-126">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="43f2d-127">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="43f2d-127">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="43f2d-128">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsLocationPolicy :</span><span class="sxs-lookup"><span data-stu-id="43f2d-128">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="43f2d-129">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="43f2d-129">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="43f2d-130">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="43f2d-130">Determining success or failure</span></span>

<span data-ttu-id="43f2d-131">Si l’utilisateur spécifié possède une stratégie d’emplacement valide, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="43f2d-131">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="43f2d-132">EnhancedEmergencyServicesEnabled : true</span><span class="sxs-lookup"><span data-stu-id="43f2d-132">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="43f2d-133">LocationPolicyTagID : User-TagId</span><span class="sxs-lookup"><span data-stu-id="43f2d-133">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="43f2d-134">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="43f2d-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="43f2d-135">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="43f2d-135">Result : Success</span></span>

<span data-ttu-id="43f2d-136">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="43f2d-136">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="43f2d-137">«</span><span class="sxs-lookup"><span data-stu-id="43f2d-137">Error :</span></span>

<span data-ttu-id="43f2d-138">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="43f2d-138">Diagnosis :</span></span>

<span data-ttu-id="43f2d-139">S’il n’est pas possible de trouver une stratégie d’emplacement valide pour l’utilisateur spécifié, result est affiché en tant que Failure et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="43f2d-139">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="43f2d-140">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="43f2d-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="43f2d-141">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="43f2d-141">Result : Failure</span></span>

<span data-ttu-id="43f2d-142">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="43f2d-142">Latency : 00:00:00</span></span>

<span data-ttu-id="43f2d-143">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="43f2d-143">Error : 404, Not Found</span></span>

<span data-ttu-id="43f2d-144">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="43f2d-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="43f2d-145">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="43f2d-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="43f2d-146">présent.</span><span class="sxs-lookup"><span data-stu-id="43f2d-146">exist.</span></span>

<span data-ttu-id="43f2d-147">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="43f2d-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="43f2d-148">La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’est pas valide : le compte n’existe pas ou l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43f2d-148">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="43f2d-149">Vous pouvez vérifier la validité d’un compte et déterminer si ce compte a été activé pour nm-OCS-14-3e, en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="43f2d-149">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="43f2d-150">Si Test-CsLocationPolicy échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="43f2d-150">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="43f2d-151">Lorsque le paramètre Verbose est inclus, Test-CsLocationPolicy renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="43f2d-151">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="43f2d-152">Par exemple, cette sortie indique que Lync Server n’a pas pu se connecter à l’utilisateur test, probablement parce qu’un mot de passe incorrect a été fourni :</span><span class="sxs-lookup"><span data-stu-id="43f2d-152">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="43f2d-153">Envoi d’une demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="43f2d-153">Sending Registration request :</span></span>

<span data-ttu-id="43f2d-154">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="43f2d-154">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="43f2d-155">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="43f2d-155">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="43f2d-156">Port de serveur d’inscriptions = 5061</span><span class="sxs-lookup"><span data-stu-id="43f2d-156">Registrar Port = 5061</span></span>

<span data-ttu-id="43f2d-157">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="43f2d-157">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="43f2d-158">Accès à l’inscription sur SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="43f2d-158">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="43f2d-159">Activité « Register » terminée dans le « 0,0601795 » secondes.</span><span class="sxs-lookup"><span data-stu-id="43f2d-159">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="43f2d-160">Une exception’l’ouverture de session a été refusée.</span><span class="sxs-lookup"><span data-stu-id="43f2d-160">An exception 'The log on was denied.</span></span> <span data-ttu-id="43f2d-161">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. '</span><span class="sxs-lookup"><span data-stu-id="43f2d-161">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="43f2d-162">s’est produite pendant le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="43f2d-162">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="43f2d-163">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="43f2d-163">Reasons why the test might have failed</span></span>

<span data-ttu-id="43f2d-164">Voici quelques raisons courantes pour lesquelles Test-CsLocationPolicy peut échouer :</span><span class="sxs-lookup"><span data-stu-id="43f2d-164">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="43f2d-165">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="43f2d-165">You specified a user account that is not valid.</span></span> <span data-ttu-id="43f2d-166">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="43f2d-166">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="43f2d-167">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43f2d-167">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="43f2d-168">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="43f2d-168">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="43f2d-169">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43f2d-169">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

