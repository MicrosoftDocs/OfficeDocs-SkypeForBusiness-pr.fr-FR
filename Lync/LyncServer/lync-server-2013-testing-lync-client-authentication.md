---
title: 'Lync Server 2013 : test de l’authentification de client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 490068a9c9eec3e582471d9ff228b9bbccad43bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="11ab5-102">Test de l’authentification client Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ab5-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ab5-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="11ab5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11ab5-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="11ab5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="11ab5-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="11ab5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ab5-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="11ab5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="11ab5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ab5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ab5-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="11ab5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="11ab5-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="11ab5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="11ab5-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="11ab5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="11ab5-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="11ab5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="11ab5-112">Description</span><span class="sxs-lookup"><span data-stu-id="11ab5-112">Description</span></span>

<span data-ttu-id="11ab5-113">L’applet de commande test-CsClientAuth vous permet de déterminer si un utilisateur peut se connecter au serveur Lync à l’aide d’un certificat client, mais vous pouvez exécuter la cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="11ab5-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="11ab5-114">Une fois appelée, l’applet de commande Test-CsClientAuth contacte le service d’approvisionnement de certificats et télécharge un exemplaire des certificats clients pour l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="11ab5-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="11ab5-115">S’il est possible de trouver un certificat client et de le télécharger, la fonction test-CsClientAuth essaiera de se connecter à l’aide de ce certificat.</span><span class="sxs-lookup"><span data-stu-id="11ab5-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="11ab5-116">Si l’ouverture de session réussit, Test-CsClientAuth ferme la session et indique que le test a réussi.</span><span class="sxs-lookup"><span data-stu-id="11ab5-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="11ab5-117">Si aucun certificat n’est disponible ou s’il n’est pas possible de télécharger un certificat, ou si l’applet de commande Test-CsClientAuth ne peut pas ouvrir une session avec un certificat téléchargé, l’applet de commande indique que le test a échoué.</span><span class="sxs-lookup"><span data-stu-id="11ab5-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="11ab5-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="11ab5-118">Running the test</span></span>

<span data-ttu-id="11ab5-119">La cmdlet Test-CsClientAuth est exécutée à l’aide du compte de n’importe quel utilisateur qui est activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11ab5-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="11ab5-120">Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="11ab5-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="11ab5-121">Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque le système appelle test-CsClientAuth :</span><span class="sxs-lookup"><span data-stu-id="11ab5-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="11ab5-122">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="11ab5-122">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="11ab5-123">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="11ab5-123">Determining success or failure</span></span>

<span data-ttu-id="11ab5-124">Si l’utilisateur spécifié peut se connecter à Lync Server à l’aide d’un certificat client, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**</span><span class="sxs-lookup"><span data-stu-id="11ab5-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="11ab5-125">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="11ab5-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="11ab5-126">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="11ab5-126">Result : Success</span></span>

<span data-ttu-id="11ab5-127">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="11ab5-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="11ab5-128">«</span><span class="sxs-lookup"><span data-stu-id="11ab5-128">Error :</span></span>

<span data-ttu-id="11ab5-129">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="11ab5-129">Diagnosis :</span></span>

<span data-ttu-id="11ab5-130">Si l’utilisateur spécifié ne peut pas se connecter, le résultat est affiché sous la forme échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :</span><span class="sxs-lookup"><span data-stu-id="11ab5-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="11ab5-131">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="11ab5-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="11ab5-132">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="11ab5-132">Result : Failure</span></span>

<span data-ttu-id="11ab5-133">Latence : 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="11ab5-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="11ab5-134">Erreur : impossible de télécharger un certificat CS pour l’utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="11ab5-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="11ab5-135">Vérifier si</span><span class="sxs-lookup"><span data-stu-id="11ab5-135">Check if</span></span>

<span data-ttu-id="11ab5-136">l’URI fourni et les informations d’identification sont corrects.</span><span class="sxs-lookup"><span data-stu-id="11ab5-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="11ab5-137">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="11ab5-137">Diagnosis :</span></span>

<span data-ttu-id="11ab5-138">Par exemple, la sortie précédente indique que le test a échoué, car il est impossible de trouver un certificat client valide pour l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="11ab5-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="11ab5-139">Vous pouvez renvoyer la liste des certificats clients délivrés à un utilisateur en exécutant une commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="11ab5-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="11ab5-140">Si test-CsClientAuth échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="11ab5-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="11ab5-141">Lorsque le paramètre Verbose est inclus, test-CsClientAuth renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11ab5-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="11ab5-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="11ab5-142">For example:</span></span>

<span data-ttu-id="11ab5-143">Tentative de téléchargement d’un certificat CS pour l’utilisateur : kenmyer@litwareinc.com Endpoint : STEpid</span><span class="sxs-lookup"><span data-stu-id="11ab5-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="11ab5-144">URL du service Web :https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="11ab5-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="11ab5-145">Impossible de télécharger un certificat CS à partir du service Web.</span><span class="sxs-lookup"><span data-stu-id="11ab5-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="11ab5-146">OPTION</span><span class="sxs-lookup"><span data-stu-id="11ab5-146">CHECK:</span></span>

<span data-ttu-id="11ab5-147">\-L’URL de service Web est valide et les services Web sont fonctionnels</span><span class="sxs-lookup"><span data-stu-id="11ab5-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="11ab5-148">\-Si vous utilisez\\\\le code confidentiel PhoneNo pour l’authentification, assurez-vous qu’ils correspondent à l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11ab5-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="11ab5-149">\-Si vous utilisez\\l’authentification NTLM Kerberos, vérifiez que vous avez fourni des informations d’identification valides.</span><span class="sxs-lookup"><span data-stu-id="11ab5-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="11ab5-150">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="11ab5-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="11ab5-151">Voici quelques-unes des causes courantes de l’échec de test-CsClientAuth :</span><span class="sxs-lookup"><span data-stu-id="11ab5-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="11ab5-152">Vous avez spécifié un compte d’utilisateur qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="11ab5-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="11ab5-153">Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="11ab5-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="11ab5-154">Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11ab5-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="11ab5-155">Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="11ab5-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="11ab5-156">Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11ab5-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="11ab5-157">Il est possible que l’utilisateur test ne dispose pas d’un certificat client valide.</span><span class="sxs-lookup"><span data-stu-id="11ab5-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="11ab5-158">Vous pouvez renvoyer des informations sur les certificats clients affectés à un utilisateur à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="11ab5-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

