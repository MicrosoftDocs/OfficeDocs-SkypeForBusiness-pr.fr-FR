---
title: 'Lync Server 2013: test de l’audioconférence tierce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="e27c2-102">Test de l’audioconférence tierce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e27c2-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e27c2-103">_**Dernière modification de la rubrique:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="e27c2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e27c2-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="e27c2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e27c2-105">Jour</span><span class="sxs-lookup"><span data-stu-id="e27c2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e27c2-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="e27c2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e27c2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e27c2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e27c2-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="e27c2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e27c2-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e27c2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e27c2-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="e27c2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="e27c2-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e27c2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e27c2-112">Description</span><span class="sxs-lookup"><span data-stu-id="e27c2-112">Description</span></span>

<span data-ttu-id="e27c2-113">Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises.</span><span class="sxs-lookup"><span data-stu-id="e27c2-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="e27c2-114">Entre autres, il permet aux utilisateurs localisés hors site et non connectés au réseau de l’entreprise ou à Internet, de participer à la partie audio d’une conférence ou d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="e27c2-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="e27c2-115">Les fournisseurs de services d’audioconférence fournissent souvent des services haut de gamme tels que la traduction dynamique, la transcription et l’assistance directe par opérateur.</span><span class="sxs-lookup"><span data-stu-id="e27c2-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="e27c2-116">L’applet de **contrôle test-CsAudioConferencingProvider** est utilisée pour vérifier qu’un utilisateur est en mesure d’établir une connexion à son fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="e27c2-117">Notez que cette applet de cmdlet peut être exécutée d’une des deux manières suivantes.</span><span class="sxs-lookup"><span data-stu-id="e27c2-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="e27c2-118">De nombreux administrateurs utilisent les applets de contrôle CsHealthMonitoringConfiguration pour configurer les utilisateurs de test pour chacun de leurs pools de bureaux d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e27c2-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="e27c2-119">Ces utilisateurs de test représentent une paire de comptes d’utilisateurs préconfigurés pour une utilisation avec des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="e27c2-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="e27c2-120">(En général, il s’agit des comptes de test et non des comptes appartenant aux utilisateurs réels.) Si les utilisateurs de test sont configurés pour un pool, les administrateurs peuvent exécuter l’applet **de connexion test-CsAudioConferencingProvider** sur ce pool sans avoir à spécifier l’identité (et fournir les informations d’identification pour) le compte d’utilisateur impliqué dans le test.</span><span class="sxs-lookup"><span data-stu-id="e27c2-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="e27c2-121">Une autre solution consiste à ce que les administrateurs puissent exécuter l’applet **de contrôle CsAudioConferencingProvider** en utilisant un compte d’utilisateur réel.</span><span class="sxs-lookup"><span data-stu-id="e27c2-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="e27c2-122">Si vous décidez d’effectuer le test en utilisant un compte d’utilisateur réel, vous devez fournir le nom de connexion et le mot de passe pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="e27c2-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e27c2-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="e27c2-123">Running the test</span></span>

