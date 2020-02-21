---
title: 'Lync Server 2013 : test de la connexion Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="fd2e4-102">Test de la connexion de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd2e4-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd2e4-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fd2e4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd2e4-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="fd2e4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fd2e4-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="fd2e4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd2e4-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="fd2e4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fd2e4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd2e4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd2e4-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="fd2e4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fd2e4-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fd2e4-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="fd2e4-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fd2e4-112">Description</span><span class="sxs-lookup"><span data-stu-id="fd2e4-112">Description</span></span>

<span data-ttu-id="fd2e4-113">L’applet de commande test-CsPhoneBootstrap permet aux administrateurs de vérifier qu’un utilisateur donné (en utilisant le numéro de téléphone et le code confidentiel qui lui ont été attribué) peut se connecter au système à partir d’un appareil compatible avec Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="fd2e4-114">(Aucun appareil n’est réellement nécessaire pour exécuter le test.)</span><span class="sxs-lookup"><span data-stu-id="fd2e4-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="fd2e4-115">Pour que l’applet de commande Test-CsPhoneBootstrap puisse effectuer cette vérification, le pool de serveurs d’inscriptions qui héberge le compte d’utilisateur testé doit pouvoir être détecté avec DHCP.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="fd2e4-116">Pour déterminer si un serveur d’inscriptions est détectable de cette manière, utilisez l’applet de commande Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fd2e4-117">Si cette propriété est définie sur false, vous devez utiliser SET-CsRegistrarConfiguration pour définir la valeur de la propriété sur true et faire en sorte que le serveur d’inscriptions soit détectable à l’aide du protocole DHCP.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="fd2e4-118">Cela peut également être réalisé à l’aide du serveur DHCP d’entreprise et de la configuration des options spécifiques à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fd2e4-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="fd2e4-119">Running the test</span></span>

<span data-ttu-id="fd2e4-120">Pour exécuter la cmdlet Test-CsPhoneBootstrap, vous devez au minimum fournir le numéro de téléphone et le code confidentiel (PIN) du client pour un utilisateur Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="fd2e4-121">Par exemple, cette commande teste la capacité d’ouverture de session de l’utilisateur qui a le numéro de téléphone 12065551219 et le code confidentiel 0712 :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="fd2e4-122">Pour une vérification plus complète, vous pouvez également inclure l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="fd2e4-123">Dans ce cas, le numéro de téléphone, le code confidentiel client et l’adresse SIP doivent tous être valides pour que le test réussisse :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="fd2e4-124">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="fd2e4-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fd2e4-125">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="fd2e4-125">Determining success or failure</span></span>

<span data-ttu-id="fd2e4-126">Si l’utilisateur spécifié a pu se connecter à Lync Server, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="fd2e4-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fd2e4-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="fd2e4-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="fd2e4-128">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="fd2e4-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="fd2e4-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd2e4-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd2e4-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="fd2e4-130">Result : Success</span></span>

<span data-ttu-id="fd2e4-131">Latence : 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="fd2e4-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="fd2e4-132">«</span><span class="sxs-lookup"><span data-stu-id="fd2e4-132">Error :</span></span>

<span data-ttu-id="fd2e4-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="fd2e4-133">Diagnosis :</span></span>

<span data-ttu-id="fd2e4-134">Si l’utilisateur spécifié n’a pas pu établir une connexion, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fd2e4-135">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd2e4-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd2e4-136">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="fd2e4-136">Result : Failure</span></span>

<span data-ttu-id="fd2e4-137">Latence : 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="fd2e4-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="fd2e4-138">Erreur : erreur-aucune réponse reçue pour le service de ticket Web.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="fd2e4-139">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="fd2e4-139">Diagnosis :</span></span>

<span data-ttu-id="fd2e4-140">La sortie précédente indique que le test a échoué, car le service de ticket Web n’a pas répondu.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="fd2e4-141">Cela peut être dû à un problème avec le service lui-même ou à une adresse SIP, un numéro de téléphone ou un code confidentiel client transmis à test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="fd2e4-142">Vous pouvez vérifier l’adresse SIP et le numéro de téléphone de l’utilisateur à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="fd2e4-143">Et vous pouvez vérifier que l’utilisateur dispose d’un code confidentiel valide à l’aide d’une commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="fd2e4-144">Si test-CsPhoneBootstrap échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="fd2e4-145">Lorsque le paramètre Verbose est inclus, test-CsPhoneBootstrap renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="fd2e4-146">Par exemple, voici une partie de la sortie pour une ouverture de session infructueuse, une session dans laquelle un code confidentiel incorrect a été inclus :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="fd2e4-147">Utilisation de l’authentification par\\code confidentiel avec le code poste tél. 12065551219:0712</span><span class="sxs-lookup"><span data-stu-id="fd2e4-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="fd2e4-148">Impossible d’obtenir le ticket Web</span><span class="sxs-lookup"><span data-stu-id="fd2e4-148">Could not get web ticket</span></span>

<span data-ttu-id="fd2e4-149">OPTION</span><span class="sxs-lookup"><span data-stu-id="fd2e4-149">CHECK :</span></span>

<span data-ttu-id="fd2e4-150">\-L’URL de service Web est valide et les services Web sont fonctionnels</span><span class="sxs-lookup"><span data-stu-id="fd2e4-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="fd2e4-151">\-Si vous utilisez\\le code confidentiel PhoneNo pour l’authentification, assurez-vous qu’ils correspondent à l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="fd2e4-152">\-Si vous utilisez\\l’authentification NTLM Kerberos, vérifiez que vous avez fourni des informations d’identification valides.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fd2e4-153">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="fd2e4-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="fd2e4-154">Voici quelques-unes des causes courantes de l’échec de test-CsPhoneBootstrap :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="fd2e4-155">Vous avez peut-être spécifié une adresse SIP qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="fd2e4-156">Vous pouvez vérifier qu’une adresse SIP est correcte à l’aide d’une commande telle que celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fd2e4-157">Vous avez peut-être spécifié un code confidentiel qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="fd2e4-158">Bien que vous ne puissiez pas récupérer le numéro de code confidentiel de l’utilisateur, vous pouvez vérifier que l’utilisateur a au moins un numéro de code confidentiel à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fd2e4-159">Vous avez peut-être spécifié un numéro de téléphone qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="fd2e4-160">Vous pouvez vérifier le téléphone d’un utilisateur à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="fd2e4-161">Le pool de serveurs d’inscriptions n’est pas activé pour DHCP.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="fd2e4-162">Pour déterminer si votre pool de serveurs d’inscriptions est activé pour DHCP, exécutez la cmdlet Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="fd2e4-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fd2e4-163">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fd2e4-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

