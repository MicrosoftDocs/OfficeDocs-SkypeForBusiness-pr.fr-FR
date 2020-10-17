---
title: 'Lync Server 2013 : test d’une session de conférence rendez-vous'
description: 'Lync Server 2013 : test de la session de conférence rendez-vous.'
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
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560630"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="02695-103">Test d’une session de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02695-103">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02695-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="02695-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02695-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="02695-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="02695-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="02695-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02695-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="02695-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="02695-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02695-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02695-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="02695-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="02695-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="02695-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="02695-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="02695-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="02695-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="02695-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="02695-113">Description</span><span class="sxs-lookup"><span data-stu-id="02695-113">Description</span></span>

<span data-ttu-id="02695-114">L’applet de commande Test-CsDialInConferencing vérifie si un utilisateur peut participer à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="02695-114">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="02695-115">Test-CsDialInConferencing fonctionne en tentant de journaliser un utilisateur test sur le système.</span><span class="sxs-lookup"><span data-stu-id="02695-115">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="02695-116">Si l’ouverture de session réussit, l’applet de commande utilise les informations d’identification et les autorisations de l’utilisateur pour essayer tous les numéros d’accès aux conférences rendez-vous disponibles.</span><span class="sxs-lookup"><span data-stu-id="02695-116">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="02695-117">La réussite ou l’échec de chaque tentative d’accès à distance est indiqué, puis l’utilisateur de test est déconnecté de Lync Server. test-CsDialInConferencing vérifie uniquement que les connexions appropriées peuvent être établies.</span><span class="sxs-lookup"><span data-stu-id="02695-117">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="02695-118">L’applet de commande ne passe pas réellement d’appels téléphoniques ou ne crée pas de conférences rendez-vous que d’autres utilisateurs peuvent rejoindre.</span><span class="sxs-lookup"><span data-stu-id="02695-118">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="02695-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="02695-119">Running the test</span></span>

<span data-ttu-id="02695-120">L’applet de commande Test-CsDialInConferencing peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02695-120">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="02695-121">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="02695-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="02695-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="02695-122">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="02695-123">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="02695-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="02695-124">Vous devez ensuite inclure l’objet Credentials et l’adresse SIP du compte l’appel test-CsDialInConferencing :</span><span class="sxs-lookup"><span data-stu-id="02695-124">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="02695-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="02695-125">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="02695-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="02695-126">Determining success or failure</span></span>

<span data-ttu-id="02695-127">Si l’utilisateur spécifié peut se connecter à Lync Server, puis établir une connexion à l’aide de l’un des numéros d’accès de conférence rendez-vous disponibles, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="02695-127">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="02695-128">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="02695-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="02695-129">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="02695-129">Result : Success</span></span>

<span data-ttu-id="02695-130">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="02695-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="02695-131">«</span><span class="sxs-lookup"><span data-stu-id="02695-131">Error :</span></span>

<span data-ttu-id="02695-132">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="02695-132">Diagnosis :</span></span>

<span data-ttu-id="02695-133">Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat est affiché en tant que défaillance et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="02695-133">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="02695-134">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="02695-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="02695-135">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="02695-135">Result : Failure</span></span>

<span data-ttu-id="02695-136">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="02695-136">Latency : 00:00:00</span></span>

<span data-ttu-id="02695-137">Erreur : la connexion a été refusée.</span><span class="sxs-lookup"><span data-stu-id="02695-137">Error : The log on was denied.</span></span> <span data-ttu-id="02695-138">Vérifiez que les informations d’identification correctes sont</span><span class="sxs-lookup"><span data-stu-id="02695-138">Check that the proper credentials are</span></span>

<span data-ttu-id="02695-139">en cours d’utilisation et que le compte est actif.</span><span class="sxs-lookup"><span data-stu-id="02695-139">being used and the account is active.</span></span>

<span data-ttu-id="02695-140">Exception interne : NegotiateSecurityAssociation failed, erreur :-</span><span class="sxs-lookup"><span data-stu-id="02695-140">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="02695-141">2146893044</span><span class="sxs-lookup"><span data-stu-id="02695-141">2146893044</span></span>

<span data-ttu-id="02695-142">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="02695-142">Diagnosis :</span></span>

<span data-ttu-id="02695-143">La sortie précédente indique que l’utilisateur test a été refusé l’accès à Lync Server lui-même.</span><span class="sxs-lookup"><span data-stu-id="02695-143">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="02695-144">Cela signifie généralement que les informations d’identification de l’utilisateur transmises à Test-CsDialInConferencing n’étaient pas valides.</span><span class="sxs-lookup"><span data-stu-id="02695-144">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="02695-145">Ensuite, vous devez recréer l’objet d’informations d’identification Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02695-145">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="02695-146">Bien que vous puissiez récupérer le mot de passe du compte d’utilisateur, vous pouvez vérifier l’adresse SIP à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="02695-146">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="02695-147">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="02695-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="02695-148">Voici quelques raisons courantes pour lesquelles Test-CsDialInConferencing peut échouer :</span><span class="sxs-lookup"><span data-stu-id="02695-148">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="02695-149">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="02695-149">You specified a user account that is not valid.</span></span> <span data-ttu-id="02695-150">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="02695-150">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="02695-151">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02695-151">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="02695-152">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="02695-152">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="02695-153">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02695-153">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="02695-154">Le numéro d’accès à la Conférence rendez-vous est peut-être incorrect.</span><span class="sxs-lookup"><span data-stu-id="02695-154">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="02695-155">Vous pouvez retourner votre liste de numéros d’accès aux conférences rendez-vous en cours à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="02695-155">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

