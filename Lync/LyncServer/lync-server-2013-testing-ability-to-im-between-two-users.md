---
title: 'Lync Server 2013: possibilité de test de la fonctionnalité de messagerie instantanée entre deux utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="f3582-102">Fonctionnalité de test de la fonctionnalité de messagerie instantanée entre deux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3582-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3582-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f3582-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3582-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="f3582-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f3582-105">Jour</span><span class="sxs-lookup"><span data-stu-id="f3582-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3582-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="f3582-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f3582-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3582-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3582-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="f3582-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f3582-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3582-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f3582-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsIM.</span><span class="sxs-lookup"><span data-stu-id="f3582-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="f3582-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f3582-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f3582-112">Description</span><span class="sxs-lookup"><span data-stu-id="f3582-112">Description</span></span>

<span data-ttu-id="f3582-113">L’applet de contrôle test-CsIM vérifie qu’un binôme d’utilisateurs de test peut échanger des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="f3582-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="f3582-114">Lorsqu’il est appelé, l’applet de connexion test-CsIM démarre en essayant de se connecter à une paire d’utilisateurs de test sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3582-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="f3582-115">En supposant que les deux ouvertures de session aboutissent, l’applet de connexion démarre une session de messagerie instantanée entre les deux utilisateurs test.</span><span class="sxs-lookup"><span data-stu-id="f3582-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="f3582-116">(L’utilisateur 1 invite l’utilisateur 2 à une session de messagerie instantanée et l’utilisateur 2 accepte l’invitation.) Après avoir vérifié que les messages peuvent être échangés entre les deux utilisateurs, testez-CsIM, puis mettez fin à la session de messagerie instantanée et enregistre les deux utilisateurs en dehors du système.</span><span class="sxs-lookup"><span data-stu-id="f3582-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="f3582-117">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f3582-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f3582-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="f3582-118">Running the Test</span></span>

<span data-ttu-id="f3582-119">L’applet de contrôle test-CsIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3582-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f3582-120">Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé.</span><span class="sxs-lookup"><span data-stu-id="f3582-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f3582-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f3582-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f3582-122">Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="f3582-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f3582-123">Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f3582-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="f3582-124">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .</span><span class="sxs-lookup"><span data-stu-id="f3582-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f3582-125">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="f3582-125">Determining Success or Failure</span></span>

<span data-ttu-id="f3582-126">Si les deux utilisateurs peuvent terminer une session de messagerie instantanée, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie:**</span><span class="sxs-lookup"><span data-stu-id="f3582-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f3582-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3582-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3582-128">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="f3582-128">Result : Success</span></span>

<span data-ttu-id="f3582-129">Latence: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="f3582-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="f3582-130">Error</span><span class="sxs-lookup"><span data-stu-id="f3582-130">Error :</span></span>

<span data-ttu-id="f3582-131">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="f3582-131">Diagnosis :</span></span>

<span data-ttu-id="f3582-132">Si les utilisateurs de test ne peuvent pas effectuer la session, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:</span><span class="sxs-lookup"><span data-stu-id="f3582-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f3582-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3582-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3582-134">Résultat: échec</span><span class="sxs-lookup"><span data-stu-id="f3582-134">Result : Failure</span></span>

<span data-ttu-id="f3582-135">Latence: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f3582-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f3582-136">Erreur: 504, délai du serveur</span><span class="sxs-lookup"><span data-stu-id="f3582-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="f3582-137">Diagnostic: codeerreur = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir</span><span class="sxs-lookup"><span data-stu-id="f3582-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="f3582-138">Code de réponse et phrase de raison.</span><span class="sxs-lookup"><span data-stu-id="f3582-138">response code and reason phrase.</span></span>

<span data-ttu-id="f3582-139">Microsoft. RTC. signalisation. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="f3582-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f3582-140">Par exemple, l’état précédent de sortie a échoué en raison de l’échec de la recherche de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="f3582-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="f3582-141">Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur affecté à cette adresse SIP a été activé pour Lync Server) en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f3582-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="f3582-142">Si test-CsIM échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:</span><span class="sxs-lookup"><span data-stu-id="f3582-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f3582-143">Lorsque le paramètre Verbose est inclus, test-CsIM renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité des deux utilisateurs de test à participer à une session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="f3582-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="f3582-144">Par exemple, voici un exemple de sortie qui se produit lorsqu’un ensemble incorrect d’informations d’identification de l’utilisateur (dans ce cas, un mot de passe incorrect) est fourni à test-CsIM:</span><span class="sxs-lookup"><span data-stu-id="f3582-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="f3582-145">Envoi de la demande d’inscription:</span><span class="sxs-lookup"><span data-stu-id="f3582-145">Sending Registration request :</span></span>

<span data-ttu-id="f3582-146">Nom de domaine complet cible = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3582-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f3582-147">Adresse SIP de l’utilisateur = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3582-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f3582-148">Port du Bureau d’enregistrement = 5061</span><span class="sxs-lookup"><span data-stu-id="f3582-148">Registrar Port = 5061</span></span>

<span data-ttu-id="f3582-149">Le type d’authentification «IWA» est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f3582-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f3582-150">Accès à l’enregistrement par SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="f3582-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3582-151">Activité «Register» achevée en «0,0601795» secondes.</span><span class="sxs-lookup"><span data-stu-id="f3582-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f3582-152">Une exception’la connexion a été refusée.</span><span class="sxs-lookup"><span data-stu-id="f3582-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="f3582-153">Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. '</span><span class="sxs-lookup"><span data-stu-id="f3582-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f3582-154">s’est produite lors du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="f3582-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f3582-155">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="f3582-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="f3582-156">Voici quelques raisons courantes pour lesquelles les tests-CsIM peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="f3582-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="f3582-157">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="f3582-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="f3582-158">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="f3582-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f3582-159">Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3582-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f3582-160">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="f3582-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f3582-161">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3582-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f3582-162">Le service de messagerie instantanée n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="f3582-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="f3582-163">Lync Server vous permet de configurer le système de sorte que la messagerie instantanée ne soit pas disponible si vous n’êtes pas en mesure d’accéder à la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="f3582-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="f3582-164">Vous pouvez vérifier qu’en exécutant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="f3582-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="f3582-165">Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="f3582-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="f3582-166">Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f3582-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="f3582-167">Le serveur d’archivage n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="f3582-167">The Archiving server might not be available.</span></span> <span data-ttu-id="f3582-168">Vous pouvez récupérer le nom de domaine complet (FQDN) de vos serveurs d’archivage à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f3582-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="f3582-169">Vous pouvez ensuite exécuter une commande ping sur le serveur approprié pour vérifier qu’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="f3582-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="f3582-170">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f3582-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

