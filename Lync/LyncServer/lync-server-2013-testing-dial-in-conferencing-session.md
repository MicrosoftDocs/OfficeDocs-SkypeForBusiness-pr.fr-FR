---
title: 'Lync Server 2013 : test d’une session de conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="9f537-102">Test d’une session de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f537-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f537-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9f537-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f537-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="9f537-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f537-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="9f537-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f537-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="9f537-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f537-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f537-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f537-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="9f537-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f537-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9f537-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f537-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="9f537-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="9f537-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9f537-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f537-112">Description</span><span class="sxs-lookup"><span data-stu-id="9f537-112">Description</span></span>

<span data-ttu-id="9f537-113">L’applet de commande test-CsDialInConferencing vérifie si un utilisateur peut participer à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9f537-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="9f537-114">Test-CsDialInConferencing fonctionne en tentant de journaliser un utilisateur test sur le système.</span><span class="sxs-lookup"><span data-stu-id="9f537-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="9f537-115">Si l’ouverture de session réussit, l’applet de commande utilise les informations d’identification et les autorisations de l’utilisateur pour essayer tous les numéros d’accès aux conférences rendez-vous disponibles.</span><span class="sxs-lookup"><span data-stu-id="9f537-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="9f537-116">La réussite ou l’échec de chaque tentative d’accès à distance est indiqué, puis l’utilisateur de test est déconnecté de Lync Server. test-CsDialInConferencing vérifie uniquement que les connexions appropriées peuvent être établies.</span><span class="sxs-lookup"><span data-stu-id="9f537-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="9f537-117">L’applet de commande ne passe pas réellement d’appels téléphoniques ou ne crée pas de conférences rendez-vous que d’autres utilisateurs peuvent rejoindre.</span><span class="sxs-lookup"><span data-stu-id="9f537-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f537-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="9f537-118">Running the test</span></span>

<span data-ttu-id="9f537-119">La cmdlet Test-CsDialInConferencing peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f537-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9f537-120">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="9f537-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9f537-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f537-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="9f537-122">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="9f537-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="9f537-123">Vous devez ensuite inclure l’objet Credentials et l’adresse SIP du compte l’appel test-CsDialInConferencing :</span><span class="sxs-lookup"><span data-stu-id="9f537-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9f537-124">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="9f537-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f537-125">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="9f537-125">Determining success or failure</span></span>

<span data-ttu-id="9f537-126">Si l’utilisateur spécifié peut se connecter à Lync Server, puis établir une connexion à l’aide de l’un des numéros d’accès de conférence rendez-vous disponibles, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="9f537-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9f537-127">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f537-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f537-128">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="9f537-128">Result : Success</span></span>

<span data-ttu-id="9f537-129">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="9f537-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="9f537-130">«</span><span class="sxs-lookup"><span data-stu-id="9f537-130">Error :</span></span>

<span data-ttu-id="9f537-131">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9f537-131">Diagnosis :</span></span>

<span data-ttu-id="9f537-132">Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat est affiché en tant que défaillance et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="9f537-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9f537-133">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f537-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f537-134">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="9f537-134">Result : Failure</span></span>

<span data-ttu-id="9f537-135">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f537-135">Latency : 00:00:00</span></span>

<span data-ttu-id="9f537-136">Erreur : la connexion a été refusée.</span><span class="sxs-lookup"><span data-stu-id="9f537-136">Error : The log on was denied.</span></span> <span data-ttu-id="9f537-137">Vérifiez que les informations d’identification correctes sont</span><span class="sxs-lookup"><span data-stu-id="9f537-137">Check that the proper credentials are</span></span>

<span data-ttu-id="9f537-138">en cours d’utilisation et que le compte est actif.</span><span class="sxs-lookup"><span data-stu-id="9f537-138">being used and the account is active.</span></span>

<span data-ttu-id="9f537-139">Exception interne : NegotiateSecurityAssociation failed, erreur :-</span><span class="sxs-lookup"><span data-stu-id="9f537-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="9f537-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="9f537-140">2146893044</span></span>

<span data-ttu-id="9f537-141">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9f537-141">Diagnosis :</span></span>

<span data-ttu-id="9f537-142">La sortie précédente indique que l’utilisateur test a été refusé l’accès à Lync Server lui-même.</span><span class="sxs-lookup"><span data-stu-id="9f537-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="9f537-143">Cela signifie généralement que les informations d’identification de l’utilisateur transmises à test-CsDialInConferencing n’étaient pas valides.</span><span class="sxs-lookup"><span data-stu-id="9f537-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="9f537-144">Ensuite, vous devez recréer l’objet d’informations d’identification Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f537-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="9f537-145">Bien que vous puissiez récupérer le mot de passe du compte d’utilisateur, vous pouvez vérifier l’adresse SIP à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9f537-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f537-146">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="9f537-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f537-147">Voici quelques-unes des causes courantes de l’échec de test-CsDialInConferencing :</span><span class="sxs-lookup"><span data-stu-id="9f537-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="9f537-148">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="9f537-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="9f537-149">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9f537-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9f537-150">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f537-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9f537-151">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9f537-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9f537-152">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f537-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="9f537-153">Le numéro d’accès à la Conférence rendez-vous est peut-être incorrect.</span><span class="sxs-lookup"><span data-stu-id="9f537-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="9f537-154">Vous pouvez retourner votre liste de numéros d’accès aux conférences rendez-vous en cours à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f537-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

