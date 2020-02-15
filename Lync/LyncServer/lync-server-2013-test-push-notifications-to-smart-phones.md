---
title: 'Lync Server 2013 : test des notifications envoyées vers des téléphones intelligents'
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
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="9bc4e-102">Test des notifications de type poussé vers les téléphones intelligents dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bc4e-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc4e-103">_**Dernière modification de la rubrique :** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="9bc4e-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bc4e-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="9bc4e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9bc4e-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="9bc4e-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc4e-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="9bc4e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9bc4e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bc4e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc4e-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="9bc4e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9bc4e-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9bc4e-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="9bc4e-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9bc4e-112">Description</span><span class="sxs-lookup"><span data-stu-id="9bc4e-112">Description</span></span>

<span data-ttu-id="9bc4e-113">Le service de notifications par émission (service de notifications d’appels poussés Apple et le service de notifications poussés Microsoft) peut envoyer des notifications sur des événements tels que de nouveaux messages instantanés ou de nouveaux messages vocaux à des appareils mobiles tels que des iPhone et des téléphones Windows, même si le client Lync sur ces appareils est actuellement suspendu ou en cours d’exécution en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="9bc4e-114">Le service de notifications d’envoi de notifications est un service en nuage qui s’exécute sur des serveurs Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="9bc4e-115">Pour pouvoir tirer parti des notifications de type « transmission », vous devez être en mesure de vous connecter à, et être authentifié par le centre d’aide à la notification.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="9bc4e-116">L’applet de commande test-CsMcxPushNotification permet aux administrateurs de vérifier que les demandes de notifications de type transmission peuvent être acheminées via votre serveur Edge vers le centre d’administration de notifications.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9bc4e-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="9bc4e-117">Running the test</span></span>

<span data-ttu-id="9bc4e-118">Pour tester le service de notifications d’envoi, appelez la cmdlet Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="9bc4e-119">Assurez-vous que vous spécifiez le nom de domaine complet de votre serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="9bc4e-120">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="9bc4e-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9bc4e-121">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="9bc4e-121">Determining success or failure</span></span>

<span data-ttu-id="9bc4e-122">Si test-CsMcxPushNotification réussit, l’applet de commande renvoie le résultat du test réussite :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="9bc4e-123">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9bc4e-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9bc4e-124">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="9bc4e-124">Result : Success</span></span>

<span data-ttu-id="9bc4e-125">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9bc4e-125">Latency : 00:00:00</span></span>

<span data-ttu-id="9bc4e-126">«</span><span class="sxs-lookup"><span data-stu-id="9bc4e-126">Error :</span></span>

<span data-ttu-id="9bc4e-127">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9bc4e-127">Diagnosis :</span></span>

<span data-ttu-id="9bc4e-128">Si test-CsMcxPushNotification ne parvient pas à se connecter au centre d’information de notifications, l’applet de commande ne renverra généralement pas de résultat de test de défaillance.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="9bc4e-129">Au lieu de cela, la commande échouera généralement entièrement.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="9bc4e-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-130">For example:</span></span>

<span data-ttu-id="9bc4e-131">Test-CsMcxPushNotification : une réponse de 504 (délai d’attente du serveur) a été reçue du réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="9bc4e-132">Pour plus d’informations, consultez les détails de l’exception.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-132">See the exception details for more information.</span></span>

<span data-ttu-id="9bc4e-133">À la ligne : 1 char : 27</span><span class="sxs-lookup"><span data-stu-id="9bc4e-133">At line:1 char:27</span></span>

<span data-ttu-id="9bc4e-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="9bc4e-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="9bc4e-135">\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="9bc4e-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="9bc4e-136">\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="9bc4e-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9bc4e-137">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="9bc4e-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="9bc4e-138">Si le service de notification d’envoi échoue, cela signifie généralement que des problèmes de communication avec votre serveur Edge ou des problèmes de communication avec le centre d’échanges de notifications d’envoi échouent.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="9bc4e-139">Si vous rencontrez des problèmes lors de l’exécution de test-CsMcxPushNotification, la première chose que vous devez faire est de vérifier que votre serveur Edge fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="9bc4e-140">Pour cela, vous pouvez utiliser la cmdlet Test-CsAVEdgeConnectivity :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9bc4e-141">Cette vérification vérifie qu’un utilisateur spécifié peut se connecter au serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="9bc4e-142">Si le serveur Edge semble fonctionner correctement, cela signifie que vous ne pouvez pas vous connecter au centre d’aide à la notification.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="9bc4e-143">En règle générale, cela signifie que vous n’avez pas configuré l’URI du centre d’aide correctement ou que vous n’avez pas d’enregistrement DNS SRV qui pointe vers cette URL.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="9bc4e-144">Vous pouvez vérifier que l’URI est défini sur la valeur correcte (sip :push@push.lync.com) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="9bc4e-145">Si la propriété PushNotificationProxyUri est définie sur une valeur autre que sip :push@push.lync.com, vous pouvez corriger ce problème à l’aide de la cmdlet Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="9bc4e-146">Par exemple, cette commande définit correctement l’URI au sein de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="9bc4e-147">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9bc4e-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="9bc4e-148">Si l’URI est correctement configuré, l’étape suivante consiste à vérifier que vous disposez d’un enregistrement DNS SRV qui est résolu vers votre domaine SIP et votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="9bc4e-149">Pour plus d’informations sur la configuration de ces enregistrements, voir la rubrique d’aide configuration DNS requise pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="9bc4e-150">Notez que le message d’erreur suivant indique généralement un problème avec les enregistrements DNS :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="9bc4e-151">Une réponse 504 (délai d’attente du serveur) a été reçue depuis le réseau et l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="9bc4e-152">Pour plus d’informations, consultez les détails de l’exception.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-152">See the exception details for more information.</span></span>

<span data-ttu-id="9bc4e-153">Il est également possible que test-CsMcxConfiguration échoue avec ce message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="9bc4e-154">Test-CsMcxPushNotification : la demande de notifications d’envoi a été rejetée.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="9bc4e-155">À la ligne : 1 char : 27</span><span class="sxs-lookup"><span data-stu-id="9bc4e-155">At line:1 char:27</span></span>

<span data-ttu-id="9bc4e-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="9bc4e-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="9bc4e-157">\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="9bc4e-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="9bc4e-158">\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="9bc4e-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="9bc4e-159">Le message « demande de notifications d’envoi rejetées » s’affiche généralement si vous avez activé le filtrage d’URL et bloque les préfixes http : et https :.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="9bc4e-160">Vous pouvez déterminer les préfixes bloqués à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="9bc4e-161">Si http : ou https : apparaissent dans les résultats, vous devez les supprimer de la liste des préfixes bloqués pour que les notifications de type transmission fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="9bc4e-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="9bc4e-162">Cela peut être réalisé à l’aide de commandes similaires à celles-ci :</span><span class="sxs-lookup"><span data-stu-id="9bc4e-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="9bc4e-163">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="9bc4e-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

