---
title: 'Lync Server 2013 : test de la capacité des utilisateurs mobiles à échanger des messages instantanés'
description: 'Lync Server 2013 : test de la capacité des utilisateurs mobiles à échanger des messages instantanés.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558290"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="001a4-103">Tester la capacité des utilisateurs mobiles à échanger des messages instantanés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="001a4-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="001a4-104">_**Dernière modification de la rubrique :** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="001a4-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="001a4-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="001a4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="001a4-106">Mensuelle</span><span class="sxs-lookup"><span data-stu-id="001a4-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="001a4-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="001a4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="001a4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="001a4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="001a4-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="001a4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="001a4-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="001a4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="001a4-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="001a4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="001a4-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="001a4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="001a4-113">Description</span><span class="sxs-lookup"><span data-stu-id="001a4-113">Description</span></span>

<span data-ttu-id="001a4-114">Le service de mobilité permet aux utilisateurs d’appareils mobiles d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="001a4-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="001a4-115">Échanger des messages instantanés et des informations de présence.</span><span class="sxs-lookup"><span data-stu-id="001a4-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="001a4-116">Stockez et récupérez les messages vocaux en interne au lieu de leur fournisseur sans fil.</span><span class="sxs-lookup"><span data-stu-id="001a4-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="001a4-117">Tirez parti des fonctionnalités de Lync Server, telles que l’appel via le bureau et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="001a4-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="001a4-118">L’applet de commande Test-CsMxcP2PIM offre un moyen rapide et facile de vérifier que les utilisateurs peuvent utiliser le service de mobilité pour échanger des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="001a4-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="001a4-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="001a4-119">Running the test</span></span>

<span data-ttu-id="001a4-120">Pour exécuter ce test, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="001a4-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="001a4-121">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsMcxP2PIM :</span><span class="sxs-lookup"><span data-stu-id="001a4-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="001a4-122">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="001a4-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="001a4-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="001a4-123">Determining success or failure</span></span>

<span data-ttu-id="001a4-124">Si les deux utilisateurs de test peuvent échanger des messages instantanés à l’aide du service de mobilité, Test-CsMcxP2PIM renverra le résultat de test réussite :</span><span class="sxs-lookup"><span data-stu-id="001a4-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="001a4-125">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="001a4-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="001a4-126">URI cible : http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="001a4-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="001a4-127">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="001a4-127">Result : Success</span></span>

<span data-ttu-id="001a4-128">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="001a4-128">Latency : 00:00:00</span></span>

<span data-ttu-id="001a4-129">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="001a4-129">Error Message :</span></span>

<span data-ttu-id="001a4-130">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="001a4-130">Diagnosis :</span></span>

<span data-ttu-id="001a4-131">Si le test échoue, le résultat est défini sur échec et un message d’erreur détaillé et un diagnostic s’affichent :</span><span class="sxs-lookup"><span data-stu-id="001a4-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="001a4-132">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="001a4-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="001a4-133">URI cible : https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="001a4-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="001a4-134">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="001a4-134">Result : Failure</span></span>

<span data-ttu-id="001a4-135">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="001a4-135">Latency : 00:00:00</span></span>

<span data-ttu-id="001a4-136">Message d’erreur : aucune réponse reçue pour le service Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="001a4-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="001a4-137">Exception interne : la demande HHTP n’est pas autorisée avec</span><span class="sxs-lookup"><span data-stu-id="001a4-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="001a4-138">schéma de négociation client « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="001a4-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="001a4-139">L’authentification</span><span class="sxs-lookup"><span data-stu-id="001a4-139">The authentication</span></span>

<span data-ttu-id="001a4-140">l’en-tête reçu du serveur était « Negotiate, NTLM ».</span><span class="sxs-lookup"><span data-stu-id="001a4-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="001a4-141">Exception interne : le serveur distant a renvoyé une erreur :</span><span class="sxs-lookup"><span data-stu-id="001a4-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="001a4-142">(401) non autorisé.</span><span class="sxs-lookup"><span data-stu-id="001a4-142">(401) Unauthorized.</span></span>

<span data-ttu-id="001a4-143">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="001a4-143">Diagnosis :</span></span>

<span data-ttu-id="001a4-144">Diagnostic interne : X-MS-Server-Fqdb : ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="001a4-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="001a4-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="001a4-145">001.litwareinc.com</span></span>

<span data-ttu-id="001a4-146">Cache-Control : Private</span><span class="sxs-lookup"><span data-stu-id="001a4-146">Cache-Control : private</span></span>

<span data-ttu-id="001a4-147">Content-type : text/html ; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="001a4-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="001a4-148">Serveur : Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="001a4-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="001a4-149">WWW-Authenticate : Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="001a4-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="001a4-150">X-alimenté par : ASP.NET</span><span class="sxs-lookup"><span data-stu-id="001a4-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="001a4-151">X-Content-type-options : nosniffer</span><span class="sxs-lookup"><span data-stu-id="001a4-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="001a4-152">Date : Wed, 28 mai 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="001a4-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="001a4-153">Longueur de contenu : 6305</span><span class="sxs-lookup"><span data-stu-id="001a4-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="001a4-154">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="001a4-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="001a4-155">Si Test-CsMcxP2PIM échoue, la première étape consiste à vérifier que le service de mobilité est opérationnel.</span><span class="sxs-lookup"><span data-stu-id="001a4-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="001a4-156">Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier que l’URL du service de mobilité de votre pool Lync Server est accessible.</span><span class="sxs-lookup"><span data-stu-id="001a4-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="001a4-157">Par exemple, cette commande vérifie l’URL du pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="001a4-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="001a4-158">Si le service de mobilité semble être en cours d’exécution, vérifiez que vos deux utilisateurs test ont des comptes Lync Server valides.</span><span class="sxs-lookup"><span data-stu-id="001a4-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="001a4-159">Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="001a4-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="001a4-160">Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="001a4-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="001a4-161">Vous devez également vérifier que l’utilisateur est activé pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="001a4-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="001a4-162">Pour ce faire, commencez par déterminer la stratégie de mobilité affectée au compte :</span><span class="sxs-lookup"><span data-stu-id="001a4-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="001a4-163">Une fois que vous avez déterminé le nom de la stratégie, utilisez l’applet de commande Get-CsMobilityPolicy pour vérifier que la propriété EnableMobility de la stratégie en question (par exemple, RedmondMobilityPolicy) a la valeur true :</span><span class="sxs-lookup"><span data-stu-id="001a4-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="001a4-164">Si vous recevez un message d’erreur avec des en-têtes d’authentification, cela signifie que vous n’avez pas spécifié de compte d’utilisateur valide.</span><span class="sxs-lookup"><span data-stu-id="001a4-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="001a4-165">Vérifiez le nom d’utilisateur et le mot de passe, puis recommencez le test.</span><span class="sxs-lookup"><span data-stu-id="001a4-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="001a4-166">Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez l’applet de commande Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="001a4-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="001a4-167">Cela vous permettra de savoir quelles méthodes d’authentification sont activées dans votre organisation. Pour plus d’informations sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [Troubleshooting External Lync Mobility connectivity problems Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="001a4-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

