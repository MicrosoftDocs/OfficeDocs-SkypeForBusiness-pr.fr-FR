---
title: 'Lync Server 2013 : test de l’accès au magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34dbf6ede9f58b39df1722e742511ee0844c41f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="4ace5-102">Test de l’accès au magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ace5-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ace5-103">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="4ace5-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ace5-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="4ace5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4ace5-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="4ace5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ace5-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="4ace5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4ace5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ace5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ace5-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4ace5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4ace5-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4ace5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4ace5-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="4ace5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="4ace5-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="4ace5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4ace5-112">Description</span><span class="sxs-lookup"><span data-stu-id="4ace5-112">Description</span></span>

<span data-ttu-id="4ace5-113">Le magasin de contacts unifié introduit dans Lync Server 2013 offre aux administrateurs la possibilité de stocker les contacts d’un utilisateur dans Microsoft Exchange Server 2013 et non dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ace5-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="4ace5-114">Cela permet à l’utilisateur d’accéder au même ensemble de contacts dans Outlook Web Access en plus de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4ace5-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="4ace5-115">(Ou vous pouvez continuer à stocker des contacts dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ace5-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="4ace5-116">Dans ce cas, les utilisateurs doivent conserver deux ensembles de contacts distincts : un pour une utilisation avec Outlook et Outlook Web Access, et un autre pour une utilisation avec Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="4ace5-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="4ace5-117">Vous pouvez déterminer si les contacts d’un utilisateur ont été déplacés vers le magasin de contacts unifié en exécutant l’applet de commande **test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="4ace5-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="4ace5-118">La cmdlet **test-CsUnifiedContactStore** prend le compte d’utilisateur spécifié, se connecte au magasin de contacts unifié et tente de récupérer un contact pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4ace5-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="4ace5-119">Si aucun contact ne peut être récupéré, la commande échoue en même temps que le message «aucun contact n’a été reçu pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4ace5-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="4ace5-120">Veuillez vérifier que l’utilisateur possède des contacts ».</span><span class="sxs-lookup"><span data-stu-id="4ace5-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="4ace5-121">Notez que l’applet de commande **test-CsUnifiedContactStore** échoue si l’utilisateur a effectué une migration vers le magasin de contacts unifié, mais qu’il n’a pas de contacts dans sa liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="4ace5-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="4ace5-122">L’utilisateur spécifié doit disposer d’au moins un contact pour que la cmdlet **test-CsUnifiedContactStore** s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="4ace5-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4ace5-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="4ace5-123">Running the test</span></span>

<span data-ttu-id="4ace5-124">Les commandes indiquées dans l’exemple suivant déterminent si les contacts de l'\\utilisateur litwareinc kenmyer se trouvent dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="4ace5-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="4ace5-125">Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows\\PowerShell pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="4ace5-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="4ace5-126">Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que la cmdlet **test-CsUnifiedContactStore** peut exécuter sa vérification.</span><span class="sxs-lookup"><span data-stu-id="4ace5-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="4ace5-127">La deuxième commande de l’exemple utilise l’objet d’informations d’identification fourni ($x) et l’adresse SIP de l'\\utilisateur litwareinc kenmyer pour déterminer si ses contacts se trouvent dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="4ace5-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4ace5-128">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="4ace5-128">Determining success or failure</span></span>

<span data-ttu-id="4ace5-129">Si l’accès au magasin de contacts est correctement configuré, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="4ace5-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4ace5-130">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4ace5-131">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="4ace5-131">Result : Success</span></span>

<span data-ttu-id="4ace5-132">Latence : 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="4ace5-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="4ace5-133">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="4ace5-133">Error Message :</span></span>

<span data-ttu-id="4ace5-134">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="4ace5-134">Diagnosis :</span></span>

<span data-ttu-id="4ace5-135">Si l’accès au magasin de contacts n’est pas configuré correctement, le résultat est indiqué comme étant un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="4ace5-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4ace5-136">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="4ace5-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="4ace5-137">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4ace5-137">domain name (FQDN).</span></span> <span data-ttu-id="4ace5-138">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="4ace5-138">Using default Registrar port number.</span></span> <span data-ttu-id="4ace5-139">Rogation</span><span class="sxs-lookup"><span data-stu-id="4ace5-139">Exception:</span></span>

<span data-ttu-id="4ace5-140">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="4ace5-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="4ace5-141">Regardez</span><span class="sxs-lookup"><span data-stu-id="4ace5-141">at</span></span>

<span data-ttu-id="4ace5-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="4ace5-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="4ace5-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="4ace5-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="4ace5-144">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4ace5-145">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="4ace5-145">Result : Failure</span></span>

<span data-ttu-id="4ace5-146">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4ace5-146">Latency : 00:00:00</span></span>

<span data-ttu-id="4ace5-147">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="4ace5-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="4ace5-148">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="4ace5-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="4ace5-149">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="4ace5-149">established connection failed because connected host has</span></span>

<span data-ttu-id="4ace5-150">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="4ace5-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="4ace5-151">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="4ace5-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="4ace5-152">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="4ace5-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="4ace5-153">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="4ace5-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="4ace5-154">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="4ace5-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="4ace5-155">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="4ace5-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4ace5-156">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="4ace5-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="4ace5-157">Voici quelques-unes des causes courantes de l’échec **de test-CsUnifiedContactStore** :</span><span class="sxs-lookup"><span data-stu-id="4ace5-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="4ace5-158">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="4ace5-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="4ace5-159">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="4ace5-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="4ace5-160">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="4ace5-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="4ace5-161">La connexion au magasin de contacts unifié a échoué et la tentative de récupération d’un contact pour l’utilisateur n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="4ace5-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="4ace5-162">Il peut y avoir des problèmes de connectivité réseau.</span><span class="sxs-lookup"><span data-stu-id="4ace5-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ace5-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ace5-163">See Also</span></span>


[<span data-ttu-id="4ace5-164">New-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="4ace5-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="4ace5-165">Set-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="4ace5-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

