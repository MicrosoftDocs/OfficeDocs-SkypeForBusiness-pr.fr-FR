---
title: 'Lync Server 2013: test de la connexion utilisateur à la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="344b2-102">Test de la connexion utilisateur à la messagerie unifiée Exchange dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="344b2-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="344b2-103">_**Dernière modification de la rubrique:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="344b2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344b2-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="344b2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="344b2-105">Jour</span><span class="sxs-lookup"><span data-stu-id="344b2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344b2-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="344b2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="344b2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="344b2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344b2-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="344b2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="344b2-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="344b2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="344b2-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="344b2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="344b2-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="344b2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="344b2-112">Description</span><span class="sxs-lookup"><span data-stu-id="344b2-112">Description</span></span>

<span data-ttu-id="344b2-113">L’applet de **contrôle test-CsExUMConnectivity** vérifie que l’utilisateur spécifié est en mesure de se connecter au service de messagerie unifiée Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="344b2-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="344b2-114">Notez que cette cmdlet vérifie uniquement qu’une connexion peut être établie au service.</span><span class="sxs-lookup"><span data-stu-id="344b2-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="344b2-115">Le service proprement dit n’est pas testé.</span><span class="sxs-lookup"><span data-stu-id="344b2-115">It does not test the service itself.</span></span> <span data-ttu-id="344b2-116">Pour tester le service de messagerie unifiée (en exécutant une cmdlet de transaction synthétique qui quitte réellement un message de messagerie vocale dans la boîte aux lettres de l’utilisateur), utilisez l’applet de contrôle test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="344b2-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="344b2-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="344b2-117">Running the test</span></span>

<span data-ttu-id="344b2-118">L’exemple suivant teste la connectivité de messagerie unifiée Exchange pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="344b2-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="344b2-119">Cette commande ne fonctionnera que si les utilisateurs de test étaient définis pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="344b2-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="344b2-120">Si tel est le cas, la commande détermine si le premier utilisateur de test peut se connecter à la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="344b2-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="344b2-121">Si les utilisateurs test n’ont pas été configurés pour le pool, la commande échoue.</span><span class="sxs-lookup"><span data-stu-id="344b2-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="344b2-122">Les commandes indiquées dans l’exemple suivant testent la connectivité de messagerie unifiée Exchange\\pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="344b2-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="344b2-123">Pour ce faire, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’identification d’interface de ligne de commande\\Windows PowerShell pour l’utilisateur litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="344b2-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="344b2-124">Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que l’applet de contrôle **CsExUMConnectivity** puisse exécuter sa vérification.</span><span class="sxs-lookup"><span data-stu-id="344b2-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="344b2-125">La deuxième commande de l’exemple utilise l’objet Credentials fourni ($x) et l’adresse SIP de l’utilisateur litwareinc\\kenmyer pour déterminer si l’utilisateur peut se connecter à la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="344b2-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="344b2-126">Dans l’exemple qui suit, la commande est une variante de la commande qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="344b2-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="344b2-127">Dans ce cas, le paramètre OutLoggerVariable est inclus pour générer un journal détaillé de chaque étape réalisée par le **test-CsExUMConnectivity** cmdletand le succès ou l’échec de chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="344b2-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="344b2-128">Pour ce faire, le paramètre OutLoggerVariable est ajouté avec la valeur de paramètre ExumText; les informations de journalisation détaillées sont alors stockées dans une variable nommée $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="344b2-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="344b2-129">Dans la commande final de l’exemple, la méthode ToXML () est utilisée pour convertir les informations du journal au format XML.</span><span class="sxs-lookup"><span data-stu-id="344b2-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="344b2-130">Ces données XML sont alors écrites dans un fichier nommé C:\\logs\\ExumTest. XML en utilisant l’applet de connexion Out-File.</span><span class="sxs-lookup"><span data-stu-id="344b2-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="344b2-131">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="344b2-131">Determining success or failure</span></span>

<span data-ttu-id="344b2-132">Si l’intégration Exchange est correctement configurée, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:</span><span class="sxs-lookup"><span data-stu-id="344b2-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="344b2-133">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="344b2-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="344b2-134">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="344b2-134">Result : Success</span></span>

<span data-ttu-id="344b2-135">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="344b2-135">Latency : 00:00:00</span></span>

<span data-ttu-id="344b2-136">Message d’erreur:</span><span class="sxs-lookup"><span data-stu-id="344b2-136">Error Message :</span></span>

<span data-ttu-id="344b2-137">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="344b2-137">Diagnosis :</span></span>

<span data-ttu-id="344b2-138">Si l’utilisateur spécifié ne peut pas recevoir de notifications, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="344b2-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="344b2-139">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="344b2-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="344b2-140">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="344b2-140">Result : Failure</span></span>

<span data-ttu-id="344b2-141">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="344b2-141">Latency : 00:00:00</span></span>

<span data-ttu-id="344b2-142">Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="344b2-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="344b2-143">ne répond pas correctement après un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="344b2-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="344b2-144">échec de la connexion établie, car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="344b2-144">established connection failed because connected host has</span></span>

<span data-ttu-id="344b2-145">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="344b2-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="344b2-146">Exception interne: une tentative de connexion a échoué, car le</span><span class="sxs-lookup"><span data-stu-id="344b2-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="344b2-147">la fête connectée ne répond pas correctement après un délai de</span><span class="sxs-lookup"><span data-stu-id="344b2-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="344b2-148">heure ou échec de la connexion en raison d’un hôte connecté</span><span class="sxs-lookup"><span data-stu-id="344b2-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="344b2-149">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="344b2-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="344b2-150">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="344b2-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="344b2-151">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="344b2-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="344b2-152">Voici quelques raisons courantes pour lesquelles **les tests-CsExUMConnectivity** peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="344b2-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="344b2-153">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="344b2-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="344b2-154">S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="344b2-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="344b2-155">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="344b2-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="344b2-156">Si le serveur Exchange n’est pas configuré correctement ou n’est pas encore déployé, cette commande échoue.</span><span class="sxs-lookup"><span data-stu-id="344b2-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="344b2-157">Cette commande échoue si le serveur Exchange n’est pas joignable sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="344b2-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="344b2-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="344b2-158">See Also</span></span>


[<span data-ttu-id="344b2-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="344b2-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

