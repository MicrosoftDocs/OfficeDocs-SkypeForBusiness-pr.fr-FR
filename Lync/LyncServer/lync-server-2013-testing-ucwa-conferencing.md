---
title: 'Lync Server 2013 : test de la Conférence UCWA'
description: 'Lync Server 2013 : test des conférences UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f88a683abb67d55211422fc4dcf45fc1d5c966
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556090"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="e2ef3-103">Test de la Conférence UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ef3-103">Testing UCWA conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ef3-104">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="e2ef3-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2ef3-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="e2ef3-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e2ef3-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="e2ef3-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2ef3-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="e2ef3-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e2ef3-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2ef3-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2ef3-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="e2ef3-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e2ef3-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e2ef3-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="e2ef3-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="e2ef3-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="e2ef3-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e2ef3-113">Description</span><span class="sxs-lookup"><span data-stu-id="e2ef3-113">Description</span></span>

<span data-ttu-id="e2ef3-114">L’applet de commande **test-CsUcwaConference** vérifie qu’une paire d’utilisateurs test peut planifier, joindre, puis mener une conférence en ligne à l’aide de l’API Web communications unifiées (UCWA).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-114">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e2ef3-115">Pour ce faire, l’applet de commande utilise le service de ticket Web Lync Server pour authentifier les deux utilisateurs de test et les inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-115">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="e2ef3-116">L’applet de commande commence alors une conférence en se servant des informations d’identification de l’organisateur et invite les participants à se joindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-116">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="e2ef3-117">Une fois la réunion jointe, l’applet de commande **test-CsUcwaConference** vérifie que les utilisateurs peuvent effectuer des actions telles que les pools de messages instantanés et de réunions Exchange, puis déconnecte la Conférence et annule l’inscription des deux utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-117">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="e2ef3-118">La conférence planifiée sera également supprimée une fois le test terminé.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-118">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="e2ef3-119">La cmdlet **test-CsUcwaConference** peut également être utilisée pour déterminer si les utilisateurs anonymes peuvent participer à des conférences en ligne.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-119">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="e2ef3-120">Notez que l’applet de commande **test-CsUcwaConference** ne doit pas être exécutée sur un pool Microsoft Lync Server 2010, sauf si UCWA a été installé sur ce pool.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-120">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="e2ef3-121">Si UCWA n’a pas été installé, l’appel de l’applet de commande **test-CsUcwaConference** échouera.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-121">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e2ef3-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="e2ef3-122">Running the test</span></span>

<span data-ttu-id="e2ef3-p104">La commande présentée dans l’exemple 1 vérifie que deux utilisateurs de test peuvent participer à une conférence UCWA dans le pool atl-cs-001.litwareinc.com. Notez que cette commande échoue si vous n’avez pas défini au préalable deux utilisateurs de test de configuration d’analyse d’intégrité pour atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e2ef3-125">Les commandes indiquées dans l’exemple 2 testent la capacité d’une paire d’utilisateurs (litwareinc \\ Pilar et litwareinc \\ kenmyer) à participer à une conférence UCWA.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-125">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="e2ef3-126">Pour ce faire, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-126">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="e2ef3-127">(Étant donné que le nom de connexion, litwareinc \\ Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credentials qui en résulte est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-127">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="e2ef3-128">La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-128">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="e2ef3-129">Avec les deux objets Credential en main, la troisième commande de l’exemple détermine si les deux utilisateurs peuvent participer à une conférence UCWA.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-129">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="e2ef3-130">Pour exécuter cette tâche, la cmdlet **test-CsUcwaConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); OrganizerSipAddress (adresse SIP de l’organisateur de la réunion); OrganizerCredential (l’objet Windows PowerShell qui contient les informations d’identification pour ce même utilisateur); ParticipantSipAddress (l’adresse SIP de l’autre utilisateur de test); et ParticipantCredential (l’objet interface de ligne de commande Windows PowerShell qui contient les informations d’identification pour l’autre utilisateur).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-130">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e2ef3-131">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="e2ef3-131">Determining success or failure</span></span>

