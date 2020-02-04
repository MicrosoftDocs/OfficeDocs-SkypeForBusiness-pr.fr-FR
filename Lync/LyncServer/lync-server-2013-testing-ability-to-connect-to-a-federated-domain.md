---
title: 'Lync Server 2013 : possibilité de test de se connecter à un domaine fédéré'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="be192-102">Le test de la capacité à se connecter à un domaine fédéré à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be192-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be192-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="be192-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be192-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="be192-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="be192-105">Jour</span><span class="sxs-lookup"><span data-stu-id="be192-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be192-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="be192-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="be192-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be192-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be192-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="be192-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="be192-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="be192-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="be192-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="be192-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="be192-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="be192-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="be192-112">Description</span><span class="sxs-lookup"><span data-stu-id="be192-112">Description</span></span>

<span data-ttu-id="be192-113">Test-CsFederatedPartner vérifie la possibilité de se connecter au domaine d’un partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="be192-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="be192-114">Pour vérifier la connectivité d’un domaine, ce domaine doit être répertorié dans la collection de domaines autorisés (fédéré).</span><span class="sxs-lookup"><span data-stu-id="be192-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="be192-115">Vous pouvez récupérer la liste des domaines de votre liste de domaines autorisés en utilisant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="be192-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="be192-116">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="be192-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="be192-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="be192-117">Running the test</span></span>

<span data-ttu-id="be192-118">L’applet de contrôle test-FederatedPartner nécessite deux éléments d’information : le nom de domaine complet (FQDN) de votre serveur Edge et le nom de domaine complet (FQDN) du partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="be192-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="be192-119">Par exemple, la commande suivante permet de tester la capacité à se connecter au domaine contoso.com :</span><span class="sxs-lookup"><span data-stu-id="be192-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="be192-120">Cette commande vous permet de tester les connexions à tous les domaines figurant actuellement dans votre liste de domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="be192-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="be192-121">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="be192-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="be192-122">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="be192-122">Determining success or failure</span></span>

<span data-ttu-id="be192-123">Si le domaine spécifié est joignable, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie :**</span><span class="sxs-lookup"><span data-stu-id="be192-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="be192-124">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be192-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="be192-125">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="be192-125">Result : Success</span></span>

<span data-ttu-id="be192-126">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="be192-126">Latency : 00:00:00</span></span>

<span data-ttu-id="be192-127">Error</span><span class="sxs-lookup"><span data-stu-id="be192-127">Error :</span></span>

<span data-ttu-id="be192-128">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="be192-128">Diagnosis :</span></span>

<span data-ttu-id="be192-129">Si le domaine spécifié ne peut pas être contacté, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="be192-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="be192-130">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be192-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="be192-131">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="be192-131">Result : Failure</span></span>

<span data-ttu-id="be192-132">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="be192-132">Latency : 00:00:00</span></span>

<span data-ttu-id="be192-133">Erreur : 504, délai du serveur</span><span class="sxs-lookup"><span data-stu-id="be192-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="be192-134">Diagnostic : codeerreur = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir</span><span class="sxs-lookup"><span data-stu-id="be192-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="be192-135">Code de réponse et phrase de raison.</span><span class="sxs-lookup"><span data-stu-id="be192-135">response code and reason phrase.</span></span>

<span data-ttu-id="be192-136">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="be192-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="be192-137">Par exemple, la sortie précédente indique que le test a échoué en raison d’une erreur de délai d’expiration du serveur.</span><span class="sxs-lookup"><span data-stu-id="be192-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="be192-138">Cela indique généralement des problèmes de connectivité réseau ou des problèmes de contact du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="be192-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="be192-139">Si test-CsFederatedPartner échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="be192-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="be192-140">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="be192-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="be192-141">Voici quelques raisons courantes pour lesquelles les tests-CsFederatedPartner peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="be192-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="be192-142">Le serveur de périphérie n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="be192-142">The Edge Server might not be available.</span></span> <span data-ttu-id="be192-143">Vous pouvez utiliser les noms de domaine complets de votre serveur Edge en utilisant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="be192-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="be192-144">Vous pouvez ensuite tester chaque serveur Edge pour vérifier qu’il est accessible via le réseau.</span><span class="sxs-lookup"><span data-stu-id="be192-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="be192-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="be192-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="be192-146">Le domaine spécifié n’est peut-être pas répertorié dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="be192-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="be192-147">Pour vérifier les domaines qui ont été ajoutés à la liste des domaines autorisés, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="be192-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="be192-148">Pour afficher une liste des domaines avec lesquels les utilisateurs ne peuvent plus communiquer, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="be192-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

