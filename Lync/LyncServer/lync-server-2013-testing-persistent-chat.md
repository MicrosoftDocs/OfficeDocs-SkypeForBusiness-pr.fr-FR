---
title: 'Lync Server 2013 : test de la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee9869d5e7a5e3a48451478de334ee656543f6f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="5ce7f-102">Test de la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce7f-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ce7f-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="5ce7f-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ce7f-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="5ce7f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5ce7f-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="5ce7f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ce7f-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="5ce7f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5ce7f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ce7f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ce7f-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="5ce7f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5ce7f-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5ce7f-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-cspersistentchatmessage ne</strong> .</span><span class="sxs-lookup"><span data-stu-id="5ce7f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="5ce7f-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="5ce7f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5ce7f-112">Description</span><span class="sxs-lookup"><span data-stu-id="5ce7f-112">Description</span></span>

<span data-ttu-id="5ce7f-113">L’applet de commande **test-cspersistentchatmessage ne** vérifie qu’une paire d’utilisateurs de test peut échanger des messages à l’aide du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="5ce7f-114">Pour ce faire, l’applet de commande enregistre les deux utilisateurs sur Lync Server 2013, connecte les utilisateurs à une salle de conversation permanente, échange une paire de messages, puis quitte la salle de conversation et déconnecte les deux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="5ce7f-115">Notez que les appels à cette cmdlet échouent si vous n’avez pas créé de salles de conversation ou si les deux comptes d’utilisateur test ne sont pas affectés d’une stratégie de conversation permanente qui leur accorde l’accès au service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5ce7f-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="5ce7f-116">Running the test</span></span>

<span data-ttu-id="5ce7f-117">Les commandes illustrées dans l’exemple suivant testent la capacité d’une paire d’utilisateurs\\(litwareinc Pilar\\et litwareinc kenmyer) à se connecter à Lync Server 2013, puis à échanger des messages à l’aide du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="5ce7f-118">Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="5ce7f-119">(Étant donné que le nom de\\connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credentials qui en résulte est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="5ce7f-120">La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="5ce7f-121">Avec les objets Credential en main, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et échanger des messages à l’aide de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="5ce7f-122">Pour effectuer cette tâche, la cmdlet **test-cspersistentchatmessage ne** est appelée à l’aide des paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); SenderSipAddress (l’adresse SIP pour le premier utilisateur test); SenderCredential (l’objet Windows PowerShell qui contient les informations d’identification pour ce même utilisateur); ReceiverSipAddress (l’adresse SIP de l’autre utilisateur de test); et ReceiverCredential (l’objet Windows PowerShell qui contient les informations d’identification pour l’autre utilisateur de test).</span><span class="sxs-lookup"><span data-stu-id="5ce7f-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5ce7f-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="5ce7f-123">Determining success or failure</span></span>

<span data-ttu-id="5ce7f-124">Si l’utilisateur spécifié possède une stratégie d’emplacement valide, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:</span><span class="sxs-lookup"><span data-stu-id="5ce7f-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="5ce7f-125">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5ce7f-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5ce7f-126">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="5ce7f-126">Result : Success</span></span>

<span data-ttu-id="5ce7f-127">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5ce7f-127">Latency : 00:00:00</span></span>

<span data-ttu-id="5ce7f-128">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="5ce7f-128">Error Message :</span></span>

<span data-ttu-id="5ce7f-129">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5ce7f-129">Diagnosis :</span></span>

<span data-ttu-id="5ce7f-130">Si les utilisateurs spécifiés ne peuvent pas échanger de messages à l’aide du service de conversation permanente, le résultat est affiché en tant que **défaillance**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="5ce7f-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5ce7f-131">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="5ce7f-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5ce7f-132">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5ce7f-132">domain name (FQDN).</span></span> <span data-ttu-id="5ce7f-133">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-133">Using default Registrar port number.</span></span> <span data-ttu-id="5ce7f-134">Rogation</span><span class="sxs-lookup"><span data-stu-id="5ce7f-134">Exception:</span></span>

<span data-ttu-id="5ce7f-135">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5ce7f-136">Regardez</span><span class="sxs-lookup"><span data-stu-id="5ce7f-136">at</span></span>

<span data-ttu-id="5ce7f-137">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="5ce7f-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5ce7f-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="5ce7f-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5ce7f-139">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5ce7f-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5ce7f-140">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="5ce7f-140">Result : Failure</span></span>

<span data-ttu-id="5ce7f-141">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5ce7f-141">Latency : 00:00:00</span></span>

<span data-ttu-id="5ce7f-142">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="5ce7f-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5ce7f-143">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="5ce7f-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5ce7f-144">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="5ce7f-144">established connection failed because connected host has</span></span>

<span data-ttu-id="5ce7f-145">échec de la \[réponse 2001:4898 : E8 : f39e : 5c9a : ad83:81b3 :\]9944 :: 5061</span><span class="sxs-lookup"><span data-stu-id="5ce7f-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="5ce7f-146">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="5ce7f-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5ce7f-147">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="5ce7f-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5ce7f-148">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="5ce7f-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5ce7f-149">n’a pas répondu</span><span class="sxs-lookup"><span data-stu-id="5ce7f-149">has failed to respond</span></span>

<span data-ttu-id="5ce7f-150">\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944\]:: 5061</span><span class="sxs-lookup"><span data-stu-id="5ce7f-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="5ce7f-151">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5ce7f-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5ce7f-152">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="5ce7f-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="5ce7f-153">Voici quelques-unes des causes courantes de l’échec **de test-cspersistentchatmessage ne** :</span><span class="sxs-lookup"><span data-stu-id="5ce7f-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="5ce7f-154">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5ce7f-155">Les comptes de test requis peuvent ne pas exister ou avoir été correctement créés.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="5ce7f-156">Un problème de réseau est peut-être à l’origine d’un retard inattendu qui a expiré le test.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ce7f-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ce7f-157">See Also</span></span>


[<span data-ttu-id="5ce7f-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce7f-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="5ce7f-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce7f-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="5ce7f-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="5ce7f-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