<span data-ttu-id="e2ef3-132">Si la Conférence est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="e2ef3-132">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e2ef3-133">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e2ef3-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e2ef3-134">URI cible : https://LyncTest-SE. LyncTest. SelfHost. Corp.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-134">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="e2ef3-135">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="e2ef3-135">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="e2ef3-136">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="e2ef3-136">Result : Success</span></span>

<span data-ttu-id="e2ef3-137">Latence : 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="e2ef3-137">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="e2ef3-138">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="e2ef3-138">Error Message :</span></span>

<span data-ttu-id="e2ef3-139">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="e2ef3-139">Diagnosis :</span></span>

<span data-ttu-id="e2ef3-140">Si les utilisateurs spécifiés ne peuvent pas utiliser la fonctionnalité de conférence, le résultat est affiché en **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="e2ef3-140">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e2ef3-141">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="e2ef3-141">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="e2ef3-142">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-142">domain name (FQDN).</span></span> <span data-ttu-id="e2ef3-143">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-143">Using default Registrar port number.</span></span> <span data-ttu-id="e2ef3-144">Rogation</span><span class="sxs-lookup"><span data-stu-id="e2ef3-144">Exception:</span></span>

<span data-ttu-id="e2ef3-145">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-145">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="e2ef3-146">Regardez</span><span class="sxs-lookup"><span data-stu-id="e2ef3-146">at</span></span>

<span data-ttu-id="e2ef3-147">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="e2ef3-147">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="e2ef3-148">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="e2ef3-148">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="e2ef3-149">Test-CsUcwaConference : aucun utilisateur de test n’est affecté à</span><span class="sxs-lookup"><span data-stu-id="e2ef3-149">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="e2ef3-150">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="e2ef3-150">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="e2ef3-151">Vérifiez la configuration de l’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-151">Verify test user configuration.</span></span>

<span data-ttu-id="e2ef3-152">À la ligne : 1 char : 1</span><span class="sxs-lookup"><span data-stu-id="e2ef3-152">At line:1 char:1</span></span>

<span data-ttu-id="e2ef3-153">\+ Test-CsUcwaConference-TargetFqdn « LyncTest.SelfHost.Corp.Microsoft.com »</span><span class="sxs-lookup"><span data-stu-id="e2ef3-153">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="e2ef3-154">\+ CategoryInfo : ResourceUnavailable : ( :) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="e2ef3-154">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="e2ef3-155">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="e2ef3-155">, InvalidOperationException</span></span>

<span data-ttu-id="e2ef3-156">\+ FullyQualifiedErrorId : NotFoundTestUsers, Microsoft. RTC. Management. synthé</span><span class="sxs-lookup"><span data-stu-id="e2ef3-156">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="e2ef3-157">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="e2ef3-157">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e2ef3-158">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="e2ef3-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="e2ef3-159">Voici quelques-unes des causes courantes de l’échec **de test-CsUcwaConference** :</span><span class="sxs-lookup"><span data-stu-id="e2ef3-159">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="e2ef3-160">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e2ef3-161">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e2ef3-162">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e2ef3-163">La possibilité d’effectuer une conférence dépend de la stratégie de conférence qui a été attribuée à l’utilisateur qui a organisé la Conférence (dans le cas de la cmdlet **test-CsUcwaConference** , qui est l’expéditeur).</span><span class="sxs-lookup"><span data-stu-id="e2ef3-163">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="e2ef3-164">Si l’organisateur n’est pas autorisé à inclure des activités collaboratives dans sa réunion (par exemple, si la propriété EnableDataCollaboration de sa stratégie de conférence est définie sur false), la cmdlet **test-CsUcwaConference** échouera.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-164">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="e2ef3-165">Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="e2ef3-165">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2ef3-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2ef3-166">See Also</span></span>


[<span data-ttu-id="e2ef3-167">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="e2ef3-167">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="e2ef3-168">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="e2ef3-168">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="e2ef3-169">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="e2ef3-169">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

