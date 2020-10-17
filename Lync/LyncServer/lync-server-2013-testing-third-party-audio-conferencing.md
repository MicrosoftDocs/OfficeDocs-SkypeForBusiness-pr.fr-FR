---
title: 'Lync Server 2013 : test de l’audioconférence tierce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503931"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="cd8bd-102">Test de l’audioconférence tierce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd8bd-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd8bd-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="cd8bd-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd8bd-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="cd8bd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cd8bd-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="cd8bd-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd8bd-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="cd8bd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cd8bd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd8bd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd8bd-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="cd8bd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cd8bd-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cd8bd-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="cd8bd-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cd8bd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cd8bd-112">Description</span><span class="sxs-lookup"><span data-stu-id="cd8bd-112">Description</span></span>

<span data-ttu-id="cd8bd-113">Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="cd8bd-114">Entre autres, les fournisseurs de services d’audioconférence permettent aux utilisateurs situés hors site et non connectés au réseau d’entreprise ou à Internet de participer à la partie audio d’une conférence ou d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="cd8bd-115">Souvent, les fournisseurs d’audioconférences proposent des services haut de gamme en direct tels que la traduction, la transcription et une assistance opérateur par conférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="cd8bd-116">La cmdlet **test-CsAudioConferencingProvider** est utilisée pour vérifier qu’un utilisateur est en mesure d’établir une connexion à son fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="cd8bd-117">Notez que cette applet de commande peut être exécutée de deux manières.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="cd8bd-118">De nombreux administrateurs utiliseront les applets de commande CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de serveurs d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="cd8bd-119">Ces utilisateurs de test sont un groupe de deux utilisateurs préconfigurés pour être utilisés avec des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="cd8bd-120">(En général, il s’agit de comptes de test et non de comptes qui appartiennent à des utilisateurs réels.) Si les utilisateurs de test sont configurés pour un pool, les administrateurs peuvent exécuter l’applet de commande **test-CsAudioConferencingProvider** sur ce pool sans avoir à spécifier l’identité (et fournir les informations d’identification pour) du compte d’utilisateur impliqué dans le test.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="cd8bd-121">Les administrateurs peuvent également exécuter l’applet de commande **test-CsAudioConferencingProvider** à l’aide d’un compte d’utilisateur réel.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="cd8bd-122">Si vous décidez d’effectuer le test à l’aide d’un tel compte, vous devrez saisir son nom de connexion et son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cd8bd-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="cd8bd-123">Running the test</span></span>

<span data-ttu-id="cd8bd-124">L’exemple 1 vérifie si un utilisateur de test défini pour le pool atl-cs-001.litwareinc.com est capable de se connecter à son fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="cd8bd-125">Cette commande nécessite qu’au moins un utilisateur test soit défini pour le pool.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="cd8bd-126">Si aucun utilisateur de test n’a été défini pour atl-cs-001.litwareinc.com, la commande échouera ; Cela est dû au fait que l’applet de commande **test-CsAudioConferencingProvider** ne saura pas quel utilisateur utiliser dans le test.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="cd8bd-127">Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification du compte d’utilisateur que la commande doit utiliser lors de la vérification de la connexion avec un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="cd8bd-128">Les commandes indiquées dans l’exemple 2 testent la capacité d’un utilisateur spécifique (litwareinc \\ kenmyer) à se connecter à son fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="cd8bd-129">Pour ce faire, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="cd8bd-130">(Étant donné que le nom de connexion litwareinc \\ kenmyer a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe pour le compte Ken Myer.) L’objet Credentials qui en résulte est stocké dans une variable nommée $credential.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="cd8bd-131">La deuxième commande vérifie ensuite si cet utilisateur peut se connecter à son fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="cd8bd-132">Pour exécuter cette tâche, la cmdlet Test-CsAudioConferencingProvider est appelée, ainsi que trois paramètres : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Ken Myer); et UserSipAddress (adresse SIP correspondant aux informations d’identification de l’utilisateur fourni).</span><span class="sxs-lookup"><span data-stu-id="cd8bd-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cd8bd-133">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="cd8bd-133">Determining success or failure</span></span>

<span data-ttu-id="cd8bd-134">Si le fournisseur de services d’audioconférence est correctement configuré, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="cd8bd-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cd8bd-135">Nom de domaine complet cible : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cd8bd-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="cd8bd-136">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="cd8bd-136">Result : Success</span></span>

<span data-ttu-id="cd8bd-137">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cd8bd-137">Latency : 00:00:00</span></span>

<span data-ttu-id="cd8bd-138">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="cd8bd-138">Error Message :</span></span>

<span data-ttu-id="cd8bd-139">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="cd8bd-139">Diagnosis :</span></span>

<span data-ttu-id="cd8bd-140">Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché comme un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="cd8bd-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cd8bd-141">Nom de domaine complet cible : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cd8bd-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="cd8bd-142">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="cd8bd-142">Result : Failure</span></span>

<span data-ttu-id="cd8bd-143">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cd8bd-143">Latency : 00:00:00</span></span>

<span data-ttu-id="cd8bd-144">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="cd8bd-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="cd8bd-145">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="cd8bd-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="cd8bd-146">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="cd8bd-146">established connection failed because connected host has</span></span>

<span data-ttu-id="cd8bd-147">échec de la réponse \[ 2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 :: \] 5061</span><span class="sxs-lookup"><span data-stu-id="cd8bd-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cd8bd-148">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="cd8bd-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="cd8bd-149">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="cd8bd-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="cd8bd-150">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="cd8bd-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="cd8bd-151">n’a pas répondu</span><span class="sxs-lookup"><span data-stu-id="cd8bd-151">has failed to respond</span></span>

<span data-ttu-id="cd8bd-152">\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 : \] : 5061</span><span class="sxs-lookup"><span data-stu-id="cd8bd-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cd8bd-153">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="cd8bd-153">Diagnosis :</span></span>

<span data-ttu-id="cd8bd-154">Par exemple, la sortie précédente inclut la note « la partie connectée n’a pas répondu correctement » qui indique généralement un problème avec le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cd8bd-155">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="cd8bd-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="cd8bd-156">Voici quelques-unes des causes courantes de l’échec **de test-CsAudioConferencingProvider** :</span><span class="sxs-lookup"><span data-stu-id="cd8bd-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="cd8bd-157">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="cd8bd-158">Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="cd8bd-159">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="cd8bd-160">Notez que le test échoue si l’utilisateur employé par la cmdlet **test-CsAudioConferencingProvider** n’a pas reçu de fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="cd8bd-161">Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="cd8bd-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

