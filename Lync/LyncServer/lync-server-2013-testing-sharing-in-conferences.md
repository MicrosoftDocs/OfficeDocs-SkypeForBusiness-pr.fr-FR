---
title: 'Lync Server 2013 : test du partage dans les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36cf05d0d3d5cce13a100d23cb541eb5aa186ef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530491"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="cc1bf-102">Test du partage dans les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc1bf-102">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc1bf-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc1bf-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc1bf-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="cc1bf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cc1bf-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="cc1bf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc1bf-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="cc1bf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cc1bf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1bf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc1bf-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="cc1bf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cc1bf-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cc1bf-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="cc1bf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="cc1bf-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cc1bf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cc1bf-112">Description</span><span class="sxs-lookup"><span data-stu-id="cc1bf-112">Description</span></span>

<span data-ttu-id="cc1bf-113">Dans Lync Server 2013, une conférence de données est une conférence où des activités collaboratives telles que le tableau blanc ou les annotations sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="cc1bf-114">L’applet de commande **test-CsDataConference** vous permet de vérifier qu’une paire d’utilisateurs est en mesure de participer à une conférence de données.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cc1bf-115">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="cc1bf-115">Running the test</span></span>

<span data-ttu-id="cc1bf-p103">La commande indiquée dans l’exemple 1 vérifie qu’une conférence de données peut être menée sur le pool atl-cs-001.litwareinc.com. Cette commande part du principe que vous avez configuré une paire d’utilisateurs de test pour le pool spécifié. En l’absence d’utilisateurs de test, la commande échoue.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="cc1bf-119">Les commandes indiquées dans l’exemple 2 testent la capacité d’une paire d’utilisateurs (litwareinc \\ Pilar et litwareinc \\ kenmyer) à se connecter à Lync Server 2013, puis à mener une conférence de données.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="cc1bf-120">Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="cc1bf-121">(Étant donné que le nom de connexion, litwareinc \\ Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="cc1bf-122">La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="cc1bf-123">Avec les objets Credential en main, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et mener une conférence de données.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="cc1bf-124">Pour exécuter cette tâche, la cmdlet **test-CsDataConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); SenderSipAddress (l’adresse SIP pour le premier utilisateur test); SenderCredential (l’objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (l’adresse SIP de l’autre utilisateur de test); et ReceiverCredential (l’objet Windows PowerShell contenant les informations d’identification pour l’autre utilisateur de test).</span><span class="sxs-lookup"><span data-stu-id="cc1bf-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cc1bf-125">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="cc1bf-125">Determining success or failure</span></span>

<span data-ttu-id="cc1bf-126">Si la Conférence de données est configurée correctement, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="cc1bf-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cc1bf-127">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc1bf-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc1bf-128">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="cc1bf-128">Result : Success</span></span>

<span data-ttu-id="cc1bf-129">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cc1bf-129">Latency : 00:00:00</span></span>

<span data-ttu-id="cc1bf-130">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="cc1bf-130">Error Message :</span></span>

<span data-ttu-id="cc1bf-131">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="cc1bf-131">Diagnosis :</span></span>

<span data-ttu-id="cc1bf-132">Si les utilisateurs spécifiés ne peuvent pas utiliser le partage de données, le résultat est indiqué comme étant un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="cc1bf-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cc1bf-133">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cc1bf-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cc1bf-134">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="cc1bf-134">Result : Failure</span></span>

<span data-ttu-id="cc1bf-135">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="cc1bf-135">Latency : 00:00:00</span></span>

<span data-ttu-id="cc1bf-136">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="cc1bf-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="cc1bf-137">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="cc1bf-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="cc1bf-138">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="cc1bf-138">established connection failed because connected host has</span></span>

<span data-ttu-id="cc1bf-139">échec de la réponse \[ 2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 :: \] 5061</span><span class="sxs-lookup"><span data-stu-id="cc1bf-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cc1bf-140">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="cc1bf-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="cc1bf-141">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="cc1bf-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="cc1bf-142">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="cc1bf-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="cc1bf-143">n’a pas répondu</span><span class="sxs-lookup"><span data-stu-id="cc1bf-143">has failed to respond</span></span>

<span data-ttu-id="cc1bf-144">\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 : \] : 5061</span><span class="sxs-lookup"><span data-stu-id="cc1bf-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cc1bf-145">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="cc1bf-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cc1bf-146">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="cc1bf-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="cc1bf-147">Voici quelques-unes des causes courantes de l’échec **de test-CsDataConference** :</span><span class="sxs-lookup"><span data-stu-id="cc1bf-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="cc1bf-148">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="cc1bf-149">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="cc1bf-150">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="cc1bf-151">La possibilité d’effectuer une conférence de données dépend de la stratégie de conférence qui a été attribuée à l’utilisateur qui a organisé la Conférence (dans le cas de la cmdlet **test-CsDataConference** , qui est l’expéditeur).</span><span class="sxs-lookup"><span data-stu-id="cc1bf-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="cc1bf-152">Si l’organisateur n’est pas autorisé à inclure des activités collaboratives dans sa réunion (par exemple, si la propriété EnableDataCollaboration de sa stratégie de conférence est définie sur false), la cmdlet **test-CsDataConference** échouera.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="cc1bf-153">Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="cc1bf-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

