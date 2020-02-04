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
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="f1a2d-102">Test de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1a2d-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1a2d-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f1a2d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1a2d-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="f1a2d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f1a2d-105">Jour</span><span class="sxs-lookup"><span data-stu-id="f1a2d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1a2d-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="f1a2d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f1a2d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1a2d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1a2d-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="f1a2d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f1a2d-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f1a2d-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="f1a2d-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f1a2d-112">Description</span><span class="sxs-lookup"><span data-stu-id="f1a2d-112">Description</span></span>

<span data-ttu-id="f1a2d-113">L’applet de contrôle test-CsLocationPolicy vérifie qu’une stratégie d’emplacement est attribuée à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="f1a2d-114">La stratégie d’emplacement est utilisée pour appliquer les paramètres liés à la fonctionnalité E9-1-1 et à l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="f1a2d-115">La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si la réponse est « oui », quel est le comportement d’un appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="f1a2d-116">Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro qui compose un appel d’urgence (911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et comment l’appel doit être routé.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="f1a2d-117">Vous pouvez tester des stratégies d’emplacement sur des utilisateurs ou des sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="f1a2d-118">Si vous exécutez le test sur un sous-réseau (en spécifiant une valeur pour le paramètre de sous-réseau), l’applet de contrôle tente de résoudre la stratégie d’emplacement du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="f1a2d-119">Si aucune stratégie d’emplacement n’est affectée au sous-réseau, la stratégie d’emplacement de l’utilisateur configuré sera récupérée.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="f1a2d-120">Si la stratégie de sous-réseau est récupérée correctement, la sortie inclura une valeur LocationPolicyTagID qui commence par le sous-réseau-TagId.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="f1a2d-121">Si une stratégie d’emplacement pour le sous-réseau est introuvable, le LocationPolicyTagID commence par user-TagId.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f1a2d-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="f1a2d-122">Running the test</span></span>

<span data-ttu-id="f1a2d-123">Vous pouvez exécuter l’applet de contrôle test-CsLocationPolicy à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="f1a2d-124">Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f1a2d-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f1a2d-126">Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f1a2d-127">Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsLocationPolicy :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f1a2d-128">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f1a2d-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f1a2d-129">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="f1a2d-129">Determining success or failure</span></span>

<span data-ttu-id="f1a2d-130">Si l’utilisateur spécifié dispose d’une stratégie d’emplacement valide, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie :**</span><span class="sxs-lookup"><span data-stu-id="f1a2d-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f1a2d-131">EnhancedEmergencyServicesEnabled : true</span><span class="sxs-lookup"><span data-stu-id="f1a2d-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="f1a2d-132">LocationPolicyTagID : User-TagId</span><span class="sxs-lookup"><span data-stu-id="f1a2d-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="f1a2d-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f1a2d-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f1a2d-134">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="f1a2d-134">Result : Success</span></span>

<span data-ttu-id="f1a2d-135">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="f1a2d-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f1a2d-136">Error</span><span class="sxs-lookup"><span data-stu-id="f1a2d-136">Error :</span></span>

<span data-ttu-id="f1a2d-137">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="f1a2d-137">Diagnosis :</span></span>

<span data-ttu-id="f1a2d-138">Si une stratégie d’emplacement valide est introuvable pour l’utilisateur spécifié, le résultat sera affiché en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f1a2d-139">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f1a2d-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f1a2d-140">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="f1a2d-140">Result : Failure</span></span>

<span data-ttu-id="f1a2d-141">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f1a2d-141">Latency : 00:00:00</span></span>

<span data-ttu-id="f1a2d-142">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="f1a2d-142">Error : 404, Not Found</span></span>

<span data-ttu-id="f1a2d-143">Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="f1a2d-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="f1a2d-144">Raison = URI de destination non activé pour le SIP ou non</span><span class="sxs-lookup"><span data-stu-id="f1a2d-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="f1a2d-145">Il.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-145">exist.</span></span>

<span data-ttu-id="f1a2d-146">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="f1a2d-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f1a2d-147">La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’est pas valide : le compte n’existe pas, ou l’utilisateur n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="f1a2d-148">Vous pouvez vérifier la validité d’un compte et déterminer s’il a été activé pour nm-OCS-14-3e, en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="f1a2d-149">Si test-CsLocationPolicy échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f1a2d-150">Lorsque le paramètre Verbose est inclus, test-CsLocationPolicy renvoie un compte détaillé de chaque action effectuée lors de la vérification de la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="f1a2d-151">Par exemple, cette sortie indique que Lync Server ne peut pas se connecter à l’utilisateur de test, probablement en raison d’un mot de passe non valide :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="f1a2d-152">Envoi de la demande d’inscription :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-152">Sending Registration request :</span></span>

<span data-ttu-id="f1a2d-153">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f1a2d-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f1a2d-154">Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f1a2d-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f1a2d-155">Port du Bureau d’enregistrement = 5061</span><span class="sxs-lookup"><span data-stu-id="f1a2d-155">Registrar Port = 5061</span></span>

<span data-ttu-id="f1a2d-156">Le type d’authentification « IWA » est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f1a2d-157">Accès à l’enregistrement par SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="f1a2d-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f1a2d-158">Activité « Register » achevée en « 0,0601795 » secondes.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f1a2d-159">Une exception’la connexion a été refusée.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="f1a2d-160">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. '</span><span class="sxs-lookup"><span data-stu-id="f1a2d-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f1a2d-161">s’est produite lors du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f1a2d-162">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="f1a2d-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="f1a2d-163">Voici quelques raisons courantes pour lesquelles les tests-CsLocationPolicy peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="f1a2d-164">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="f1a2d-165">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f1a2d-166">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f1a2d-167">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f1a2d-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f1a2d-168">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1a2d-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

