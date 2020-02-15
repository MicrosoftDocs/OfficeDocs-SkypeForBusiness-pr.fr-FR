---
title: 'Lync Server 2013 : test de la messagerie à l’aide de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94841a3ec17878258b26fd945aa60123ac76a9c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="5fb85-102">Test de la messagerie à l’aide de XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fb85-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb85-103">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="5fb85-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fb85-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="5fb85-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5fb85-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="5fb85-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb85-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="5fb85-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5fb85-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fb85-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb85-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="5fb85-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5fb85-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5fb85-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5fb85-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="5fb85-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="5fb85-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="5fb85-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5fb85-112">Description</span><span class="sxs-lookup"><span data-stu-id="5fb85-112">Description</span></span>

<span data-ttu-id="5fb85-113">Le protocole XMPP (Extensible Messaging and Presence Protocol) est un protocole de communication standard (fondé sur XML) utilisé pour envoyer des messages sur Internet.</span><span class="sxs-lookup"><span data-stu-id="5fb85-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="5fb85-114">XMPP a été initialement nommé Jabber, et est pris en charge par plusieurs applications de messagerie et de communication Internet, telles que Google Talk et Facebook chat.</span><span class="sxs-lookup"><span data-stu-id="5fb85-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="5fb85-115">L’applet de commande **test-CsXmppIM** vérifie qu’un utilisateur peut échanger des messages instantanés avec un utilisateur sur un réseau XMPP.</span><span class="sxs-lookup"><span data-stu-id="5fb85-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="5fb85-116">Notez que pour que ce test réussisse, vous devez disposer d’une adresse SIP valide pour l’utilisateur XMPP et que l’adresse SIP doit se trouver sur un réseau configuré en tant que partenaire XMPP autorisé.</span><span class="sxs-lookup"><span data-stu-id="5fb85-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5fb85-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="5fb85-117">Running the test</span></span>

<span data-ttu-id="5fb85-118">L’exemple suivant vérifie les fonctionnalités de messagerie instantanée XMPP pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5fb85-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5fb85-119">Cette commande fonctionne uniquement si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5fb85-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5fb85-120">Si c’est le cas, la commande détermine si le premier utilisateur test peut envoyer un message instantané XMPP à un utilisateur disposant de l’adresse SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5fb85-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="5fb85-121">Si les utilisateurs de test ne sont pas définis, la commande échoue, car elle ne peut pas identifier l’utilisateur sous lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="5fb85-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="5fb85-122">Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.</span><span class="sxs-lookup"><span data-stu-id="5fb85-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="5fb85-123">Les commandes présentées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (\\litwareinc Pilar) à se connecter pour envoyer un message instantané XMPP à l’utilisateur adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5fb85-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="5fb85-124">Pour ce faire, la première commande de l’exemple utilise la cmdlet Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="5fb85-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="5fb85-125">(Étant donné que le nom\\de connexion litwareinc Pilar a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="5fb85-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="5fb85-126">La deuxième commande vérifie ensuite si cet utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et envoyer le message instantané XMPP.</span><span class="sxs-lookup"><span data-stu-id="5fb85-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="5fb85-127">Pour exécuter cette tâche, la cmdlet **test-CsXmppIm** est appelée, avec quatre paramètres : TargetFqdn (le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions); Récepteur (adresse SIP de l’utilisateur auquel le message est adressé); UserCredential (l’objet Windows PowerShell qui contient les informations d’identification de l’utilisateur de Pilar Ackerman); et UserSipAddress (l’adresse SIP qui correspond aux informations d’identification de l’utilisateur fourni).</span><span class="sxs-lookup"><span data-stu-id="5fb85-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5fb85-128">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="5fb85-128">Determining success or failure</span></span>

<span data-ttu-id="5fb85-129">Si la messagerie instantanée XMPP est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="5fb85-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5fb85-130">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5fb85-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5fb85-131">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="5fb85-131">Result : Success</span></span>

<span data-ttu-id="5fb85-132">Latence : 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="5fb85-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="5fb85-133">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="5fb85-133">Error Message :</span></span>

<span data-ttu-id="5fb85-134">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5fb85-134">Diagnosis :</span></span>

<span data-ttu-id="5fb85-135">Si les utilisateurs spécifiés ne peuvent pas utiliser la messagerie instantanée XMPP, le résultat est affiché en **panne**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="5fb85-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5fb85-136">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="5fb85-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5fb85-137">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5fb85-137">domain name (FQDN).</span></span> <span data-ttu-id="5fb85-138">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="5fb85-138">Using default Registrar port number.</span></span> <span data-ttu-id="5fb85-139">Rogation</span><span class="sxs-lookup"><span data-stu-id="5fb85-139">Exception:</span></span>

<span data-ttu-id="5fb85-140">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="5fb85-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5fb85-141">Regardez</span><span class="sxs-lookup"><span data-stu-id="5fb85-141">at</span></span>

<span data-ttu-id="5fb85-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="5fb85-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5fb85-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="5fb85-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5fb85-144">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5fb85-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5fb85-145">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="5fb85-145">Result : Failure</span></span>

<span data-ttu-id="5fb85-146">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5fb85-146">Latency : 00:00:00</span></span>

<span data-ttu-id="5fb85-147">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="5fb85-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5fb85-148">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="5fb85-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5fb85-149">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="5fb85-149">established connection failed because connected host has</span></span>

<span data-ttu-id="5fb85-150">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5fb85-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5fb85-151">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="5fb85-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5fb85-152">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="5fb85-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5fb85-153">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="5fb85-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5fb85-154">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5fb85-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5fb85-155">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5fb85-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5fb85-156">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="5fb85-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="5fb85-157">Voici quelques-unes des causes courantes de l’échec **de test-CsXmppIM** :</span><span class="sxs-lookup"><span data-stu-id="5fb85-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="5fb85-158">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="5fb85-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5fb85-159">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="5fb85-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5fb85-160">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="5fb85-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5fb85-161">Cette commande échoue si la configuration de la passerelle XMPP n’est pas configurée correctement ou n’est pas encore déployée.</span><span class="sxs-lookup"><span data-stu-id="5fb85-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fb85-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fb85-162">See Also</span></span>


[<span data-ttu-id="5fb85-163">Set-applet csxmppgatewayconfiguration ne</span><span class="sxs-lookup"><span data-stu-id="5fb85-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

