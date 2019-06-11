---
title: 'Lync Server 2013: test de la configuration du serveur LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="adf6c-102">Test de la configuration du serveur LIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adf6c-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adf6c-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="adf6c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adf6c-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="adf6c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="adf6c-105">Jour</span><span class="sxs-lookup"><span data-stu-id="adf6c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adf6c-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="adf6c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="adf6c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="adf6c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adf6c-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="adf6c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="adf6c-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="adf6c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="adf6c-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="adf6c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="adf6c-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="adf6c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="adf6c-112">Description</span><span class="sxs-lookup"><span data-stu-id="adf6c-112">Description</span></span>

<span data-ttu-id="adf6c-113">L’applet de contrôle test-CsLisConfiguration vérifie la possibilité de contacter le service Web LIS.</span><span class="sxs-lookup"><span data-stu-id="adf6c-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="adf6c-114">Si le service Web peut être contacté, le test sera considéré comme ayant réussi, qu’il y ait ou non d’emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="adf6c-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="adf6c-115">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="adf6c-115">Running the test</span></span>

<span data-ttu-id="adf6c-116">Vous pouvez exécuter l’applet de contrôle test-CsLisConfguration à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adf6c-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="adf6c-117">Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="adf6c-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="adf6c-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="adf6c-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="adf6c-119">Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="adf6c-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="adf6c-120">Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="adf6c-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="adf6c-121">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="adf6c-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="adf6c-122">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="adf6c-122">Determining success or failure</span></span>

<span data-ttu-id="adf6c-123">Si le LIS est configuré correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="adf6c-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="adf6c-124">TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="adf6c-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="adf6c-125">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="adf6c-125">liservice.svc</span></span>

<span data-ttu-id="adf6c-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="adf6c-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="adf6c-127">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="adf6c-127">Result : Success</span></span>

<span data-ttu-id="adf6c-128">Latence: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="adf6c-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="adf6c-129">Error</span><span class="sxs-lookup"><span data-stu-id="adf6c-129">Error :</span></span>

<span data-ttu-id="adf6c-130">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="adf6c-130">Diagnosis :</span></span>

<span data-ttu-id="adf6c-131">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="adf6c-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="adf6c-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="adf6c-132">TargetUri :</span></span>

<span data-ttu-id="adf6c-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="adf6c-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="adf6c-134">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="adf6c-134">Result : Failure</span></span>

<span data-ttu-id="adf6c-135">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="adf6c-135">Latency : 00:00:00</span></span>

<span data-ttu-id="adf6c-136">Erreur: 11004, le nom demandé est valide, mais aucune donnée de la requête</span><span class="sxs-lookup"><span data-stu-id="adf6c-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="adf6c-137">type détecté</span><span class="sxs-lookup"><span data-stu-id="adf6c-137">type was found</span></span>

<span data-ttu-id="adf6c-138">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="adf6c-138">Diagnosis :</span></span>

<span data-ttu-id="adf6c-139">Test-CsLisConfiguration: aucun cluster correspondant détecté dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="adf6c-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="adf6c-140">Par exemple, la sortie précédente inclut la remarque «aucun cluster correspondant trouvé dans la topologie».</span><span class="sxs-lookup"><span data-stu-id="adf6c-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="adf6c-141">Il s’agit généralement d’un problème avec le serveur Edge: les LIS utilisant le serveur de périphérie pour se connecter au fournisseur de services et valider les adresses.</span><span class="sxs-lookup"><span data-stu-id="adf6c-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="adf6c-142">Si test-CsLisConfiguration échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose:</span><span class="sxs-lookup"><span data-stu-id="adf6c-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="adf6c-143">Lorsque le paramètre Verbose est inclus, test-CsLisConfiguration renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adf6c-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="adf6c-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="adf6c-144">For example:</span></span>

<span data-ttu-id="adf6c-145">Appel de service d’information d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="adf6c-145">Calling Location Information Service.</span></span>

<span data-ttu-id="adf6c-146">Path du service =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="adf6c-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="adf6c-147">Sous-réseau =</span><span class="sxs-lookup"><span data-stu-id="adf6c-147">Subnet =</span></span>

<span data-ttu-id="adf6c-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="adf6c-148">BssId = 5</span></span>

<span data-ttu-id="adf6c-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="adf6c-149">ChassisId =</span></span>

<span data-ttu-id="adf6c-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="adf6c-150">PortId =</span></span>

<span data-ttu-id="adf6c-151">PortIdSubType = type non défini</span><span class="sxs-lookup"><span data-stu-id="adf6c-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="adf6c-152">Mac</span><span class="sxs-lookup"><span data-stu-id="adf6c-152">Mac</span></span>

<span data-ttu-id="adf6c-153">Une demande de service Web d’information d’emplacement d’exception a échoué avec le code de réponse Item400. '</span><span class="sxs-lookup"><span data-stu-id="adf6c-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="adf6c-154">Il s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTrsnactions. flux de travail. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="adf6c-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="adf6c-155">Si vous examinez soigneusement la sortie précédente, vous verrez que l’applet de la cmdlet a essayé d’appeler le service d’information d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="adf6c-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="adf6c-156">L’un des paramètres qui ont été utilisés dans cet appel est le suivant:</span><span class="sxs-lookup"><span data-stu-id="adf6c-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="adf6c-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="adf6c-157">BssId = 5</span></span>

<span data-ttu-id="adf6c-158">Ce n’est pas une valeur valide pour le champ BssID (Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="adf6c-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="adf6c-159">Au lieu de cela, un BssID doit ressembler à ceci:</span><span class="sxs-lookup"><span data-stu-id="adf6c-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="adf6c-160">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="adf6c-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="adf6c-161">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="adf6c-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="adf6c-162">Voici quelques raisons courantes pour lesquelles les tests-CsLisConfiguration peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="adf6c-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="adf6c-163">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="adf6c-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="adf6c-164">Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="adf6c-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="adf6c-165">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="adf6c-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

