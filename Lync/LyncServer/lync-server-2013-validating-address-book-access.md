---
title: 'Lync Server 2013 : validation de l’accès au carnet d’adresses'
description: 'Lync Server 2013 : validation de l’accès au carnet d’adresses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547240"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="a55b5-103">Validation de l’accès au carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a55b5-103">Validating address book access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a55b5-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a55b5-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a55b5-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="a55b5-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a55b5-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="a55b5-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a55b5-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="a55b5-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a55b5-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a55b5-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a55b5-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="a55b5-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a55b5-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a55b5-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a55b5-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="a55b5-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="a55b5-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a55b5-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a55b5-113">Description</span><span class="sxs-lookup"><span data-stu-id="a55b5-113">Description</span></span>

<span data-ttu-id="a55b5-114">L’applet de commande Test-CsAddressBookService vous permet de vérifier qu’un utilisateur peut se connecter au service Web de téléchargement du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a55b5-114">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="a55b5-115">Lorsque vous exécutez l’applet de commande, Test-CsAddressBookService se connecte au service Web de téléchargement du carnet d’adresses sur le pool spécifié et demande l’emplacement des fichiers du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a55b5-115">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="a55b5-116">Si le service Web de téléchargement du carnet d’adresses fournit cet emplacement, le test est considéré comme réussi.</span><span class="sxs-lookup"><span data-stu-id="a55b5-116">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="a55b5-117">Si la demande est rejetée, cela signifie que la vérification a échoué.</span><span class="sxs-lookup"><span data-stu-id="a55b5-117">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a55b5-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="a55b5-118">Running the test</span></span>

<span data-ttu-id="a55b5-119">La cmdlet Test-CsAddressBookService peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de n’importe quel utilisateur qui a été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a55b5-119">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="a55b5-120">Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="a55b5-120">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="a55b5-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a55b5-121">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a55b5-122">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a55b5-122">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="a55b5-123">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lors de l’appel de test-CsAddressBookService :</span><span class="sxs-lookup"><span data-stu-id="a55b5-123">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a55b5-124">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="a55b5-124">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a55b5-125">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="a55b5-125">Determining success or failure</span></span>

<span data-ttu-id="a55b5-126">Si l’utilisateur spécifié est en mesure de se connecter au service de carnet d’adresses, vous obtiendrez un résultat similaire à celui-ci, avec la propriété Result marquée comme **Success**:</span><span class="sxs-lookup"><span data-stu-id="a55b5-126">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a55b5-127">TargetUri https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="a55b5-127">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="a55b5-128">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a55b5-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a55b5-129">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="a55b5-129">Result : Success</span></span>

<span data-ttu-id="a55b5-130">Latence : 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="a55b5-130">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="a55b5-131">«</span><span class="sxs-lookup"><span data-stu-id="a55b5-131">Error :</span></span>

<span data-ttu-id="a55b5-132">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="a55b5-132">Diagnosis :</span></span>

<span data-ttu-id="a55b5-133">Si l’utilisateur spécifié ne parvient pas à établir cette connexion, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="a55b5-133">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a55b5-134">TargetUri</span><span class="sxs-lookup"><span data-stu-id="a55b5-134">TargetUri :</span></span>

<span data-ttu-id="a55b5-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a55b5-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a55b5-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="a55b5-136">Result : Failure</span></span>

<span data-ttu-id="a55b5-137">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a55b5-137">Latency : 00:00:00</span></span>

<span data-ttu-id="a55b5-138">Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="a55b5-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="a55b5-139">Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas</span><span class="sxs-lookup"><span data-stu-id="a55b5-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="a55b5-140">présent.</span><span class="sxs-lookup"><span data-stu-id="a55b5-140">exist.</span></span>

<span data-ttu-id="a55b5-141">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="a55b5-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="a55b5-142">Par exemple, la sortie précédente indique que le test a échoué, car l’utilisateur spécifié (c’est-à-dire, « l’URI de destination ») n’existe pas ou n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a55b5-142">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="a55b5-143">Vous pouvez vérifier si un compte d’utilisateur est valide, et vérifier que vous avez fourni l’adresse SIP correcte en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="a55b5-143">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="a55b5-144">Get-CsUser-Identity « sip :kenmyer@litwareinc.com » | Select-Object SipAddress, activé</span><span class="sxs-lookup"><span data-stu-id="a55b5-144">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="a55b5-145">Si Test-CsAddressBookService échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="a55b5-145">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="a55b5-146">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="a55b5-146">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="a55b5-147">Lorsque le paramètre Verbose est inclus Test-CsAddressBookService renverra un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a55b5-147">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a55b5-148">Par exemple, cet exemple de sortie indique que test-CsAddressBookService, au moins dans cet exemple, a pu télécharger le fichier de carnet d’adresses :</span><span class="sxs-lookup"><span data-stu-id="a55b5-148">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="a55b5-149">Envoi d’une demande HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="a55b5-149">Sending Http GET Request.</span></span>

<span data-ttu-id="a55b5-150">Chemin d’accès du fichier = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a55b5-150">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="a55b5-151">Numéro de tentative = 1</span><span class="sxs-lookup"><span data-stu-id="a55b5-151">Attempt Number = 1</span></span>

<span data-ttu-id="a55b5-152">Délai d’expiration (msec) = 60000</span><span class="sxs-lookup"><span data-stu-id="a55b5-152">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="a55b5-153">Téléchargement du fichier ABS réussi https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a55b5-153">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a55b5-154">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="a55b5-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="a55b5-155">Voici quelques raisons courantes pour lesquelles Test-CsAddressBookService peut échouer :</span><span class="sxs-lookup"><span data-stu-id="a55b5-155">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="a55b5-156">Vous avez spécifié un compte d’utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="a55b5-156">You specified an invalid user account.</span></span> <span data-ttu-id="a55b5-157">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="a55b5-157">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a55b5-158">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a55b5-158">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="a55b5-159">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="a55b5-159">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a55b5-160">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a55b5-160">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a55b5-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a55b5-161">See Also</span></span>


[<span data-ttu-id="a55b5-162">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="a55b5-162">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

