---
title: 'Lync Server 2013 : test du partage d’application'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab428e5bbfb5ffc58fa7b1d092cd7fc04b117226
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="b3f61-102">Test du partage d’application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3f61-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3f61-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b3f61-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3f61-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="b3f61-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b3f61-105">Jour</span><span class="sxs-lookup"><span data-stu-id="b3f61-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3f61-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b3f61-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b3f61-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3f61-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3f61-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b3f61-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b3f61-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b3f61-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b3f61-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="b3f61-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="b3f61-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b3f61-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b3f61-112">Description</span><span class="sxs-lookup"><span data-stu-id="b3f61-112">Description</span></span>

<span data-ttu-id="b3f61-113">L’applet de **contrôle test-CsASConference** vérifie qu’un binôme d’utilisateurs de test peut participer à une conférence en ligne incluant le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="b3f61-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="b3f61-114">Pour ce faire, l’applet de demande enregistre les deux utilisateurs avec Lync Server 2013, puis utilise l’un des comptes d’utilisateurs pour créer une nouvelle conférence incluant le partage d’applications.</span><span class="sxs-lookup"><span data-stu-id="b3f61-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="b3f61-115">L’applet de connexion vérifie alors que le second utilisateur est en mesure de rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="b3f61-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b3f61-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b3f61-116">Running the test</span></span>

<span data-ttu-id="b3f61-117">La commande décrite dans l’exemple 1 vérifie qu’une conférence de partage d’application peut être effectuée sur le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b3f61-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b3f61-118">Cette commande part du principe que vous avez configuré un couple d’utilisateurs de test pour le pool spécifié.</span><span class="sxs-lookup"><span data-stu-id="b3f61-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="b3f61-119">S’il n’existe pas de tels utilisateurs de test, la commande échoue.</span><span class="sxs-lookup"><span data-stu-id="b3f61-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b3f61-120">Dans l’exemple 2, le service de lancement de jointure peut participer à une conférence de partage d’application sur le pool atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b3f61-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b3f61-121">Notez que cette commande teste uniquement le service proprement dit ; pour exécuter la commande, vous n’avez pas besoin d’appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="b3f61-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="b3f61-122">Les commandes illustrées dans l’exemple 2 testent la capacité d’une paire d'\\utilisateurs (litwareinc\\Pilar et litwareinc kenmyer) à se connecter à Lync Server 2013, puis à effectuer une conférence de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="b3f61-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="b3f61-123">Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès.</span><span class="sxs-lookup"><span data-stu-id="b3f61-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b3f61-124">(Dans la mesure où le nom\\de connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Pilar Arès.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b3f61-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="b3f61-125">La deuxième commande effectue la même opération en renvoyant alors un objet Credential pour le compte Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3f61-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="b3f61-126">Avec les objets d’information d’identification disponibles, la troisième commande détermine si les deux utilisateurs suivants peuvent se connecter à Lync Server 2013 et diriger une conférence de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="b3f61-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="b3f61-127">Pour effectuer cette tâche, l’applet de commande **test-CsASConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); SenderSipAddress (adresse SIP pour le premier utilisateur test); SenderCredential (objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (adresse SIP de l’autre utilisateur du test); et ReceiverCredential (objet Windows PowerShell contenant les informations d’identification de l’autre utilisateur du test).</span><span class="sxs-lookup"><span data-stu-id="b3f61-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b3f61-128">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="b3f61-128">Determining success or failure</span></span>

<span data-ttu-id="b3f61-129">Si le partage d’application est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie :**</span><span class="sxs-lookup"><span data-stu-id="b3f61-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b3f61-130">Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3f61-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3f61-131">Résultat : réussite</span><span class="sxs-lookup"><span data-stu-id="b3f61-131">Result : Success</span></span>

<span data-ttu-id="b3f61-132">Latence : 00:00:01</span><span class="sxs-lookup"><span data-stu-id="b3f61-132">Latency : 00:00:01</span></span>

<span data-ttu-id="b3f61-133">Message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="b3f61-133">Error Message :</span></span>

<span data-ttu-id="b3f61-134">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="b3f61-134">Diagnosis :</span></span>

<span data-ttu-id="b3f61-135">Si les utilisateurs spécifiés ne peuvent pas partager des applications, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="b3f61-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b3f61-136">Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3f61-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3f61-137">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="b3f61-137">Result : Failure</span></span>

<span data-ttu-id="b3f61-138">Latence : 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b3f61-138">Latency : 00:00:00</span></span>

<span data-ttu-id="b3f61-139">Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée</span><span class="sxs-lookup"><span data-stu-id="b3f61-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b3f61-140">ne répond pas correctement après un certain temps, ou</span><span class="sxs-lookup"><span data-stu-id="b3f61-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b3f61-141">échec de la connexion établie, car l’hôte connecté a</span><span class="sxs-lookup"><span data-stu-id="b3f61-141">established connection failed because connected host has</span></span>

<span data-ttu-id="b3f61-142">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b3f61-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b3f61-143">Exception interne : une tentative de connexion a échoué, car le</span><span class="sxs-lookup"><span data-stu-id="b3f61-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b3f61-144">la fête connectée ne répond pas correctement après un délai de</span><span class="sxs-lookup"><span data-stu-id="b3f61-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b3f61-145">heure ou échec de la connexion en raison d’un hôte connecté</span><span class="sxs-lookup"><span data-stu-id="b3f61-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b3f61-146">échec de la réponse à 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b3f61-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b3f61-147">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="b3f61-147">Diagnosis :</span></span>

<span data-ttu-id="b3f61-148">Par exemple, la sortie précédente inclut la remarque « la partie connectée n’a pas répondu correctement », qui indique généralement un problème avec le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b3f61-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b3f61-149">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="b3f61-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="b3f61-150">Voici quelques raisons courantes pour lesquelles **les tests-CsASConference** peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="b3f61-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="b3f61-151">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="b3f61-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b3f61-152">S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="b3f61-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b3f61-153">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="b3f61-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b3f61-154">Cette commande échouera si les utilisateurs test disposent d’une stratégie de conférence qui les empêche d’utiliser le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="b3f61-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="b3f61-155">Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.</span><span class="sxs-lookup"><span data-stu-id="b3f61-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3f61-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3f61-156">See Also</span></span>


[<span data-ttu-id="b3f61-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3f61-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="b3f61-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="b3f61-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

