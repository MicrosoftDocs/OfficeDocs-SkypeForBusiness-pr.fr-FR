---
title: 'Lync Server 2013 : test du planificateur Web'
description: 'Lync Server 2013 : test du planificateur Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556150"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="243ff-103">Test du planificateur Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="243ff-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="243ff-104">_**Dernière modification de la rubrique :** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="243ff-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243ff-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="243ff-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="243ff-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="243ff-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243ff-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="243ff-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="243ff-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="243ff-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243ff-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="243ff-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="243ff-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="243ff-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="243ff-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet cswebscheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="243ff-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="243ff-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="243ff-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="243ff-113">Description</span><span class="sxs-lookup"><span data-stu-id="243ff-113">Description</span></span>

<span data-ttu-id="243ff-114">L’applet de commande **test-applet cswebscheduler** vous permet de déterminer si un utilisateur spécifique peut planifier une réunion à l’aide du planificateur Web.</span><span class="sxs-lookup"><span data-stu-id="243ff-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="243ff-115">Le planificateur Web permet aux utilisateurs qui n’exécutent pas Outlook de planifier des réunions en ligne.</span><span class="sxs-lookup"><span data-stu-id="243ff-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="243ff-116">Entre autres, cette nouvelle fonctionnalité (qui intègre les fonctionnalités de l’outil Web Scheduler fourni avec le kit de ressources Microsoft Lync Server 2010) permet aux utilisateurs d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="243ff-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="243ff-117">planifier une nouvelle réunion en ligne ;</span><span class="sxs-lookup"><span data-stu-id="243ff-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="243ff-118">dresser une liste de toutes les réunions qu’ils ont planifiées ;</span><span class="sxs-lookup"><span data-stu-id="243ff-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="243ff-119">afficher/modifier une réunion existante ;</span><span class="sxs-lookup"><span data-stu-id="243ff-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="243ff-120">supprimer une réunion existante ;</span><span class="sxs-lookup"><span data-stu-id="243ff-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="243ff-121">envoyer une invitation par courrier électronique aux participants aux réunions par le biais d’un serveur de messagerie SMTP ;</span><span class="sxs-lookup"><span data-stu-id="243ff-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="243ff-122">participer à une conférence existante.</span><span class="sxs-lookup"><span data-stu-id="243ff-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="243ff-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="243ff-123">Running the test</span></span>

<span data-ttu-id="243ff-124">L’exemple suivant vérifie le planificateur Web pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="243ff-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="243ff-125">Cette commande fonctionne uniquement si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="243ff-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="243ff-126">Si c’est le cas, la commande détermine si le premier utilisateur de test peut planifier une réunion en ligne à l’aide du planificateur Web.</span><span class="sxs-lookup"><span data-stu-id="243ff-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="243ff-127">Si les utilisateurs de test ne sont pas définis, la commande échoue, car elle ne peut pas identifier l’utilisateur sous lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="243ff-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="243ff-128">Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.</span><span class="sxs-lookup"><span data-stu-id="243ff-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="243ff-129">Les commandes présentées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (litwareinc \\ kenmeyer) à planifier une réunion en ligne à l’aide du planificateur Web.</span><span class="sxs-lookup"><span data-stu-id="243ff-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="243ff-130">Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="243ff-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="243ff-131">(Étant donné que le nom de connexion litwareinc \\ kenmeyer est inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Ken Meyer.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="243ff-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="243ff-132">La deuxième commande vérifie ensuite si cet utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et planifier une réunion en ligne.</span><span class="sxs-lookup"><span data-stu-id="243ff-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="243ff-133">Pour exécuter cette tâche, la cmdlet **test-applet cswebscheduler** est appelée, ainsi que trois paramètres : TargetFqdn (le nom de domaine complet du pool de serveurs d’inscriptions); UserCredential (l’objet Windows PowerShell qui contient les informations d’identification de l’utilisateur de Pilar Ackerman); et UserSipAddress (l’adresse SIP qui correspond aux informations d’identification de l’utilisateur fourni).</span><span class="sxs-lookup"><span data-stu-id="243ff-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="243ff-134">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="243ff-134">Determining success or failure</span></span>

<span data-ttu-id="243ff-135">Si le planificateur Web est configuré correctement, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:</span><span class="sxs-lookup"><span data-stu-id="243ff-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="243ff-136">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="243ff-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="243ff-137">URI cible : https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="243ff-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="243ff-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="243ff-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="243ff-139">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="243ff-139">Result : Success</span></span>

<span data-ttu-id="243ff-140">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="243ff-140">Latency : 00:00:00</span></span>

<span data-ttu-id="243ff-141">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="243ff-141">Error Message :</span></span>

<span data-ttu-id="243ff-142">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="243ff-142">Diagnosis :</span></span>

<span data-ttu-id="243ff-143">Si le planificateur Web n’est pas configuré correctement, le résultat est affiché sous la forme **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="243ff-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="243ff-144">AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet</span><span class="sxs-lookup"><span data-stu-id="243ff-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="243ff-145">nom de domaine (FQDN).</span><span class="sxs-lookup"><span data-stu-id="243ff-145">domain name (FQDN).</span></span> <span data-ttu-id="243ff-146">À l’aide du numéro de port de serveur d’inscriptions par défaut.</span><span class="sxs-lookup"><span data-stu-id="243ff-146">Using default Registrar port number.</span></span> <span data-ttu-id="243ff-147">Rogation</span><span class="sxs-lookup"><span data-stu-id="243ff-147">Exception:</span></span>

<span data-ttu-id="243ff-148">System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="243ff-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="243ff-149">Regardez</span><span class="sxs-lookup"><span data-stu-id="243ff-149">at</span></span>

<span data-ttu-id="243ff-150">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="243ff-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="243ff-151">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="243ff-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="243ff-152">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="243ff-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="243ff-153">URI cible :</span><span class="sxs-lookup"><span data-stu-id="243ff-153">Target Uri :</span></span>

<span data-ttu-id="243ff-154">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="243ff-154">Result : Failure</span></span>

<span data-ttu-id="243ff-155">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="243ff-155">Latency : 00:00:00</span></span>

<span data-ttu-id="243ff-156">Message d’erreur : aucun cluster correspondant n’a été trouvé dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="243ff-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="243ff-157">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="243ff-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="243ff-158">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="243ff-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="243ff-159">Voici quelques-unes des causes courantes de l’échec **de test-applet cswebscheduler** :</span><span class="sxs-lookup"><span data-stu-id="243ff-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="243ff-160">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="243ff-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="243ff-161">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="243ff-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="243ff-162">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="243ff-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="243ff-163">Cette commande échoue si le planificateur Web est configuré de façon incorrecte ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="243ff-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="243ff-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="243ff-164">See Also</span></span>


[<span data-ttu-id="243ff-165">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="243ff-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

