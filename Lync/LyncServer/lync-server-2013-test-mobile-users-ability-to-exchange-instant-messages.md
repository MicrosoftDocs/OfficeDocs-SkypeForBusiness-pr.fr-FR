---
title: 'Lync Server 2013 : tester la capacité des utilisateurs mobiles à échanger des messages instantanés'
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
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="a3254-102">Testez la capacité des utilisateurs mobiles à échanger des messages instantanés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3254-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3254-103">_**Dernière modification de la rubrique :** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="a3254-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3254-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="a3254-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a3254-105">Mois</span><span class="sxs-lookup"><span data-stu-id="a3254-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3254-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="a3254-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a3254-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3254-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3254-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="a3254-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a3254-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a3254-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a3254-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="a3254-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="a3254-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a3254-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a3254-112">Description</span><span class="sxs-lookup"><span data-stu-id="a3254-112">Description</span></span>

<span data-ttu-id="a3254-113">Le service de mobilité permet aux utilisateurs de périphériques mobiles d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3254-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="a3254-114">Échangez des messages instantanés et des informations de présence.</span><span class="sxs-lookup"><span data-stu-id="a3254-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="a3254-115">Stockez et récupérez les messages vocaux en interne plutôt qu’avec leur opérateur sans fil.</span><span class="sxs-lookup"><span data-stu-id="a3254-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="a3254-116">Tirez parti des fonctionnalités du serveur Lync, telles que les appels par le biais de tâches et de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="a3254-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="a3254-117">L’applet de contrôle test-CsMxcP2PIM fournit un moyen rapide et facile de vérifier que les utilisateurs peuvent utiliser le service de mobilité pour échanger des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="a3254-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a3254-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="a3254-118">Running the test</span></span>

<span data-ttu-id="a3254-119">Pour effectuer ce test, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom et le mot de passe du compte) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="a3254-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="a3254-120">Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsMcxP2PIM :</span><span class="sxs-lookup"><span data-stu-id="a3254-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="a3254-121">Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="a3254-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a3254-122">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="a3254-122">Determining success or failure</span></span>

<span data-ttu-id="a3254-123">Si les deux utilisateurs de test peuvent échanger des messages instantanés à l’aide du service de mobilité, le test-CsMcxP2PIM renvoie le résultat réussite du test :</span><span class="sxs-lookup"><span data-stu-id="a3254-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="a3254-124">Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3254-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a3254-125">URI de destination :http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="a3254-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="a3254-126">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="a3254-126">Result : Success</span></span>

<span data-ttu-id="a3254-127">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a3254-127">Latency : 00:00:00</span></span>

<span data-ttu-id="a3254-128">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="a3254-128">Error Message :</span></span>

<span data-ttu-id="a3254-129">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="a3254-129">Diagnosis :</span></span>

<span data-ttu-id="a3254-130">Si le test échoue, le résultat est défini sur échec et un message d’erreur et un diagnostic détaillés s’affichent :</span><span class="sxs-lookup"><span data-stu-id="a3254-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="a3254-131">Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3254-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a3254-132">URI de destination :https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="a3254-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="a3254-133">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="a3254-133">Result : Failure</span></span>

<span data-ttu-id="a3254-134">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a3254-134">Latency : 00:00:00</span></span>

<span data-ttu-id="a3254-135">Message d’erreur : aucune réponse n’est reçue pour le service de ticket Web.</span><span class="sxs-lookup"><span data-stu-id="a3254-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="a3254-136">Exception interne : la requête HHTP n’est pas autorisée avec</span><span class="sxs-lookup"><span data-stu-id="a3254-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="a3254-137">le schéma de négociation du client « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="a3254-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="a3254-138">L’authentification</span><span class="sxs-lookup"><span data-stu-id="a3254-138">The authentication</span></span>

<span data-ttu-id="a3254-139">l’en-tête reçu du serveur était « Negotiate, NTLM ».</span><span class="sxs-lookup"><span data-stu-id="a3254-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="a3254-140">Exception interne : le serveur distant a renvoyé une erreur :</span><span class="sxs-lookup"><span data-stu-id="a3254-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="a3254-141">(401) non autorisé.</span><span class="sxs-lookup"><span data-stu-id="a3254-141">(401) Unauthorized.</span></span>

<span data-ttu-id="a3254-142">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="a3254-142">Diagnosis :</span></span>

<span data-ttu-id="a3254-143">Diagnostic interne : X-MS-Server-Fqdb : ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="a3254-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="a3254-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3254-144">001.litwareinc.com</span></span>

<span data-ttu-id="a3254-145">Cache-contrôle : privé</span><span class="sxs-lookup"><span data-stu-id="a3254-145">Cache-Control : private</span></span>

<span data-ttu-id="a3254-146">Type de contenu : texte/html ; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a3254-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="a3254-147">Serveur : Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="a3254-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="a3254-148">WWW-authentifier : Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="a3254-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="a3254-149">X-par : ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a3254-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="a3254-150">X-type de contenu-options : nosniff</span><span class="sxs-lookup"><span data-stu-id="a3254-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="a3254-151">Date : Wed, 28 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="a3254-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="a3254-152">Longueur du contenu : 6305</span><span class="sxs-lookup"><span data-stu-id="a3254-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a3254-153">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="a3254-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="a3254-154">Si test-CsMcxP2PIM échoue, la première étape consiste à vérifier que le service de mobilité est actif et qu’il est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="a3254-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="a3254-155">Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier qu’il est possible d’accéder à l’URL du service de mobilité pour votre pool Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3254-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="a3254-156">Par exemple, la commande suivante vérifie l’URL du pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="a3254-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="a3254-157">Si le service de mobilité semble être en cours d’exécution, assurez-vous que les deux utilisateurs de test disposent de comptes Lync Server valides.</span><span class="sxs-lookup"><span data-stu-id="a3254-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="a3254-158">Vous pouvez récupérer les informations sur le compte à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="a3254-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="a3254-159">Si la propriété Enabled n’est pas égale à true ou en cas d’échec de la commande, cela signifie que l’utilisateur ne possède pas de compte Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="a3254-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="a3254-160">Vous devez également vérifier que l’utilisateur est activé pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="a3254-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="a3254-161">Pour ce faire, vous devez d’abord déterminer la stratégie de mobilité affectée au compte :</span><span class="sxs-lookup"><span data-stu-id="a3254-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="a3254-162">Lorsque vous connaissez le nom de la stratégie, utilisez l’applet de contrôle Get-CsMobilityPolicy pour vérifier que la stratégie en question (par exemple, RedmondMobilityPolicy) a la propriété EnableMobility définie sur la valeur true :</span><span class="sxs-lookup"><span data-stu-id="a3254-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="a3254-163">Si vous recevez un message d’erreur avec des en-têtes d’authentification, cela signifie souvent que vous n’avez pas spécifié de compte d’utilisateur valide.</span><span class="sxs-lookup"><span data-stu-id="a3254-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="a3254-164">Vérifiez le nom d’utilisateur et le mot de passe, puis relancez le test.</span><span class="sxs-lookup"><span data-stu-id="a3254-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="a3254-165">Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez l’applet de contrôle Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth.</span><span class="sxs-lookup"><span data-stu-id="a3254-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="a3254-166">Cela vous indique les méthodes d’authentification activées au sein de votre organisation. Pour obtenir des conseils supplémentaires sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [résolution des problèmes de connectivité externes Lync Mobility](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3254-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

