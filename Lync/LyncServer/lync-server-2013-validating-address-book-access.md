---
title: 'Lync Server 2013 : validation de l’accès au carnet d’adresses'
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
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="d9dbf-102">Validation de l’accès au carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9dbf-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9dbf-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d9dbf-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9dbf-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="d9dbf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d9dbf-105">Jour</span><span class="sxs-lookup"><span data-stu-id="d9dbf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9dbf-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="d9dbf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d9dbf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9dbf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9dbf-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="d9dbf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d9dbf-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d9dbf-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="d9dbf-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d9dbf-112">Description</span><span class="sxs-lookup"><span data-stu-id="d9dbf-112">Description</span></span>

<span data-ttu-id="d9dbf-113">L’applet de contrôle test-CsAddressBookService vous permet de vérifier qu’un utilisateur peut se connecter au service Web de téléchargement du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="d9dbf-114">Lorsque vous exécutez l’applet de requête, test-CsAddressBookService se connecte au service Web de téléchargement du carnet d’adresses sur le pool spécifié et demande l’emplacement des fichiers du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="d9dbf-115">Si le service Web de téléchargement de carnet d’adresses fournit cet emplacement, le test est considéré comme réussi.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="d9dbf-116">Si la requête est refusée, le test est considéré comme un échec.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d9dbf-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="d9dbf-117">Running the test</span></span>

<span data-ttu-id="d9dbf-118">Vous pouvez exécuter l’applet de contrôle de test-CsAddressBookService à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui a été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="d9dbf-119">Pour exécuter cette recherche à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="d9dbf-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d9dbf-121">Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d9dbf-122">Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lors de l’appel de test-CsAddressBookService :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d9dbf-123">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="d9dbf-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d9dbf-124">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="d9dbf-124">Determining success or failure</span></span>

<span data-ttu-id="d9dbf-125">Si l’utilisateur spécifié est en mesure de se connecter au service de carnet d’adresses, vous obtiendrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:</span><span class="sxs-lookup"><span data-stu-id="d9dbf-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="d9dbf-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="d9dbf-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="d9dbf-127">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d9dbf-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d9dbf-128">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="d9dbf-128">Result : Success</span></span>

<span data-ttu-id="d9dbf-129">Latence : 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="d9dbf-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="d9dbf-130">Error</span><span class="sxs-lookup"><span data-stu-id="d9dbf-130">Error :</span></span>

<span data-ttu-id="d9dbf-131">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="d9dbf-131">Diagnosis :</span></span>

<span data-ttu-id="d9dbf-132">Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d9dbf-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="d9dbf-133">TargetUri :</span></span>

<span data-ttu-id="d9dbf-134">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d9dbf-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d9dbf-135">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="d9dbf-135">Result : Failure</span></span>

<span data-ttu-id="d9dbf-136">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d9dbf-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d9dbf-137">Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="d9dbf-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="d9dbf-138">Raison = URI de destination non activé pour le SIP ou non</span><span class="sxs-lookup"><span data-stu-id="d9dbf-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="d9dbf-139">Il.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-139">exist.</span></span>

<span data-ttu-id="d9dbf-140">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d9dbf-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d9dbf-141">Par exemple, la sortie précédente indique qu’un test a échoué, car l’utilisateur spécifié (autrement dit, l’URI de destination) n’existe pas ou n’a pas été activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="d9dbf-142">Vous pouvez vérifier qu’un compte d’utilisateur est valide ou non et que vous avez fourni l’adresse SIP correcte en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="d9dbf-143">Get-CsUser-Identity "sip :kenmyer@litwareinc.com" | SipAddress de sélection d’objet activée</span><span class="sxs-lookup"><span data-stu-id="d9dbf-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="d9dbf-144">Si test-CsAddressBookService échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="d9dbf-145">Test-CsAddressBookService-TargetFqdn « atl-cs-001.litwareinc.com »-détails</span><span class="sxs-lookup"><span data-stu-id="d9dbf-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="d9dbf-146">Lorsque le paramètre Verbose est inclus, le test-CsAddressBookService renvoie un compte étape par étape de chaque action qu’il a lancée lors de la vérification de la possibilité de connexion de l’utilisateur spécifié à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d9dbf-147">Par exemple, cet exemple de sortie montre que test-CsAddressBookService, au moins dans cet exemple, a pu télécharger le fichier du carnet d’adresses :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="d9dbf-148">Envoi de la requête HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-148">Sending Http GET Request.</span></span>

<span data-ttu-id="d9dbf-149">Chemin d’accès du fichier =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="d9dbf-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="d9dbf-150">Tentative de numérotation = 1</span><span class="sxs-lookup"><span data-stu-id="d9dbf-150">Attempt Number = 1</span></span>

<span data-ttu-id="d9dbf-151">Délai d’expiration (MS) = 60000</span><span class="sxs-lookup"><span data-stu-id="d9dbf-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="d9dbf-152">Téléchargement du fichier ABS réussihttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="d9dbf-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d9dbf-153">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="d9dbf-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="d9dbf-154">Voici quelques raisons courantes pour lesquelles les tests-CsAddressBookService peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="d9dbf-155">Vous avez spécifié un compte d’utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-155">You specified an invalid user account.</span></span> <span data-ttu-id="d9dbf-156">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d9dbf-157">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="d9dbf-158">Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d9dbf-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d9dbf-159">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas actuellement activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9dbf-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9dbf-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9dbf-160">See Also</span></span>


[<span data-ttu-id="d9dbf-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="d9dbf-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

