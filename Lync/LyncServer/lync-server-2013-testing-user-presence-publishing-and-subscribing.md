---
title: 'Lync Server 2013 : test de la publication de la présence de l’utilisateur et de l’abonnement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d506ed0115fd5346048ff8870763a7ffc888a69
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="2021e-102">Test de la publication de la présence de l’utilisateur et de l’abonnement à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2021e-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2021e-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2021e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2021e-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="2021e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2021e-105">Jour</span><span class="sxs-lookup"><span data-stu-id="2021e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2021e-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="2021e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2021e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2021e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2021e-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="2021e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2021e-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2021e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2021e-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsPresence.</span><span class="sxs-lookup"><span data-stu-id="2021e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="2021e-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="2021e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2021e-112">Description</span><span class="sxs-lookup"><span data-stu-id="2021e-112">Description</span></span>

<span data-ttu-id="2021e-113">Test-CsPresence est utilisé pour déterminer si un binôme d’utilisateurs de test peut se connecter à Lync Server, puis échanger des informations de présence.</span><span class="sxs-lookup"><span data-stu-id="2021e-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="2021e-114">Pour ce faire, l’applet de connexion enregistre d’abord les deux utilisateurs sur le système.</span><span class="sxs-lookup"><span data-stu-id="2021e-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="2021e-115">Si les deux ouvertures de session aboutissent, le premier utilisateur de test demande alors de recevoir les informations de présence du deuxième utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2021e-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="2021e-116">Le deuxième utilisateur publie ces informations et test-CsPresence vérifie que les informations ont bien été transmises au premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2021e-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="2021e-117">Après l’échange des informations de présence, les deux utilisateurs de test sont alors déconnectés de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2021e-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="2021e-118">Running the test</span></span>

<span data-ttu-id="2021e-119">L’applet de contrôle test-CsPresence peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="2021e-120">Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="2021e-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="2021e-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2021e-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2021e-122">Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="2021e-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="2021e-123">Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsPresence :</span><span class="sxs-lookup"><span data-stu-id="2021e-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="2021e-124">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .</span><span class="sxs-lookup"><span data-stu-id="2021e-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2021e-125">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="2021e-125">Determining success or failure</span></span>

<span data-ttu-id="2021e-126">Si les utilisateurs spécifiés peuvent échanger des informations de présence, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie :**</span><span class="sxs-lookup"><span data-stu-id="2021e-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2021e-127">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2021e-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2021e-128">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="2021e-128">Result : Success</span></span>

<span data-ttu-id="2021e-129">Latence : 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="2021e-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="2021e-130">Error</span><span class="sxs-lookup"><span data-stu-id="2021e-130">Error :</span></span>

<span data-ttu-id="2021e-131">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="2021e-131">Diagnosis :</span></span>

<span data-ttu-id="2021e-132">Si les deux utilisateurs ne peuvent pas échanger des informations de présence, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="2021e-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2021e-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2021e-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2021e-134">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="2021e-134">Result : Failure</span></span>

<span data-ttu-id="2021e-135">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2021e-135">Latency : 00:00:00</span></span>

<span data-ttu-id="2021e-136">Erreur : 404, introuvable</span><span class="sxs-lookup"><span data-stu-id="2021e-136">Error : 404, Not Found</span></span>

<span data-ttu-id="2021e-137">Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="2021e-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="2021e-138">Raison = URI de destination non activé pour le SIP ou non</span><span class="sxs-lookup"><span data-stu-id="2021e-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="2021e-139">Il.</span><span class="sxs-lookup"><span data-stu-id="2021e-139">exist.</span></span>

<span data-ttu-id="2021e-140">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="2021e-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2021e-141">Par exemple, la sortie précédente indique que le test a échoué car au moins un des deux comptes d’utilisateurs n’est pas valide : le compte n’existe pas ou n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="2021e-142">Vous pouvez vérifier qu’il existe des comptes et déterminer s’ils sont activés pour Lync Server en exécutant une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2021e-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="2021e-143">Si test-CsPresence échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="2021e-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="2021e-144">Lorsque le paramètre Verbose est inclus, test-CsPresence renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2021e-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2021e-145">For example:</span></span>

<span data-ttu-id="2021e-146">Demande d’inscription inattendue</span><span class="sxs-lookup"><span data-stu-id="2021e-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="2021e-147">Activité « Register » achevée en « 0,0345791 » secondes.</span><span class="sxs-lookup"><span data-stu-id="2021e-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="2021e-148">Activité « SelfSubscribeActivity » démarrée.</span><span class="sxs-lookup"><span data-stu-id="2021e-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="2021e-149">Activité « SelfSubscribeActivity » terminée en « 0,0041174 » secondes.</span><span class="sxs-lookup"><span data-stu-id="2021e-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="2021e-150">Activité « SubscribePresence » démarrée.</span><span class="sxs-lookup"><span data-stu-id="2021e-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="2021e-151">Activité « SubscribePresence » terminée en « 0,0038764 » secondes.</span><span class="sxs-lookup"><span data-stu-id="2021e-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="2021e-152">Activité « PublishPresence » démarrée.</span><span class="sxs-lookup"><span data-stu-id="2021e-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="2021e-153">La notification de présence d’une exception n’est pas reçue dans un délai de 25 secondes. '</span><span class="sxs-lookup"><span data-stu-id="2021e-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="2021e-154">Il s’est produit ruing flux de travail Microsoft. RTC. SyntheticTransactions. flux de travail. STPresenceWorkflow.</span><span class="sxs-lookup"><span data-stu-id="2021e-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="2021e-155">Le fait que la notification de présence n’a pas été reçue dans les 25 secondes peut indiquer que des problèmes réseau empêchent les informations d’être échangées.</span><span class="sxs-lookup"><span data-stu-id="2021e-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2021e-156">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="2021e-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="2021e-157">Voici quelques raisons courantes pour lesquelles les tests-CsPresence peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="2021e-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="2021e-158">Vous avez spécifié un compte d’utilisateur incorrect.</span><span class="sxs-lookup"><span data-stu-id="2021e-158">You specified an incorrect user account.</span></span> <span data-ttu-id="2021e-159">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2021e-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2021e-160">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2021e-161">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2021e-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2021e-162">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2021e-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

