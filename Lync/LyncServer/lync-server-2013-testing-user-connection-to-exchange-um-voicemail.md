---
title: 'Lync Server 2013 : test de la messagerie vocale de messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="5e79d-102">Test de la connexion utilisateur à la messagerie vocale de messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e79d-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e79d-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5e79d-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e79d-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="5e79d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5e79d-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="5e79d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e79d-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="5e79d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5e79d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e79d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e79d-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="5e79d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5e79d-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5e79d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5e79d-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="5e79d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="5e79d-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="5e79d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5e79d-112">Description</span><span class="sxs-lookup"><span data-stu-id="5e79d-112">Description</span></span>

<span data-ttu-id="5e79d-113">L’applet de commande **test-CsExUMVoiceMail** permet aux administrateurs de vérifier qu’un utilisateur peut accéder au service de messagerie unifiée Microsoft Exchange Server 2013 et l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="5e79d-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="5e79d-114">Pour y parvenir, l’applet de commande se connecte au service de messagerie unifiée et laisse un message vocal dans la boîte aux lettres spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5e79d-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="5e79d-115">Il peut s’agir d’un message vocal généré par le système ou d’un fichier .WAV personnalisé que vous avez enregistré vous-même.</span><span class="sxs-lookup"><span data-stu-id="5e79d-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5e79d-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="5e79d-116">Running the test</span></span>

<span data-ttu-id="5e79d-117">L’exemple suivant teste la connectivité de messagerie vocale de la messagerie unifiée Exchange pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e79d-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5e79d-118">Cette commande fonctionne uniquement si les utilisateurs de test ont été définis pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e79d-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5e79d-119">Si c’est le cas, la commande détermine si le premier utilisateur test peut utiliser la messagerie vocale de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="5e79d-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="5e79d-120">Si les utilisateurs de test n’ont pas été configurés pour le pool, la commande échouera.</span><span class="sxs-lookup"><span data-stu-id="5e79d-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="5e79d-121">Les commandes indiquées dans l’exemple suivant testent la connectivité de la messagerie vocale de la messagerie\\unifiée Exchange pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="5e79d-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="5e79d-122">Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows\\PowerShell pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="5e79d-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="5e79d-123">Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que la cmdlet **test-CsExUMVoiceMail** peut exécuter sa vérification.</span><span class="sxs-lookup"><span data-stu-id="5e79d-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="5e79d-124">La deuxième commande de l’exemple utilise l’objet d’informations d’identification fourni ($x) et l’adresse SIP de l'\\utilisateur litwareinc kenmyer pour déterminer si l’utilisateur peut se connecter à la messagerie vocale de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="5e79d-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="5e79d-125">La commande illustrée dans l’exemple suivant est une variante de la commande illustrée dans l’exemple 1 ; dans ce cas, le paramètre OutLoggerVariable est inclus pour générer un journal détaillé de chaque étape effectuée par le **test-CsExUMVoiceMail** cmdletand la réussite ou l’échec de chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="5e79d-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="5e79d-126">Pour ce faire, le paramètre OutLoggerVariable est ajouté avec la valeur de paramètre ExumText ; les informations de journalisation détaillées sont alors stockées dans une variable nommée $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="5e79d-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="5e79d-127">Dans la dernière commande de l’exemple, la méthode ToXML () est utilisée pour convertir les informations du journal au format XML.</span><span class="sxs-lookup"><span data-stu-id="5e79d-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="5e79d-128">Ces données XML sont ensuite écrites dans un fichier nommé C :\\logs\\VoicemailTest. XML à l’aide de l’applet de commande Out-File.</span><span class="sxs-lookup"><span data-stu-id="5e79d-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5e79d-129">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="5e79d-129">Determining success or failure</span></span>

<span data-ttu-id="5e79d-130">Si l’intégration d’Exchange est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:</span><span class="sxs-lookup"><span data-stu-id="5e79d-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="5e79d-131">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e79d-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5e79d-132">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="5e79d-132">Result : Success</span></span>

<span data-ttu-id="5e79d-133">Latence : 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="5e79d-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="5e79d-134">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="5e79d-134">Error Message :</span></span>

<span data-ttu-id="5e79d-135">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5e79d-135">Diagnosis :</span></span>

<span data-ttu-id="5e79d-136">Si l’utilisateur spécifié ne peut pas se connecter à la messagerie vocale, le résultat apparaîtra en **échec**et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="5e79d-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5e79d-137">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="5e79d-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5e79d-138">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5e79d-138">domain name (FQDN).</span></span> <span data-ttu-id="5e79d-139">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="5e79d-139">Using default Registrar port number.</span></span> <span data-ttu-id="5e79d-140">Rogation</span><span class="sxs-lookup"><span data-stu-id="5e79d-140">Exception:</span></span>

<span data-ttu-id="5e79d-141">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="5e79d-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5e79d-142">Regardez</span><span class="sxs-lookup"><span data-stu-id="5e79d-142">at</span></span>

<span data-ttu-id="5e79d-143">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="5e79d-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5e79d-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="5e79d-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5e79d-145">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e79d-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5e79d-146">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="5e79d-146">Result : Failure</span></span>

<span data-ttu-id="5e79d-147">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5e79d-147">Latency : 00:00:00</span></span>

<span data-ttu-id="5e79d-148">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="5e79d-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5e79d-149">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="5e79d-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5e79d-150">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="5e79d-150">established connection failed because connected host has</span></span>

<span data-ttu-id="5e79d-151">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5e79d-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5e79d-152">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="5e79d-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5e79d-153">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="5e79d-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5e79d-154">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="5e79d-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5e79d-155">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5e79d-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5e79d-156">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="5e79d-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5e79d-157">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="5e79d-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="5e79d-158">Voici quelques-unes des causes courantes de l’échec **de test-CsExUMVoiceMail** :</span><span class="sxs-lookup"><span data-stu-id="5e79d-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="5e79d-159">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="5e79d-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5e79d-160">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="5e79d-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5e79d-161">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="5e79d-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5e79d-162">Cette commande échoue si le serveur Exchange est mal configuré ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="5e79d-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e79d-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e79d-163">See Also</span></span>


[<span data-ttu-id="5e79d-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="5e79d-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

