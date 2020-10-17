---
title: 'Lync Server 2013 : test de l’accès des utilisateurs mobiles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d5be38ecddad1f9388f5e2efb33994b49e4bfd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519211"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="0c97c-102">Tester l’accès des utilisateurs mobiles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c97c-102">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c97c-103">_**Dernière modification de la rubrique :** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="0c97c-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c97c-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="0c97c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0c97c-105">Mensuelle</span><span class="sxs-lookup"><span data-stu-id="0c97c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c97c-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="0c97c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0c97c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c97c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c97c-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="0c97c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0c97c-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0c97c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0c97c-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="0c97c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="0c97c-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0c97c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0c97c-112">Description</span><span class="sxs-lookup"><span data-stu-id="0c97c-112">Description</span></span>

<span data-ttu-id="0c97c-113">Le service de mobilité permet aux utilisateurs d’appareils mobiles d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c97c-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="0c97c-114">Échanger des messages instantanés et des informations de présence.</span><span class="sxs-lookup"><span data-stu-id="0c97c-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="0c97c-115">Stockez et récupérez les messages vocaux en interne au lieu de leur fournisseur sans fil.</span><span class="sxs-lookup"><span data-stu-id="0c97c-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="0c97c-116">Tirez parti des fonctionnalités de Lync Server, telles que l’appel via le bureau et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0c97c-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="0c97c-117">L’applet de commande Test-CsMcxConference offre un moyen rapide et simple de vérifier que les utilisateurs peuvent participer à des conférences Lync Server à l’aide d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="0c97c-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0c97c-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="0c97c-118">Running the test</span></span>

<span data-ttu-id="0c97c-119">Pour exécuter cette vérification, vous devez créer trois objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="0c97c-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="0c97c-120">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez Test-CsMcxConference comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="0c97c-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="0c97c-121">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="0c97c-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0c97c-122">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="0c97c-122">Determining success or failure</span></span>

<span data-ttu-id="0c97c-123">Si la vérification réussit, Test-CsMcxConference signalera un résultat de test réussi :</span><span class="sxs-lookup"><span data-stu-id="0c97c-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="0c97c-124">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c97c-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c97c-125">URI cible : http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="0c97c-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="0c97c-126">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="0c97c-126">Result : Success</span></span>

<span data-ttu-id="0c97c-127">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0c97c-127">Latency : 00:00:00</span></span>

<span data-ttu-id="0c97c-128">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="0c97c-128">Error Message :</span></span>

<span data-ttu-id="0c97c-129">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="0c97c-129">Diagnosis :</span></span>

<span data-ttu-id="0c97c-130">Si la vérification échoue Test-CsMcxConference signale un résultat de test de défaillance.</span><span class="sxs-lookup"><span data-stu-id="0c97c-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="0c97c-131">Ce résultat de test est généralement accompagné d’un message d’erreur détaillé et d’un diagnostic.</span><span class="sxs-lookup"><span data-stu-id="0c97c-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="0c97c-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0c97c-132">For example:</span></span>

<span data-ttu-id="0c97c-133">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c97c-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c97c-134">URI cible : https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="0c97c-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="0c97c-135">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="0c97c-135">Result : Failure</span></span>

<span data-ttu-id="0c97c-136">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0c97c-136">Latency : 00:00:00</span></span>

<span data-ttu-id="0c97c-137">Message d’erreur : aucune réponse reçue pour le service Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="0c97c-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="0c97c-138">Exception interne : la demande HHTP n’est pas autorisée avec le client</span><span class="sxs-lookup"><span data-stu-id="0c97c-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="0c97c-139">schéma de négociation « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="0c97c-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="0c97c-140">En-tête d’authentification reçu</span><span class="sxs-lookup"><span data-stu-id="0c97c-140">The authentication header received</span></span>

<span data-ttu-id="0c97c-141">à partir du serveur était « Negotiate ».</span><span class="sxs-lookup"><span data-stu-id="0c97c-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="0c97c-142">Exception interne : le serveur distant a renvoyé une erreur : (401)</span><span class="sxs-lookup"><span data-stu-id="0c97c-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="0c97c-143">Non autorisé.</span><span class="sxs-lookup"><span data-stu-id="0c97c-143">Unauthorized.</span></span>

<span data-ttu-id="0c97c-144">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="0c97c-144">Diagnosis :</span></span>

<span data-ttu-id="0c97c-145">Diagnostic interne : X-MS-Server-Fqdb : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c97c-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c97c-146">Cache-Control : Private</span><span class="sxs-lookup"><span data-stu-id="0c97c-146">Cache-Control : private</span></span>

<span data-ttu-id="0c97c-147">Content-type : text/html ; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0c97c-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="0c97c-148">Serveur : Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="0c97c-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="0c97c-149">WWW-Authenticate : Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="0c97c-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="0c97c-150">X-alimenté par : ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0c97c-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="0c97c-151">X-Content-type-options : nosniffer</span><span class="sxs-lookup"><span data-stu-id="0c97c-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="0c97c-152">Date : Wed, 28 mai 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="0c97c-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="0c97c-153">Longueur de contenu : 6305</span><span class="sxs-lookup"><span data-stu-id="0c97c-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0c97c-154">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="0c97c-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="0c97c-155">Si Test-CsMcxConference échoue, vous devez commencer par vérifier que le service de mobilité est en cours d’exécution et qu’il est accessible.</span><span class="sxs-lookup"><span data-stu-id="0c97c-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="0c97c-156">Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier que l’URL du service de mobilité de votre pool Lync Server est accessible.</span><span class="sxs-lookup"><span data-stu-id="0c97c-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="0c97c-157">Par exemple, cette commande vérifie l’URL du pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="0c97c-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="0c97c-158">S’il est possible d’accéder au service de mobilité, vous devez vérifier que vos utilisateurs test disposent de comptes Lync Server valides.</span><span class="sxs-lookup"><span data-stu-id="0c97c-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="0c97c-159">Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="0c97c-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="0c97c-160">Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide. Vous devez également vérifier que chaque compte d’utilisateur est activé pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="0c97c-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="0c97c-161">Pour ce faire, commencez par déterminer la stratégie de mobilité affectée au compte :</span><span class="sxs-lookup"><span data-stu-id="0c97c-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="0c97c-162">Une fois que vous avez déterminé le nom de la stratégie, utilisez l’applet de commande Get-CsMobilityPolicy pour vérifier que la propriété EnableMobility de la stratégie en question (par exemple, RedmondMobilityPolicy) a la valeur true :</span><span class="sxs-lookup"><span data-stu-id="0c97c-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="0c97c-163">Si vous recevez un message d’erreur « en-tête d’authentification » lorsque vous exécutez Test-CsMcxConference cela signifie que vous n’avez pas spécifié de compte d’utilisateur valide, vérifiez le nom d’utilisateur et le mot de passe, puis recommencez le test.</span><span class="sxs-lookup"><span data-stu-id="0c97c-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="0c97c-164">Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez l’applet de commande Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="0c97c-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="0c97c-165">Cela vous permettra de savoir quelles méthodes d’authentification sont activées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0c97c-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="0c97c-166">Pour plus d’informations sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [Troubleshooting External Lync Mobility connectivity problems Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c97c-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

