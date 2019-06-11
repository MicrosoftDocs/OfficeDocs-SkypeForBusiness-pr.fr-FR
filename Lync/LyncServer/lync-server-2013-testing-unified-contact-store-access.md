---
title: 'Lync Server 2013: test de l’accès au magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="13d3e-102">Test de l’accès au magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13d3e-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13d3e-103">_**Dernière modification de la rubrique:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="13d3e-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13d3e-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="13d3e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="13d3e-105">Jour</span><span class="sxs-lookup"><span data-stu-id="13d3e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d3e-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="13d3e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="13d3e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13d3e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d3e-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="13d3e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="13d3e-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="13d3e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="13d3e-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="13d3e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="13d3e-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13d3e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="13d3e-112">Description</span><span class="sxs-lookup"><span data-stu-id="13d3e-112">Description</span></span>

<span data-ttu-id="13d3e-113">Le magasin de contacts unifié introduit dans Lync Server 2013 permet aux administrateurs de stocker les contacts d’un utilisateur dans Microsoft Exchange Server 2013 au lieu de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13d3e-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="13d3e-114">Cela permet à l’utilisateur d’accéder au même jeu de contacts dans Outlook Web Access en plus de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="13d3e-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="13d3e-115">(Vous pouvez continuer à stocker vos contacts dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13d3e-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="13d3e-116">Dans ce cas, les utilisateurs doivent tenir compte de deux ensembles de contacts distincts: un pour une utilisation avec Outlook et Outlook Web Access, et un pour une utilisation avec Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="13d3e-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="13d3e-117">Vous pouvez déterminer si les contacts d’un utilisateur ont été déplacés dans le magasin de contacts unifié en exécutant l’applet de **contrôle CsUnifiedContactStore de test** .</span><span class="sxs-lookup"><span data-stu-id="13d3e-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="13d3e-118">L’applet de connexion **test-CsUnifiedContactStore** prend le compte d’utilisateur spécifié, se connecte au magasin de contacts unifié et tente de récupérer un contact pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13d3e-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="13d3e-119">Si aucun contact ne peut être récupéré, la commande échoue avec le message «aucun contact n’a été reçu pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13d3e-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="13d3e-120">Vérifiez qu’il existe des contacts pour l’utilisateur.»</span><span class="sxs-lookup"><span data-stu-id="13d3e-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="13d3e-121">Notez que l’applet **de contrôle test-CsUnifiedContactStore** échoue si l’utilisateur a effectué une migration réussie vers le magasin de contacts unifié, mais qu’aucun contact n’a été trouvé dans sa liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="13d3e-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="13d3e-122">L’utilisateur spécifié doit avoir au moins un contact pour que l’applet de **contrôle test-CsUnifiedContactStore** se termine correctement.</span><span class="sxs-lookup"><span data-stu-id="13d3e-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="13d3e-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="13d3e-123">Running the test</span></span>

<span data-ttu-id="13d3e-124">Les commandes indiquées dans l’exemple ci-dessous déterminent si les contacts\\de l’utilisateur litwareinc kenmyer se trouvent dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="13d3e-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="13d3e-125">Pour ce faire, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’identification d’interface de ligne de commande\\Windows PowerShell pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="13d3e-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="13d3e-126">Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et vérifier que l’applet de contrôle **CsUnifiedContactStore** peut exécuter sa vérification.</span><span class="sxs-lookup"><span data-stu-id="13d3e-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="13d3e-127">La deuxième commande de l’exemple utilise l’objet Credentials fourni ($x) et l’adresse SIP de l’utilisateur litwareinc\\kenmyer pour déterminer si ses contacts sont accessibles dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="13d3e-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="13d3e-128">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="13d3e-128">Determining success or failure</span></span>

<span data-ttu-id="13d3e-129">Si l’accès au magasin de contacts est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="13d3e-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="13d3e-130">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="13d3e-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="13d3e-131">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="13d3e-131">Result : Success</span></span>

<span data-ttu-id="13d3e-132">Latence: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="13d3e-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="13d3e-133">Message d’erreur:</span><span class="sxs-lookup"><span data-stu-id="13d3e-133">Error Message :</span></span>

<span data-ttu-id="13d3e-134">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="13d3e-134">Diagnosis :</span></span>

<span data-ttu-id="13d3e-135">Si l’accès au magasin de contacts n’est pas configuré correctement, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="13d3e-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="13d3e-136">AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni</span><span class="sxs-lookup"><span data-stu-id="13d3e-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="13d3e-137">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="13d3e-137">domain name (FQDN).</span></span> <span data-ttu-id="13d3e-138">Utilisation du numéro de port de bureau par défaut.</span><span class="sxs-lookup"><span data-stu-id="13d3e-138">Using default Registrar port number.</span></span> <span data-ttu-id="13d3e-139">Sauf</span><span class="sxs-lookup"><span data-stu-id="13d3e-139">Exception:</span></span>

<span data-ttu-id="13d3e-140">System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="13d3e-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="13d3e-141">dès</span><span class="sxs-lookup"><span data-stu-id="13d3e-141">at</span></span>

<span data-ttu-id="13d3e-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="13d3e-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="13d3e-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="13d3e-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="13d3e-144">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="13d3e-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="13d3e-145">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="13d3e-145">Result : Failure</span></span>

<span data-ttu-id="13d3e-146">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="13d3e-146">Latency : 00:00:00</span></span>

<span data-ttu-id="13d3e-147">Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="13d3e-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="13d3e-148">ne répond pas correctement après un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="13d3e-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="13d3e-149">échec de la connexion établie, car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="13d3e-149">established connection failed because connected host has</span></span>

<span data-ttu-id="13d3e-150">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="13d3e-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="13d3e-151">Exception interne: une tentative de connexion a échoué, car le</span><span class="sxs-lookup"><span data-stu-id="13d3e-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="13d3e-152">la fête connectée ne répond pas correctement après un délai de</span><span class="sxs-lookup"><span data-stu-id="13d3e-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="13d3e-153">heure ou échec de la connexion en raison d’un hôte connecté</span><span class="sxs-lookup"><span data-stu-id="13d3e-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="13d3e-154">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="13d3e-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="13d3e-155">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="13d3e-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="13d3e-156">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="13d3e-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="13d3e-157">Voici quelques raisons courantes pour lesquelles **les tests-CsUnifiedContactStore** peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="13d3e-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="13d3e-158">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="13d3e-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="13d3e-159">S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="13d3e-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="13d3e-160">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="13d3e-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="13d3e-161">La connexion au magasin de contacts unifié a échoué et la tentative de récupération d’un contact pour l’utilisateur n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="13d3e-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="13d3e-162">Il y a peut-être des problèmes de connectivité réseau.</span><span class="sxs-lookup"><span data-stu-id="13d3e-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13d3e-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13d3e-163">See Also</span></span>


[<span data-ttu-id="13d3e-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="13d3e-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="13d3e-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="13d3e-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

