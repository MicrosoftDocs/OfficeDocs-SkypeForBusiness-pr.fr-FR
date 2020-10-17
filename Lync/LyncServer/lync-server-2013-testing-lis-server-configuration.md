---
title: 'Lync Server 2013 : test de la configuration du serveur LIS'
description: 'Lync Server 2013 : test de la configuration du serveur LIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560610"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="db62e-103">Test de la configuration du serveur LIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db62e-103">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db62e-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="db62e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db62e-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="db62e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="db62e-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="db62e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db62e-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="db62e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="db62e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db62e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db62e-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="db62e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="db62e-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="db62e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="db62e-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="db62e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="db62e-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="db62e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="db62e-113">Description</span><span class="sxs-lookup"><span data-stu-id="db62e-113">Description</span></span>

<span data-ttu-id="db62e-114">L’applet de commande Test-CsLisConfiguration vérifie votre capacité à contacter le service Web LIS.</span><span class="sxs-lookup"><span data-stu-id="db62e-114">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="db62e-115">Si le service Web peut être contacté, le test sera considéré comme une réussite, que des emplacements spécifiques puissent être trouvés ou non.</span><span class="sxs-lookup"><span data-stu-id="db62e-115">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="db62e-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="db62e-116">Running the test</span></span>

<span data-ttu-id="db62e-117">L’applet de commande Test-CsLisConfguration peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db62e-117">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="db62e-118">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="db62e-118">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="db62e-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="db62e-119">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="db62e-120">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="db62e-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="db62e-121">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsLisConfiguration :</span><span class="sxs-lookup"><span data-stu-id="db62e-121">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="db62e-122">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="db62e-122">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="db62e-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="db62e-123">Determining success or failure</span></span>

<span data-ttu-id="db62e-124">Si la LIS est configurée correctement, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="db62e-124">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="db62e-125">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="db62e-125">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="db62e-126">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="db62e-126">liservice.svc</span></span>

<span data-ttu-id="db62e-127">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db62e-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db62e-128">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="db62e-128">Result : Success</span></span>

<span data-ttu-id="db62e-129">Latence : 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="db62e-129">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="db62e-130">«</span><span class="sxs-lookup"><span data-stu-id="db62e-130">Error :</span></span>

<span data-ttu-id="db62e-131">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="db62e-131">Diagnosis :</span></span>

<span data-ttu-id="db62e-132">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat s’affiche en panne et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="db62e-132">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="db62e-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="db62e-133">TargetUri :</span></span>

<span data-ttu-id="db62e-134">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db62e-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db62e-135">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="db62e-135">Result : Failure</span></span>

<span data-ttu-id="db62e-136">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="db62e-136">Latency : 00:00:00</span></span>

<span data-ttu-id="db62e-137">Erreur : 11004, le nom demandé est valide, mais aucune donnée de la requête</span><span class="sxs-lookup"><span data-stu-id="db62e-137">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="db62e-138">le type a été trouvé</span><span class="sxs-lookup"><span data-stu-id="db62e-138">type was found</span></span>

<span data-ttu-id="db62e-139">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="db62e-139">Diagnosis :</span></span>

<span data-ttu-id="db62e-140">Test-CsLisConfiguration : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="db62e-140">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="db62e-141">Par exemple, la sortie précédente inclut la note « aucun cluster de correspondance n’a été trouvé dans la topologie ».</span><span class="sxs-lookup"><span data-stu-id="db62e-141">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="db62e-142">Cela indique généralement un problème avec le serveur Edge : la LIS qui utilise le serveur Edge pour se connecter au fournisseur de services et valider les adresses.</span><span class="sxs-lookup"><span data-stu-id="db62e-142">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="db62e-143">Si Test-CsLisConfiguration échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="db62e-143">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="db62e-144">Lorsque le paramètre Verbose est inclus, Test-CsLisConfiguration renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db62e-144">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="db62e-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="db62e-145">For example:</span></span>

<span data-ttu-id="db62e-146">Appel du service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="db62e-146">Calling Location Information Service.</span></span>

<span data-ttu-id="db62e-147">Chemin d’accès du service = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="db62e-147">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="db62e-148">Sous-réseau =</span><span class="sxs-lookup"><span data-stu-id="db62e-148">Subnet =</span></span>

<span data-ttu-id="db62e-149">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="db62e-149">BssId = 5</span></span>

<span data-ttu-id="db62e-150">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="db62e-150">ChassisId =</span></span>

<span data-ttu-id="db62e-151">PortId =</span><span class="sxs-lookup"><span data-stu-id="db62e-151">PortId =</span></span>

<span data-ttu-id="db62e-152">PortIdSubType = type non défini</span><span class="sxs-lookup"><span data-stu-id="db62e-152">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="db62e-153">Mac</span><span class="sxs-lookup"><span data-stu-id="db62e-153">Mac</span></span>

<span data-ttu-id="db62e-154">Une demande de service Web d’informations d’emplacement de l’exception a échoué avec un code de réponse Item400.</span><span class="sxs-lookup"><span data-stu-id="db62e-154">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="db62e-155">s’est produite lors de l’exécution de flux de travail Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.</span><span class="sxs-lookup"><span data-stu-id="db62e-155">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="db62e-156">Si vous examinez attentivement la sortie précédente, vous verrez que l’applet de commande a échoué après avoir tenté d’appeler le service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="db62e-156">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="db62e-157">L’un des paramètres qui ont été utilisés dans cet appel était le suivant :</span><span class="sxs-lookup"><span data-stu-id="db62e-157">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="db62e-158">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="db62e-158">BssId = 5</span></span>

<span data-ttu-id="db62e-159">Il ne s’agit pas d’une valeur valide pour l’identificateur BssID (Basic Service Set Identifier).</span><span class="sxs-lookup"><span data-stu-id="db62e-159">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="db62e-160">Au lieu de cela, un BssID doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="db62e-160">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="db62e-161">12-34-56-78-90-AB</span><span class="sxs-lookup"><span data-stu-id="db62e-161">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="db62e-162">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="db62e-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="db62e-163">Voici quelques raisons courantes pour lesquelles Test-CsLisConfiguration peut échouer :</span><span class="sxs-lookup"><span data-stu-id="db62e-163">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="db62e-164">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="db62e-164">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="db62e-165">Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="db62e-165">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="db62e-166">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="db62e-166">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

