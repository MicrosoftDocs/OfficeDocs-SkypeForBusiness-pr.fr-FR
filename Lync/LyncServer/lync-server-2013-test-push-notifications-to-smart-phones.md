---
title: 'Lync Server 2013 : tester les notifications de transmission vers des téléphones intelligents'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94daa288757e2a0af446b455b951af9a990147b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="eb4d3-102">Tester des notifications de transmission vers des téléphones intelligents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb4d3-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb4d3-103">_**Dernière modification de la rubrique :** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="eb4d3-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb4d3-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="eb4d3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="eb4d3-105">Mois</span><span class="sxs-lookup"><span data-stu-id="eb4d3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb4d3-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="eb4d3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="eb4d3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb4d3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb4d3-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="eb4d3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="eb4d3-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="eb4d3-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="eb4d3-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="eb4d3-112">Description</span><span class="sxs-lookup"><span data-stu-id="eb4d3-112">Description</span></span>

<span data-ttu-id="eb4d3-113">Le service de notifications de transmission (Apple Send notification service et service de notifications de transmission de messages Microsoft) peut envoyer des notifications relatives à des événements tels que les nouveaux messages instantanés et les nouveaux messages vocaux sur des appareils mobiles tels que les iPhone et les téléphones Windows, même si le client Lync sur ces appareils est actuellement suspendu ou en cours d’exécution en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="eb4d3-114">Le service de notifications d’émission est un service basé sur le Cloud qui s’exécute sur les serveurs Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="eb4d3-115">Pour tirer parti des notifications de transmission, vous devez être en mesure de vous connecter au centre de notifications de transmission Clearinghouse et de vous y authentifier.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="eb4d3-116">L’applet de contrôle test-CsMcxPushNotification permet aux administrateurs de vérifier que les demandes de notifications de transmission peuvent être routées via votre serveur Edge vers le centre de notifications de type Clearinghouse.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="eb4d3-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="eb4d3-117">Running the test</span></span>

<span data-ttu-id="eb4d3-118">Pour tester le service de notifications d’émission, appelez l’applet de contrôle de test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="eb4d3-119">Vérifiez que vous spécifiez le nom de domaine complet de votre serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="eb4d3-120">Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="eb4d3-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="eb4d3-121">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="eb4d3-121">Determining success or failure</span></span>

<span data-ttu-id="eb4d3-122">Si test-CsMcxPushNotification réussit l’applet de contrôle, elle renvoie le résultat de test réussite :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="eb4d3-123">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb4d3-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eb4d3-124">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="eb4d3-124">Result : Success</span></span>

<span data-ttu-id="eb4d3-125">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="eb4d3-125">Latency : 00:00:00</span></span>

<span data-ttu-id="eb4d3-126">Error</span><span class="sxs-lookup"><span data-stu-id="eb4d3-126">Error :</span></span>

<span data-ttu-id="eb4d3-127">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="eb4d3-127">Diagnosis :</span></span>

<span data-ttu-id="eb4d3-128">Si test-CsMcxPushNotification n’est pas en mesure de se connecter au centre de notifications de type Clearinghouse, l’applet de connexion ne renverra généralement aucun résultat de test d’échec</span><span class="sxs-lookup"><span data-stu-id="eb4d3-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="eb4d3-129">En règle générale, la commande échoue entièrement.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="eb4d3-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-130">For example:</span></span>

<span data-ttu-id="eb4d3-131">Test-CsMcxPushNotification : une réponse de 504 (délai d’expiration du serveur) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="eb4d3-132">Pour plus d’informations, consultez les détails de l’exception.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-132">See the exception details for more information.</span></span>

<span data-ttu-id="eb4d3-133">À la ligne : 1 car : 27</span><span class="sxs-lookup"><span data-stu-id="eb4d3-133">At line:1 char:27</span></span>

<span data-ttu-id="eb4d3-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="eb4d3-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="eb4d3-135">\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="eb4d3-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="eb4d3-136">\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="eb4d3-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="eb4d3-137">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="eb4d3-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="eb4d3-138">Si le service de notifications de transmission ne fonctionne pas, ce qui signifie généralement que vous rencontrez des problèmes de communication avec votre serveur Edge ou que vous rencontrez des problèmes pour communiquer avec le centre de suppression</span><span class="sxs-lookup"><span data-stu-id="eb4d3-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="eb4d3-139">Si vous rencontrez des problèmes lorsque vous exécutez test-CsMcxPushNotification, la première chose à faire est de vérifier que votre serveur Edge fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="eb4d3-140">Pour cela, vous pouvez utiliser l’applet de contrôle CsAVEdgeConnectivity :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="eb4d3-141">Ce contrôle vérifie qu’un utilisateur spécifié peut se connecter au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="eb4d3-142">Si le serveur Edge semble fonctionner correctement, il se peut que vous ne puissiez pas vous connecter au centre de notifications de transmission Clearinghouse.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="eb4d3-143">En règle générale, cela signifie généralement que vous n’avez pas configuré l’URI de Clearinghouse correctement ou que vous n’avez pas d’enregistrement SRV DNS qui pointe vers cette URL.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="eb4d3-144">Vous pouvez vérifier que l’URI est défini sur la valeur correcte (sip :push@push.lync.com) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="eb4d3-145">Si la propriété PushNotificationProxyUri est définie sur une valeur autre que sip :push@push.lync.com, vous pouvez corriger ce problème à l’aide de l’applet de action Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="eb4d3-146">Par exemple, cette commande définit correctement l’URI au sein de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="eb4d3-147">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="eb4d3-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="eb4d3-148">Si l’URI est configuré correctement, l’étape suivante consiste à vérifier que vous disposez d’un enregistrement DNS SRV qui est résolu vers votre domaine SIP et votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="eb4d3-149">Pour plus d’informations sur la configuration de ces enregistrements, voir la rubrique d’aide configuration requise pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="eb4d3-150">Notez que le message d’erreur suivant indique généralement un problème avec les enregistrements DNS :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="eb4d3-151">Une réponse de 504 (délai d’expiration du serveur) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="eb4d3-152">Pour plus d’informations, consultez les détails de l’exception.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-152">See the exception details for more information.</span></span>

<span data-ttu-id="eb4d3-153">Il est également possible que test-CsMcxConfiguration ne fonctionne pas avec ce message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="eb4d3-154">Test-CsMcxPushNotification : la demande de notifications de type pousser a été refusée.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="eb4d3-155">À la ligne : 1 car : 27</span><span class="sxs-lookup"><span data-stu-id="eb4d3-155">At line:1 char:27</span></span>

<span data-ttu-id="eb4d3-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="eb4d3-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="eb4d3-157">\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="eb4d3-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="eb4d3-158">\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="eb4d3-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="eb4d3-159">Le message « la demande de notifications de transmission a été refusée » s’affiche généralement si vous avez activé le filtrage d’URL et que vous bloquez les préfixes http : et https :.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="eb4d3-160">Vous pouvez déterminer les préfixes bloqués à l’aide d’une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="eb4d3-161">Si http : ou https : apparaissent dans les résultats, vous devez les supprimer de la liste des préfixes bloqués pour que les notifications de transmission fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="eb4d3-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="eb4d3-162">Pour cela, vous pouvez utiliser des commandes similaires à celles-ci :</span><span class="sxs-lookup"><span data-stu-id="eb4d3-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="eb4d3-163">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="eb4d3-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

