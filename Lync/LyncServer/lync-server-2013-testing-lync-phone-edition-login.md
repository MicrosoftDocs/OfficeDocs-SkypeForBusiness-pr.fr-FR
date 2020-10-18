---
title: 'Lync Server 2013 : test de la connexion Lync Phone Edition'
description: 'Lync Server 2013 : test de la connexion Lync Phone Edition.'
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
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575240"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="e8ad7-103">Test de la connexion de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ad7-103">Testing Lync Phone Edition login in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ad7-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e8ad7-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8ad7-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="e8ad7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e8ad7-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="e8ad7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8ad7-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="e8ad7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e8ad7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8ad7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8ad7-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="e8ad7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e8ad7-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e8ad7-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="e8ad7-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e8ad7-113">Description</span><span class="sxs-lookup"><span data-stu-id="e8ad7-113">Description</span></span>

<span data-ttu-id="e8ad7-114">L’applet de commande Test-CsPhoneBootstrap permet aux administrateurs de vérifier qu’un utilisateur donné (en utilisant le numéro de téléphone et le code confidentiel qui lui sont attribués) peut se connecter au système à partir d’un appareil compatible avec Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-114">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="e8ad7-115">(Aucun appareil n’est réellement nécessaire pour exécuter le test.)</span><span class="sxs-lookup"><span data-stu-id="e8ad7-115">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="e8ad7-116">Pour que l’applet de commande Test-CsPhoneBootstrap puisse effectuer cette vérification, le pool de serveurs d’inscriptions qui héberge le compte d’utilisateur testé doit pouvoir être détecté avec DHCP.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-116">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="e8ad7-117">Pour déterminer si un serveur d’inscriptions est détectable de cette manière, utilisez l’applet de commande Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-117">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="e8ad7-118">Si cette propriété est définie sur false, vous devez utiliser Set-CsRegistrarConfiguration pour définir la valeur de la propriété sur true et faire en sorte que le Bureau d’enregistrement soit détectable à l’aide du protocole DHCP.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-118">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="e8ad7-119">Cela peut également être réalisé à l’aide du serveur DHCP d’entreprise et de la configuration des options spécifiques à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-119">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e8ad7-120">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="e8ad7-120">Running the test</span></span>

<span data-ttu-id="e8ad7-121">Pour exécuter l’applet de commande Test-CsPhoneBootstrap, vous devez au minimum fournir le numéro de téléphone et le code confidentiel (PIN) du client pour un utilisateur Lync Server valide.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-121">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="e8ad7-122">Par exemple, cette commande teste la capacité d’ouverture de session de l’utilisateur qui a le numéro de téléphone 12065551219 et le code confidentiel 0712 :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-122">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="e8ad7-123">Pour une vérification plus complète, vous pouvez également inclure l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-123">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="e8ad7-124">Dans ce cas, le numéro de téléphone, le code confidentiel client et l’adresse SIP doivent tous être valides pour que le test réussisse :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-124">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="e8ad7-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="e8ad7-125">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e8ad7-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="e8ad7-126">Determining success or failure</span></span>

<span data-ttu-id="e8ad7-127">Si l’utilisateur spécifié a pu se connecter à Lync Server, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**</span><span class="sxs-lookup"><span data-stu-id="e8ad7-127">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e8ad7-128">TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="e8ad7-128">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="e8ad7-129">CertProvisioningService. svc</span><span class="sxs-lookup"><span data-stu-id="e8ad7-129">CertProvisioningService.svc</span></span>

<span data-ttu-id="e8ad7-130">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8ad7-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8ad7-131">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="e8ad7-131">Result : Success</span></span>

<span data-ttu-id="e8ad7-132">Latence : 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="e8ad7-132">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="e8ad7-133">«</span><span class="sxs-lookup"><span data-stu-id="e8ad7-133">Error :</span></span>

<span data-ttu-id="e8ad7-134">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="e8ad7-134">Diagnosis :</span></span>

<span data-ttu-id="e8ad7-135">Si l’utilisateur spécifié n’a pas pu établir une connexion, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-135">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e8ad7-136">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e8ad7-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e8ad7-137">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="e8ad7-137">Result : Failure</span></span>

<span data-ttu-id="e8ad7-138">Latence : 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="e8ad7-138">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="e8ad7-139">Erreur : erreur-aucune réponse reçue pour le service de Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-139">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="e8ad7-140">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="e8ad7-140">Diagnosis :</span></span>

<span data-ttu-id="e8ad7-141">La sortie précédente indique que le test a échoué, car le service de ticket Web n’a pas répondu.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-141">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="e8ad7-142">Cela peut être dû à un problème avec le service lui-même ou à une adresse SIP, un numéro de téléphone ou un code confidentiel client transmis à test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-142">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="e8ad7-143">Vous pouvez vérifier l’adresse SIP et le numéro de téléphone de l’utilisateur à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-143">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="e8ad7-144">Et vous pouvez vérifier que l’utilisateur dispose d’un code confidentiel valide à l’aide d’une commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-144">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="e8ad7-145">Si Test-CsPhoneBootstrap échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-145">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="e8ad7-146">Lorsque le paramètre Verbose est inclus, Test-CsPhoneBootstrap renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-146">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e8ad7-147">Par exemple, voici une partie de la sortie pour une ouverture de session infructueuse, une session dans laquelle un code confidentiel incorrect a été inclus :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-147">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="e8ad7-148">Utilisation de l’authentification par code confidentiel avec le \\ code poste Tél. 12065551219:0712</span><span class="sxs-lookup"><span data-stu-id="e8ad7-148">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="e8ad7-149">Impossible d’obtenir le ticket Web</span><span class="sxs-lookup"><span data-stu-id="e8ad7-149">Could not get web ticket</span></span>

<span data-ttu-id="e8ad7-150">OPTION</span><span class="sxs-lookup"><span data-stu-id="e8ad7-150">CHECK :</span></span>

<span data-ttu-id="e8ad7-151">\- L’URL de service Web est valide et les services Web sont fonctionnels</span><span class="sxs-lookup"><span data-stu-id="e8ad7-151">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="e8ad7-152">\- Si vous utilisez \\ le code confidentiel PhoneNo pour l’authentification, assurez-vous qu’ils correspondent à l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-152">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="e8ad7-153">\- Si vous utilisez l' \\ authentification NTLM Kerberos, vérifiez que vous avez fourni des informations d’identification valides.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-153">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e8ad7-154">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="e8ad7-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="e8ad7-155">Voici quelques raisons courantes pour lesquelles Test-CsPhoneBootstrap peut échouer :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-155">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="e8ad7-156">Vous avez peut-être spécifié une adresse SIP qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-156">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="e8ad7-157">Vous pouvez vérifier qu’une adresse SIP est correcte à l’aide d’une commande telle que celle-ci :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-157">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e8ad7-158">Vous avez peut-être spécifié un code confidentiel qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-158">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="e8ad7-159">Bien que vous ne puissiez pas récupérer le numéro de code confidentiel de l’utilisateur, vous pouvez vérifier que l’utilisateur a au moins un numéro de code confidentiel à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-159">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e8ad7-160">Vous avez peut-être spécifié un numéro de téléphone qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-160">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="e8ad7-161">Vous pouvez vérifier le téléphone d’un utilisateur à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-161">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="e8ad7-162">Le pool de serveurs d’inscriptions n’est pas activé pour DHCP.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-162">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="e8ad7-163">Pour déterminer si votre pool de serveurs d’inscriptions est activé pour DHCP, exécutez l’applet de commande Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="e8ad7-163">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="e8ad7-164">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e8ad7-164">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

