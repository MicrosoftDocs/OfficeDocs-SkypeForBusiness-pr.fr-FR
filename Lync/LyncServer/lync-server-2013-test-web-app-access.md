---
title: 'Lync Server 2013 : test de l’accès à l’application Web'
description: 'Lync Server 2013 : test de l’accès à l’application Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560830"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="3eeb3-103">Tester l’accès à l’application Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3eeb3-103">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eeb3-104">_**Dernière modification de la rubrique :** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="3eeb3-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eeb3-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="3eeb3-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3eeb3-106">Mensuelle</span><span class="sxs-lookup"><span data-stu-id="3eeb3-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eeb3-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="3eeb3-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3eeb3-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3eeb3-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eeb3-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="3eeb3-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3eeb3-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3eeb3-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsWebApp.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="3eeb3-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3eeb3-113">Description</span><span class="sxs-lookup"><span data-stu-id="3eeb3-113">Description</span></span>

<span data-ttu-id="3eeb3-114">L’applet de commande Test-CsWebApp vérifie que les utilisateurs authentifiés peuvent participer à des conférences Lync Server à l’aide de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-114">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="3eeb3-115">Lorsque vous exécutez l’applet de commande, Test-CsWebApp contacte le service de ticket Web pour obtenir des tickets Web pour les utilisateurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-115">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="3eeb3-116">Ces tickets agissent efficacement comme des « tickets d’admission » pour la Conférence Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-116">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="3eeb3-117">Si les tickets peuvent être récupérés, et si les utilisateurs peuvent être authentifiés, Test-CsWebApp contacte ensuite Lync Server et tentent d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-117">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="3eeb3-118">Notez que Test-CsWebApp vérifie simplement les API et les connexions utilisées pour créer ces conférences.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-118">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="3eeb3-119">L’applet de commande est conçue pour vérifier que Lync Web App peut être utilisé pour créer et rejoindre des conférences.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-119">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="3eeb3-120">Toutefois, il ne crée pas réellement de conférence.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-120">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3eeb3-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="3eeb3-121">Running the test</span></span>

<span data-ttu-id="3eeb3-122">L’applet de commande Test-CsWebApp peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-122">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="3eeb3-123">Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-123">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="3eeb3-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-124">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3eeb3-125">Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="3eeb3-126">Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsWebApp :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="3eeb3-127">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="3eeb3-127">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="3eeb3-128">Notez que Test-CsWebApp était déconseillé pour une utilisation sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-128">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3eeb3-129">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="3eeb3-129">Determining success or failure</span></span>

<span data-ttu-id="3eeb3-130">Si Test-CsWebApp pouvez joindre les utilisateurs à leurs conférences, la cmdlet renverra le résultat du test réussite :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-130">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="3eeb3-131">Nom de domaine complet cible :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-131">Target Fqdn :</span></span>

<span data-ttu-id="3eeb3-132">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="3eeb3-132">Result : Success</span></span>

<span data-ttu-id="3eeb3-133">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3eeb3-133">Latency : 00:00:00</span></span>

<span data-ttu-id="3eeb3-134">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-134">Error Message :</span></span>

<span data-ttu-id="3eeb3-135">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="3eeb3-135">Diagnosis :</span></span>

<span data-ttu-id="3eeb3-136">Si les utilisateurs ne peuvent pas rejoindre les conférences nécessaires, le résultat du test sera marqué comme étant un échec.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-136">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="3eeb3-137">En règle générale, Test-CsWebApp renvoie un message d’erreur détaillé et un diagnostic :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-137">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="3eeb3-138">Nom de domaine complet cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3eeb3-138">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3eeb3-139">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="3eeb3-139">Result : Failure</span></span>

<span data-ttu-id="3eeb3-140">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3eeb3-140">Latency : 00:00:00</span></span>

<span data-ttu-id="3eeb3-141">Message d’erreur : aucune réponse reçue pour le service Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="3eeb3-141">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="3eeb3-142">Diagnostic : la demande HTTP n’est pas autorisée avec le client</span><span class="sxs-lookup"><span data-stu-id="3eeb3-142">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="3eeb3-143">modèle d’authentification « NTLM ».</span><span class="sxs-lookup"><span data-stu-id="3eeb3-143">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="3eeb3-144">L’authentification</span><span class="sxs-lookup"><span data-stu-id="3eeb3-144">The authentication</span></span>

<span data-ttu-id="3eeb3-145">l’en-tête reçu du serveur était « Negotiate, NTLM ».</span><span class="sxs-lookup"><span data-stu-id="3eeb3-145">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3eeb3-146">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="3eeb3-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="3eeb3-147">Les Test-CsWebApp les échecs impliquent généralement des erreurs d’authentification de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-147">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="3eeb3-148">Si Test-CsWebApp échoue, vérifiez d’abord que les utilisateurs spécifiés disposent de comptes d’utilisateur valides et sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-148">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="3eeb3-149">Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="3eeb3-149">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="3eeb3-150">Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide. Vous devez également vérifier que les mots de passe que vous avez fournis à la cmdlet sont valides.</span><span class="sxs-lookup"><span data-stu-id="3eeb3-150">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

