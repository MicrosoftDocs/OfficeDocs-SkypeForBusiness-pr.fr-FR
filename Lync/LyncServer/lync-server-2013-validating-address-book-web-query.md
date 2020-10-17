---
title: 'Lync Server 2013 : validation de la requête Web du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae10fa68703393459a72eaab7236f214502a614
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508551"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="9f8fb-102">Validation de la requête Web du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f8fb-102">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f8fb-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9f8fb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8fb-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="9f8fb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f8fb-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="9f8fb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8fb-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="9f8fb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f8fb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f8fb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8fb-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="9f8fb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f8fb-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f8fb-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="9f8fb-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f8fb-112">Description</span><span class="sxs-lookup"><span data-stu-id="9f8fb-112">Description</span></span>

<span data-ttu-id="9f8fb-113">L’applet de commande Test-CsAddressBookWebQuery permet aux administrateurs de vérifier que les utilisateurs peuvent utiliser le service de requête Web du carnet d’adresses pour rechercher un contact spécifique.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="9f8fb-114">Lorsque vous exécutez l’applet de commande, Test-CsAddressBookWebQuery se connectera d’abord au service de ticket Web pour être authentifié.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="9f8fb-115">Si l’authentification réussit, l’applet de commande se connecte au service de requête Web du carnet d’adresses et recherche le contact spécifié.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="9f8fb-116">Si ce contact est trouvé, l’applet de commande tente de renvoyer ces informations à l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="9f8fb-117">Le test sera marqué comme étant une réussite uniquement si toutes ces étapes peuvent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="9f8fb-118">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="9f8fb-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f8fb-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="9f8fb-119">Running the test</span></span>

<span data-ttu-id="9f8fb-120">L’applet de commande Test-CsAddressBookWebQuery peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9f8fb-121">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server et l’adresse SIP de l’utilisateur agissant comme cible de la recherche.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="9f8fb-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="9f8fb-123">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell qui contient un nom d’utilisateur et un mot de passe valides.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="9f8fb-124">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque le code appelle test-CsAddressBookWebQuery :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9f8fb-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="9f8fb-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f8fb-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="9f8fb-126">Determining success or failure</span></span>

<span data-ttu-id="9f8fb-127">Si l’utilisateur spécifié peut se connecter au service de carnet d’adresses et récupérer l’adresse de l’utilisateur ciblé, vous obtiendrez un résultat similaire à celui-ci avec la propriété Result marquée comme Success :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="9f8fb-128">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="9f8fb-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="9f8fb-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f8fb-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f8fb-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="9f8fb-130">Result : Success</span></span>

<span data-ttu-id="9f8fb-131">Latence : 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="9f8fb-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="9f8fb-132">«</span><span class="sxs-lookup"><span data-stu-id="9f8fb-132">Error :</span></span>

<span data-ttu-id="9f8fb-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9f8fb-133">Diagnosis :</span></span>

<span data-ttu-id="9f8fb-134">Si l’utilisateur spécifié ne peut pas se connecter ou si l’adresse de l’utilisateur cible ne peut pas être récupérée, le résultat s’affiche en panne et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9f8fb-135">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="9f8fb-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="9f8fb-136">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f8fb-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f8fb-137">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="9f8fb-137">Result : Failure</span></span>

<span data-ttu-id="9f8fb-138">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f8fb-138">Latency : 00:00:00</span></span>

<span data-ttu-id="9f8fb-139">Erreur : la demande de service Web du carnet d’adresses a échoué avec le code de réponse</span><span class="sxs-lookup"><span data-stu-id="9f8fb-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="9f8fb-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-140">NoEntryFound.</span></span>

<span data-ttu-id="9f8fb-141">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="9f8fb-141">Diagnosis :</span></span>

<span data-ttu-id="9f8fb-142">La sortie précédente indique que le test a échoué, car l’utilisateur cible est introuvable.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="9f8fb-143">Vous pouvez déterminer si une adresse SIP valide a été transmise à Test-CsAddressBookWebQuery en exécutant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="9f8fb-144">Si Test-CsAddressBookWebQuery échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="9f8fb-145">Lorsque le paramètre Verbose est inclus, Test-CsAddressBookWebQuery renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9f8fb-146">Par exemple, cette sortie indique que Test-CsAddressBookWebQuery a pu se connecter au service de carnet d’adresses, mais qu’il n’a pas été en mesure de trouver l’adresse SIP cible :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="9f8fb-147">Activité « QueryAddressBookWebService » démarrée.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="9f8fb-148">Appel du service de requête Web du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="9f8fb-149">URL ABWS =</span><span class="sxs-lookup"><span data-stu-id="9f8fb-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="9f8fb-150">Exception de requête de carnet d’adresses : échec de la demande de service Web de carnet d’adresses avec le code de réponse NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f8fb-151">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="9f8fb-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="9f8fb-152">Voici quelques raisons courantes pour lesquelles Test-CsAddressBookWebQuery peut échouer :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="9f8fb-153">Vous avez spécifié un compte d’utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-153">You specified an invalid user account.</span></span> <span data-ttu-id="9f8fb-154">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9f8fb-155">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="9f8fb-156">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9f8fb-157">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="9f8fb-158">L’utilisateur cible n’est peut-être pas dans le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="9f8fb-159">Il se peut que le carnet d’adresses ne dispose pas de la mise à jour et de la réplication complètes.</span><span class="sxs-lookup"><span data-stu-id="9f8fb-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="9f8fb-160">Vous pouvez forcer une mise à jour de tous les serveurs de carnet d’adresses de votre organisation en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f8fb-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

