---
title: 'Lync Server 2013: test de Web Scheduler'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="7ea6d-102">Test de Web Scheduler dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea6d-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ea6d-103">_**Dernière modification de la rubrique:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="7ea6d-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ea6d-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="7ea6d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7ea6d-105">Jour</span><span class="sxs-lookup"><span data-stu-id="7ea6d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ea6d-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="7ea6d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7ea6d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ea6d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ea6d-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="7ea6d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7ea6d-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7ea6d-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="7ea6d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="7ea6d-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7ea6d-112">Description</span><span class="sxs-lookup"><span data-stu-id="7ea6d-112">Description</span></span>

<span data-ttu-id="7ea6d-113">L’applet de **contrôle test-CsWebScheduler** vous permet de déterminer si un utilisateur spécifique peut planifier une réunion à l’aide de Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="7ea6d-114">Web Scheduler permet aux utilisateurs qui n’exécutent pas Outlook de planifier des réunions en ligne.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="7ea6d-115">Entre autres choses, cette nouvelle fonctionnalité (qui incorpore les fonctionnalités disponibles dans l’outil Web Scheduler inclus dans le kit de ressources Microsoft Lync Server 2010) permet aux utilisateurs d’effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="7ea6d-116">Planifier une nouvelle réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="7ea6d-117">Répertorier toutes les réunions qu’il a planifiées.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="7ea6d-118">Afficher/modifier une réunion existante.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="7ea6d-119">Supprimez une réunion existante.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="7ea6d-120">Envoyez une invitation électronique aux participants à la réunion à l’aide d’un serveur de messagerie SMTP préconfiguré.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="7ea6d-121">Participez à une conférence existante.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7ea6d-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="7ea6d-122">Running the test</span></span>

<span data-ttu-id="7ea6d-123">L’exemple suivant vérifie le planificateur Web pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7ea6d-124">Cette commande ne fonctionne que si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7ea6d-125">Si tel est le cas, la commande détermine si le premier utilisateur du test peut planifier une réunion en ligne à l’aide de Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="7ea6d-126">Si les utilisateurs de test ne sont pas définis, la commande échoue, car il ne connaît pas l’utilisateur sur lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="7ea6d-127">Si vous n’avez pas défini les utilisateurs test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7ea6d-128">Les commandes indiquées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (\\litwareinc kenmeyer) pour planifier une réunion en ligne à l’aide de Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="7ea6d-129">Pour cela, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’informations d’identification d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="7ea6d-130">(Dans la mesure où le\\nom de connexion litwareinc kenmeyer est inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Ken Meyer.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="7ea6d-131">La deuxième commande vérifie que l’utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et planifier une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="7ea6d-132">Pour exécuter cette tâche, l’applet de **contrôle test-CsWebScheduler** est appelée, avec trois paramètres: TargetFqdn (nom de domaine complet du pool d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Pilar Arès); et UserSipAddress (adresse SIP correspondant aux informations d’identification fournies par l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="7ea6d-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7ea6d-133">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="7ea6d-133">Determining success or failure</span></span>

<span data-ttu-id="7ea6d-134">Si Web Scheduler est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="7ea6d-135">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7ea6d-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7ea6d-136">URI cible: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="7ea6d-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="7ea6d-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="7ea6d-138">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="7ea6d-138">Result : Success</span></span>

<span data-ttu-id="7ea6d-139">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7ea6d-139">Latency : 00:00:00</span></span>

<span data-ttu-id="7ea6d-140">Message d’erreur:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-140">Error Message :</span></span>

<span data-ttu-id="7ea6d-141">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="7ea6d-141">Diagnosis :</span></span>

<span data-ttu-id="7ea6d-142">Si Web Scheduler n’est pas configuré correctement, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7ea6d-143">AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni</span><span class="sxs-lookup"><span data-stu-id="7ea6d-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="7ea6d-144">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="7ea6d-144">domain name (FQDN).</span></span> <span data-ttu-id="7ea6d-145">Utilisation du numéro de port de bureau par défaut.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-145">Using default Registrar port number.</span></span> <span data-ttu-id="7ea6d-146">Sauf</span><span class="sxs-lookup"><span data-stu-id="7ea6d-146">Exception:</span></span>

<span data-ttu-id="7ea6d-147">System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="7ea6d-148">dès</span><span class="sxs-lookup"><span data-stu-id="7ea6d-148">at</span></span>

<span data-ttu-id="7ea6d-149">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="7ea6d-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="7ea6d-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="7ea6d-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="7ea6d-151">Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7ea6d-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7ea6d-152">URI de destination:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-152">Target Uri :</span></span>

<span data-ttu-id="7ea6d-153">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="7ea6d-153">Result : Failure</span></span>

<span data-ttu-id="7ea6d-154">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7ea6d-154">Latency : 00:00:00</span></span>

<span data-ttu-id="7ea6d-155">Message d’erreur: aucun cluster correspondant détecté dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="7ea6d-156">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="7ea6d-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7ea6d-157">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="7ea6d-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="7ea6d-158">Voici quelques raisons courantes pour lesquelles **les tests-CsWebScheduler** peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="7ea6d-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="7ea6d-159">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="7ea6d-160">S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="7ea6d-161">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="7ea6d-162">Cette commande échoue si Web Scheduler n’est pas configuré correctement ou n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="7ea6d-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ea6d-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ea6d-163">See Also</span></span>


[<span data-ttu-id="7ea6d-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="7ea6d-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

