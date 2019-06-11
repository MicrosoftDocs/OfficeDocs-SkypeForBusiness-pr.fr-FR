---
title: 'Lync Server 2013: possibilité de test d’utiliser l’extension de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="58788-102">Fonctionnalité de test permettant d’utiliser l’extension de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58788-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58788-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="58788-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58788-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="58788-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="58788-105">Jour</span><span class="sxs-lookup"><span data-stu-id="58788-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58788-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="58788-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="58788-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58788-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58788-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="58788-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="58788-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="58788-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="58788-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="58788-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="58788-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="58788-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="58788-112">Description</span><span class="sxs-lookup"><span data-stu-id="58788-112">Description</span></span>

<span data-ttu-id="58788-113">L’applet de contrôle test-CsGroupExpansion vous permet de déterminer si l’extension de groupe fonctionne au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="58788-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="58788-114">Lorsque l’extension du groupe est activée, les utilisateurs configurent les groupes de distribution en tant que contact.</span><span class="sxs-lookup"><span data-stu-id="58788-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="58788-115">Cela signifie que les utilisateurs peuvent alors envoyer le même message instantané à tous les membres du groupe en envoyant le message au groupe plutôt qu’à des membres individuels du groupe.</span><span class="sxs-lookup"><span data-stu-id="58788-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="58788-116">L’extension de groupe vous permet d’afficher rapidement et facilement tous les membres du groupe et leur statut actuel.</span><span class="sxs-lookup"><span data-stu-id="58788-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="58788-117">À l’aide de l’applet de contrôle test-CsGroupExpansion, vous spécifiez un groupe de distribution Active Directory à l’aide de l’adresse de messagerie du groupe.</span><span class="sxs-lookup"><span data-stu-id="58788-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="58788-118">Test-CsGroupExpansion utilise alors l’extension de groupe pour récupérer l’appartenance au groupe et comparer la liste récupérée à l’appartenance de l’adresse de messagerie de groupe que vous avez fournie.</span><span class="sxs-lookup"><span data-stu-id="58788-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="58788-119">Si les deux listes correspondent, l’extension du groupe fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="58788-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="58788-120">Notez que vous pouvez tester l’extension du groupe de deux manières: en testant le service proprement dit ou en testant le service Web associé.</span><span class="sxs-lookup"><span data-stu-id="58788-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="58788-121">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="58788-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="58788-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="58788-122">Running the test</span></span>

<span data-ttu-id="58788-123">Vous pouvez exécuter l’applet de contrôle test-CsGroupExpansion à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte de tout utilisateur ayant activé Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="58788-124">Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé et l’adresse de courrier d’un groupe de distribution valide.</span><span class="sxs-lookup"><span data-stu-id="58788-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="58788-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="58788-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="58788-126">Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Lync Server contenant le nom et le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="58788-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="58788-127">Lorsque le système appelle test-CsGroupExpansion, vous devez inclure l’objet Credential et l’adresse SIP associée au compte.</span><span class="sxs-lookup"><span data-stu-id="58788-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="58788-128">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="58788-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="58788-129">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="58788-129">Determining success or failure</span></span>

<span data-ttu-id="58788-130">Si l’utilisateur spécifié peut utiliser l’extension de groupe, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="58788-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="58788-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="58788-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="58788-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="58788-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="58788-133">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="58788-133">Result : Success</span></span>

<span data-ttu-id="58788-134">Latence: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="58788-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="58788-135">Error</span><span class="sxs-lookup"><span data-stu-id="58788-135">Error :</span></span>

<span data-ttu-id="58788-136">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="58788-136">Diagnosis :</span></span>

<span data-ttu-id="58788-137">Si l’utilisateur spécifié ne peut pas utiliser l’extension de groupe, le résultat s’affichera en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="58788-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="58788-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="58788-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="58788-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="58788-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="58788-140">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="58788-140">Result : Failure</span></span>

<span data-ttu-id="58788-141">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="58788-141">Latency : 00:00:00</span></span>

<span data-ttu-id="58788-142">Error</span><span class="sxs-lookup"><span data-stu-id="58788-142">Error :</span></span>

<span data-ttu-id="58788-143">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="58788-143">Diagnosis :</span></span>

<span data-ttu-id="58788-144">Test-CsGroupExpansion: le point de terminaison n’a pas pu s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="58788-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="58788-145">Afficher le code d’après pour une raison spécifique.</span><span class="sxs-lookup"><span data-stu-id="58788-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="58788-146">La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’a pas pu s’inscrire sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="58788-147">Cela se produit généralement si le compte de test n’existe pas ou n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="58788-148">Vous pouvez vérifier que le compte existe et déterminez si le compte a été activé pour nm-OCS-14-3e en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="58788-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="58788-149">Si test-CsGroupExpansion échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:</span><span class="sxs-lookup"><span data-stu-id="58788-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="58788-150">Lorsque le paramètre Verbose est inclus, le test-CsGroupExpansion renvoie un compte détaillé de chaque action qu’il a exécutée lorsqu’il a vérifié la possibilité de l’utilisateur spécifié de se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="58788-151">Par exemple, cette sortie indique que le groupe de distribution spécifié est introuvable:</span><span class="sxs-lookup"><span data-stu-id="58788-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="58788-152">Essayez d’obtenir le ticket Web.</span><span class="sxs-lookup"><span data-stu-id="58788-152">Trying to get web ticket.</span></span>

<span data-ttu-id="58788-153">URL du service Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="58788-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="58788-154">À l’aide de l’authentification NTLM/Kerb.</span><span class="sxs-lookup"><span data-stu-id="58788-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="58788-155">GetWebTicketActivity terminé.</span><span class="sxs-lookup"><span data-stu-id="58788-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="58788-156">Activité «VerifyDistributionList» démarrée.</span><span class="sxs-lookup"><span data-stu-id="58788-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="58788-157">DLX état de réponse du service Web est: NotFound.</span><span class="sxs-lookup"><span data-stu-id="58788-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="58788-158">Activité «VerifyDistributionList» terminée en «0,2597923» secondes.</span><span class="sxs-lookup"><span data-stu-id="58788-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="58788-159">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="58788-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="58788-160">Voici quelques raisons courantes pour lesquelles les tests-CsGroupExpansion peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="58788-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="58788-161">Vous avez spécifié un compte d’utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="58788-161">You specified an invalid user account.</span></span> <span data-ttu-id="58788-162">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="58788-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="58788-163">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="58788-164">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="58788-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="58788-165">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58788-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="58788-166">L’extension du groupe est peut-être désactivée.</span><span class="sxs-lookup"><span data-stu-id="58788-166">Group expansion might be disabled.</span></span> <span data-ttu-id="58788-167">Il est possible de désactiver l’extension de groupe.</span><span class="sxs-lookup"><span data-stu-id="58788-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="58788-168">Si l’extension du groupe a été désactivée, l’applet de contrôle CsGroupExpansion de test échoue.</span><span class="sxs-lookup"><span data-stu-id="58788-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="58788-169">Pour déterminer si l’extension du groupe est activée, utilisez une commande semblable à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="58788-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

