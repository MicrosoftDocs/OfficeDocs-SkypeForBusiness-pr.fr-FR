---
title: 'Lync Server 2013 : test de la fonctionnalité de connexion à un domaine fédéré'
description: 'Lync Server 2013 : test de la fonctionnalité de connexion à un domaine fédéré.'
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
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560820"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="b3ad2-103">Test de la possibilité de se connecter à un domaine fédéré à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3ad2-103">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3ad2-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b3ad2-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3ad2-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="b3ad2-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b3ad2-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="b3ad2-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ad2-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b3ad2-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b3ad2-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3ad2-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3ad2-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b3ad2-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b3ad2-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b3ad2-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="b3ad2-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b3ad2-113">Description</span><span class="sxs-lookup"><span data-stu-id="b3ad2-113">Description</span></span>

<span data-ttu-id="b3ad2-114">Test-CsFederatedPartner vérifie votre capacité à vous connecter au domaine d’un partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-114">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="b3ad2-115">Pour vérifier la connectivité à un domaine, ce domaine doit être mentionné dans la collection de domaines autorisés (fédérés).</span><span class="sxs-lookup"><span data-stu-id="b3ad2-115">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="b3ad2-116">Vous pouvez récupérer la liste des domaines de votre liste de domaines autorisés à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-116">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="b3ad2-117">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="b3ad2-117">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b3ad2-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b3ad2-118">Running the test</span></span>

<span data-ttu-id="b3ad2-119">La cmdlet Test-FederatedPartner nécessite deux informations : le nom de domaine complet (FQDN) de votre serveur Edge et le nom de domaine complet (FQDN) du partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-119">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="b3ad2-120">Par exemple, cette commande teste la capacité à se connecter au domaine contoso.com :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-120">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="b3ad2-121">Cette commande vous permet de tester les connexions à tous les domaines figurant actuellement dans la liste des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-121">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="b3ad2-122">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="b3ad2-122">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b3ad2-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="b3ad2-123">Determining success or failure</span></span>

<span data-ttu-id="b3ad2-124">Si le domaine spécifié peut être contacté, vous recevrez un résultat semblable à celui-ci avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="b3ad2-124">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b3ad2-125">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3ad2-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3ad2-126">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="b3ad2-126">Result : Success</span></span>

<span data-ttu-id="b3ad2-127">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b3ad2-127">Latency : 00:00:00</span></span>

<span data-ttu-id="b3ad2-128">«</span><span class="sxs-lookup"><span data-stu-id="b3ad2-128">Error :</span></span>

<span data-ttu-id="b3ad2-129">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="b3ad2-129">Diagnosis :</span></span>

<span data-ttu-id="b3ad2-130">Si le domaine spécifié ne peut pas être contacté, le résultat est affiché en tant que échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-130">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b3ad2-131">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3ad2-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3ad2-132">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="b3ad2-132">Result : Failure</span></span>

<span data-ttu-id="b3ad2-133">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b3ad2-133">Latency : 00:00:00</span></span>

<span data-ttu-id="b3ad2-134">Erreur : 504, délai d’attente du serveur</span><span class="sxs-lookup"><span data-stu-id="b3ad2-134">Error : 504, Server time-out</span></span>

<span data-ttu-id="b3ad2-135">Diagnostic : ErrorCode = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir</span><span class="sxs-lookup"><span data-stu-id="b3ad2-135">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="b3ad2-136">Code de réponse et expression de motif.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-136">response code and reason phrase.</span></span>

<span data-ttu-id="b3ad2-137">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="b3ad2-137">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="b3ad2-138">Par exemple, la sortie précédente indique que le test a échoué en raison d’une erreur de délai d’attente du serveur.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-138">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="b3ad2-139">Cela indique généralement des problèmes de connectivité réseau ou des problèmes de contact avec le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-139">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="b3ad2-140">Si Test-CsFederatedPartner échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-140">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b3ad2-141">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="b3ad2-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="b3ad2-142">Voici quelques raisons courantes pour lesquelles Test-CsFederatedPartner peut échouer :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-142">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="b3ad2-143">Le serveur Edge n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-143">The Edge Server might not be available.</span></span> <span data-ttu-id="b3ad2-144">Vous pouvez utiliser cette commande pour les noms de domaine complets de vos serveurs Edge :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-144">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="b3ad2-145">Vous pouvez ensuite exécuter la commande ping sur chaque serveur Edge pour vérifier qu’il est accessible sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-145">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="b3ad2-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-146">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="b3ad2-147">Le domaine spécifié n’est peut-être pas répertorié dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="b3ad2-147">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="b3ad2-148">Pour vérifier les domaines qui ont été ajoutés à la liste des domaines autorisés, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-148">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="b3ad2-149">Si vous souhaitez afficher la liste des domaines avec lesquels les utilisateurs ne peuvent pas communiquer, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b3ad2-149">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

