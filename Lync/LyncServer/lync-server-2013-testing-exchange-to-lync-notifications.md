---
title: 'Lync Server 2013 : test des notifications Exchange vers Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f192d71bbe36bd4e417c06e93152858ac761ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="ffba8-102">Test d’Exchange vers des notifications Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffba8-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffba8-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ffba8-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffba8-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="ffba8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ffba8-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="ffba8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffba8-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="ffba8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ffba8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffba8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffba8-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="ffba8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ffba8-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ffba8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ffba8-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="ffba8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="ffba8-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ffba8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ffba8-112">Description</span><span class="sxs-lookup"><span data-stu-id="ffba8-112">Description</span></span>

<span data-ttu-id="ffba8-113">La cmdlet **test-CsExStorageNotification** est utilisée pour vérifier que le service de notification de Microsoft Exchange Server 2013 peut avertir Lync Server 2013 toutes les mises à jour apportées à la liste des contacts d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ffba8-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="ffba8-114">Cette applet de commande est valide uniquement si vous utilisez le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="ffba8-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ffba8-115">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="ffba8-115">Running the test</span></span>

<span data-ttu-id="ffba8-116">La commande illustrée dans l’exemple 1 vérifie si le service de stockage Lync Server peut se connecter au service de notification de boîte aux lettres Microsoft Exchange Server pour l’utilisateur sip :kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ffba8-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="ffba8-117">Dans cet exemple, NetNamedPipe est utilisé comme liaison WCF.</span><span class="sxs-lookup"><span data-stu-id="ffba8-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ffba8-118">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="ffba8-118">Determining success or failure</span></span>

<span data-ttu-id="ffba8-119">Si l’intégration d’Exchange est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:</span><span class="sxs-lookup"><span data-stu-id="ffba8-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ffba8-120">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ffba8-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ffba8-121">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="ffba8-121">Result : Success</span></span>

<span data-ttu-id="ffba8-122">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ffba8-122">Latency : 00:00:00</span></span>

<span data-ttu-id="ffba8-123">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="ffba8-123">Error Message :</span></span>

<span data-ttu-id="ffba8-124">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="ffba8-124">Diagnosis :</span></span>

<span data-ttu-id="ffba8-125">Si l’utilisateur spécifié ne peut pas recevoir de notifications, le résultat est affiché sous la forme échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="ffba8-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ffba8-126">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ffba8-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ffba8-127">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="ffba8-127">Result : Failure</span></span>

<span data-ttu-id="ffba8-128">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ffba8-128">Latency : 00:00:00</span></span>

<span data-ttu-id="ffba8-129">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="ffba8-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ffba8-130">ne répond pas correctement au bout d’un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="ffba8-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ffba8-131">échec de la connexion établie car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="ffba8-131">established connection failed because connected host has</span></span>

<span data-ttu-id="ffba8-132">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ffba8-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ffba8-133">Exception interne : une tentative de connexion a échoué car le</span><span class="sxs-lookup"><span data-stu-id="ffba8-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ffba8-134">la partie connectée n’a pas répondu correctement après une période de</span><span class="sxs-lookup"><span data-stu-id="ffba8-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ffba8-135">heure ou échec de la connexion établie car l’hôte connecté</span><span class="sxs-lookup"><span data-stu-id="ffba8-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ffba8-136">échec de la réponse de 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ffba8-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ffba8-137">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="ffba8-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ffba8-138">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="ffba8-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="ffba8-139">Voici quelques-unes des causes courantes de l’échec **de test-CsExStorageNotification** :</span><span class="sxs-lookup"><span data-stu-id="ffba8-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="ffba8-140">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="ffba8-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ffba8-141">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="ffba8-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ffba8-142">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="ffba8-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ffba8-143">Cette commande échoue si le serveur Microsoft Exchange est mal configuré ou s’il n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="ffba8-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffba8-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffba8-144">See Also</span></span>


[<span data-ttu-id="ffba8-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="ffba8-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

