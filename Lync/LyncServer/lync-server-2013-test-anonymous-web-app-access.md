---
title: 'Lync Server 2013 : tester l’accès anonyme à l’application Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5001b7c318c9d165d9e20bbcde83e7f34b3b7cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="21235-102">Tester l’accès aux applications Web anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21235-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21235-103">_**Dernière modification de la rubrique :** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="21235-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21235-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="21235-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="21235-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="21235-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21235-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="21235-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="21235-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21235-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21235-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="21235-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="21235-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="21235-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="21235-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="21235-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="21235-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="21235-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="21235-112">Description</span><span class="sxs-lookup"><span data-stu-id="21235-112">Description</span></span>

<span data-ttu-id="21235-113">L’applet de commande test-CsWebAppAnonymous vérifie qu’un utilisateur anonyme peut participer à des conférences Lync Server à l’aide de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="21235-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="21235-114">Lorsque vous exécutez l’applet de commande, test-CsWebAppAnonymous contacte le service de ticket Web pour obtenir un ticket Web pour l’utilisateur anonyme.</span><span class="sxs-lookup"><span data-stu-id="21235-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="21235-115">Si l’applet de commande réussit à obtenir ce ticket, test-CsWebAppAnonymous contacte ensuite Lync Server et tente d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.</span><span class="sxs-lookup"><span data-stu-id="21235-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="21235-116">Notez que test-CsWebAppAnonymous vérifie uniquement les API et les connexions utilisées pour créer ces conférences.</span><span class="sxs-lookup"><span data-stu-id="21235-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="21235-117">L’applet de commande ne crée pas réellement de conférence.</span><span class="sxs-lookup"><span data-stu-id="21235-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="21235-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="21235-118">Running the test</span></span>

<span data-ttu-id="21235-119">La cmdlet Test-CsWebAppAnonymous peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21235-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="21235-120">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="21235-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="21235-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="21235-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="21235-122">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets qui contiennent le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="21235-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="21235-123">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsWebAppAnonymous :</span><span class="sxs-lookup"><span data-stu-id="21235-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="21235-124">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="21235-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="21235-125">Notez que test-CsWebAppAnonymous est déconseillé pour une utilisation sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21235-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="21235-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="21235-126">Determining success or failure</span></span>

<span data-ttu-id="21235-127">Si test-CsWebAppAnonymous peut joindre l’utilisateur anonyme à ses conférences, la cmdlet renverra le résultat du test réussite :</span><span class="sxs-lookup"><span data-stu-id="21235-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="21235-128">Nom de domaine complet cible :</span><span class="sxs-lookup"><span data-stu-id="21235-128">Target Fqdn :</span></span>

<span data-ttu-id="21235-129">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="21235-129">Result : Success</span></span>

<span data-ttu-id="21235-130">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="21235-130">Latency : 00:00:00</span></span>

<span data-ttu-id="21235-131">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="21235-131">Error Message :</span></span>

<span data-ttu-id="21235-132">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="21235-132">Diagnosis :</span></span>

<span data-ttu-id="21235-133">Si l’utilisateur anonyme ne peut pas rejoindre les conférences nécessaires, le résultat du test sera marqué comme étant un échec.</span><span class="sxs-lookup"><span data-stu-id="21235-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="21235-134">En règle générale, test-CsWebAppAnonymous signale également un message d’erreur détaillé et un diagnostic :</span><span class="sxs-lookup"><span data-stu-id="21235-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="21235-135">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="21235-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="21235-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="21235-136">Result : Failure</span></span>

<span data-ttu-id="21235-137">Latence : 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="21235-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="21235-138">Message d’erreur : aucune réponse reçue pour le service de ticket Web</span><span class="sxs-lookup"><span data-stu-id="21235-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="21235-139">Diagnostic : la demande HTTP n’est pas autorisée avec le client</span><span class="sxs-lookup"><span data-stu-id="21235-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="21235-140">modèle d’authentification « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="21235-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="21235-141">L’authentification</span><span class="sxs-lookup"><span data-stu-id="21235-141">The authentication</span></span>

<span data-ttu-id="21235-142">l’en-tête reçu du serveur était « Negotiate, NTLM ».</span><span class="sxs-lookup"><span data-stu-id="21235-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="21235-143">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="21235-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="21235-144">Les échecs de test-CsWebAppAnonymous se produisent généralement autour des erreurs d’authentification de l’utilisateur : vous devez exécuter le test à l’aide d’un compte d’utilisateur valide même si l’applet de commande vérifie la capacité d’un utilisateur anonyme à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21235-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="21235-145">Si test-CsWebAppAnonymous échoue, vérifiez que l’utilisateur spécifié a un compte d’utilisateur de Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="21235-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="21235-146">Vous pouvez récupérer les informations de compte Lync Server à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="21235-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="21235-147">Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="21235-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="21235-148">Vous devez également vérifier que le mot de passe que vous avez fourni lors de l’exécution de l’applet de commande est un mot de passe valide.</span><span class="sxs-lookup"><span data-stu-id="21235-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="21235-149">Les problèmes de configuration avec Office Web Apps Server peuvent également entraîner l’échec de test-CsWebAppAnonymous ; ce sera souvent le cas si vous recevez le diagnostic suivant :</span><span class="sxs-lookup"><span data-stu-id="21235-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="21235-150">La demande HTTP n’est pas autorisée avec le modèle d’authentification client « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="21235-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="21235-151">L’en-tête d’authentification reçu du serveur était « Negotiate, NTLM ».</span><span class="sxs-lookup"><span data-stu-id="21235-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="21235-152">Pour plus d’informations sur le diagnostic et la résolution des problèmes liés à Office Web Apps Server, voir le billet de blog [Office Web Apps server 2013-les ordinateurs sont toujours signalés comme défectueux](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="21235-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