<span data-ttu-id="e27c2-124">Exemple 1 vérifie si un utilisateur de test défini pour le pool atl-cs-001.litwareinc.com est en mesure de se connecter à son fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="e27c2-125">Ce contrôle nécessite qu’au moins un utilisateur de test soit défini pour le pool.</span><span class="sxs-lookup"><span data-stu-id="e27c2-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="e27c2-126">Si aucun utilisateur de test n’a été défini pour atl-cs-001.litwareinc.com, la commande échouera. ce n’est pas parce que l’applet de **contrôle de test-CsAudioConferencingProvider** ne connaît pas l’utilisateur à employer dans le test.</span><span class="sxs-lookup"><span data-stu-id="e27c2-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="e27c2-127">Si vous n’avez pas défini les utilisateurs test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification du compte d’utilisateur que la commande doit utiliser pour vérifier la connexion à un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="e27c2-128">Les commandes illustrées dans l’exemple 2 permettent de tester la capacité d’un\\utilisateur spécifique (litwareinc kenmyer) de se connecter à son fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="e27c2-129">Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e27c2-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="e27c2-130">(Dans la mesure où le\\nom de connexion litwareinc kenmyer a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Ken Myer.) L’objet Credentials obtenu est stocké dans une variable nommée $credential.</span><span class="sxs-lookup"><span data-stu-id="e27c2-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="e27c2-131">La deuxième commande vérifie alors que l’utilisateur peut se connecter à son fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="e27c2-132">Pour effectuer cette tâche, l’applet de contrôle test-CsAudioConferencingProvider est appelée, avec trois paramètres: TargetFqdn (nom de domaine complet du pool d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Ken Myer); et UserSipAddress (adresse SIP correspondant aux informations d’identification fournies par l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="e27c2-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e27c2-133">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="e27c2-133">Determining success or failure</span></span>

<span data-ttu-id="e27c2-134">Si le fournisseur de services d’audioconférence est configuré correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="e27c2-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e27c2-135">Nom de domaine complet (FQDN) cible: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e27c2-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e27c2-136">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="e27c2-136">Result : Success</span></span>

<span data-ttu-id="e27c2-137">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e27c2-137">Latency : 00:00:00</span></span>

<span data-ttu-id="e27c2-138">Message d’erreur:</span><span class="sxs-lookup"><span data-stu-id="e27c2-138">Error Message :</span></span>

<span data-ttu-id="e27c2-139">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="e27c2-139">Diagnosis :</span></span>

<span data-ttu-id="e27c2-140">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat s’affichera en tant qu' **échec**et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="e27c2-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e27c2-141">Nom de domaine complet (FQDN) cible: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e27c2-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e27c2-142">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="e27c2-142">Result : Failure</span></span>

<span data-ttu-id="e27c2-143">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e27c2-143">Latency : 00:00:00</span></span>

<span data-ttu-id="e27c2-144">Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="e27c2-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="e27c2-145">ne répond pas correctement après un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="e27c2-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="e27c2-146">échec de la connexion établie, car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="e27c2-146">established connection failed because connected host has</span></span>

<span data-ttu-id="e27c2-147">échec de la \[réponse à 2001:4898: E8: f39e: 5c9a: ad83:81b3\]: 9944:5061</span><span class="sxs-lookup"><span data-stu-id="e27c2-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="e27c2-148">Exception interne: une tentative de connexion a échoué, car le</span><span class="sxs-lookup"><span data-stu-id="e27c2-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="e27c2-149">la fête connectée ne répond pas correctement après un délai de</span><span class="sxs-lookup"><span data-stu-id="e27c2-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="e27c2-150">heure ou échec de la connexion en raison d’un hôte connecté</span><span class="sxs-lookup"><span data-stu-id="e27c2-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="e27c2-151">échec de la réponse</span><span class="sxs-lookup"><span data-stu-id="e27c2-151">has failed to respond</span></span>

<span data-ttu-id="e27c2-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="e27c2-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="e27c2-153">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="e27c2-153">Diagnosis :</span></span>

<span data-ttu-id="e27c2-154">Par exemple, la sortie précédente inclut la remarque «la partie connectée n’a pas répondu correctement», qui indique généralement un problème avec le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e27c2-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e27c2-155">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="e27c2-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="e27c2-156">Voici quelques raisons courantes pour lesquelles **les tests-CsAudioConferencingProvider** peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="e27c2-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="e27c2-157">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="e27c2-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e27c2-158">Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="e27c2-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e27c2-159">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="e27c2-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e27c2-160">Notez que le test échoue si l’utilisateur utilisé par l’applet de **contrôle de test-CsAudioConferencingProvider** n’a pas été affecté à un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e27c2-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="e27c2-161">Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="e27c2-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

