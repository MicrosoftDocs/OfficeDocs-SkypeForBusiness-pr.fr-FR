---
title: 'Lync Server 2013 : vérifier les certificats du serveur Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="ff3c0-102">Vérifier les certificats du serveur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff3c0-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff3c0-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ff3c0-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff3c0-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="ff3c0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ff3c0-105">Mois</span><span class="sxs-lookup"><span data-stu-id="ff3c0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff3c0-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="ff3c0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ff3c0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff3c0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff3c0-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="ff3c0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ff3c0-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ff3c0-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="ff3c0-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ff3c0-112">Description</span><span class="sxs-lookup"><span data-stu-id="ff3c0-112">Description</span></span>

<span data-ttu-id="ff3c0-113">L’applet de passe Get-CsCertificate vous permet de récupérer des informations sur chacun de vos certificats Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="ff3c0-114">C’est particulièrement important car les certificats disposent d’une date d’expiration prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="ff3c0-115">Par exemple, les certificats émis en privé arrivent généralement après 12 mois.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="ff3c0-116">Si l’un de vos certificats serveur Lync expire alors, vous perdrez la fonctionnalité qui vous est fournie tant que ce certificat n’est pas renouvelé ou remplacé.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ff3c0-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="ff3c0-117">Running the test</span></span>

<span data-ttu-id="ff3c0-118">Pour renvoyer des informations sur chacun de vos certificats de serveur Lync, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="ff3c0-119">Vous pouvez ou filtrer les informations de certificat de renvoi en fonction de la date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="ff3c0-120">Par exemple, la commande suivante permet de limiter les données renvoyées aux certificats qui expirent (ne peut pas être utilisé après le 1er juin), 2014 :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="ff3c0-121">Pour plus d’informations, consultez la documentation d’aide relative à l’applet de passe Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="ff3c0-122">Notez que bien que l’applet de contrôle CsCertificateConfiguration de test existe, il n’est pas très utile aux administrateurs.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="ff3c0-123">(Au lieu de cela, cette applet de certification est essentiellement utilisée par l’Assistant certificat.) Même si l’applet de commande fonctionne, les informations qu’elle renvoie sont de valeur minimale, comme indiqué dans l’exemple de sortie suivant :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="ff3c0-124">Utilisation de l’empreinte digitale</span><span class="sxs-lookup"><span data-stu-id="ff3c0-124">Thumbprint Use</span></span>

<span data-ttu-id="ff3c0-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="ff3c0-125">\---------- ---</span></span>

<span data-ttu-id="ff3c0-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 par défaut</span><span class="sxs-lookup"><span data-stu-id="ff3c0-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="ff3c0-127">Examen de la sortie</span><span class="sxs-lookup"><span data-stu-id="ff3c0-127">Reviewing the output</span></span>

<span data-ttu-id="ff3c0-128">L’applet de commande Get-CsCertificate renvoie des informations similaires à ce qui suit pour chacun de vos certificats Lync Server :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="ff3c0-129">Émetteur : CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="ff3c0-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="ff3c0-130">NotAfter : 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="ff3c0-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="ff3c0-131">NotBefore : 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="ff3c0-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="ff3c0-132">SerialNumber : 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="ff3c0-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="ff3c0-133">Subject : CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="ff3c0-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="ff3c0-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="ff3c0-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="ff3c0-136">Empreinte : A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="ff3c0-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="ff3c0-137">Utiliser : par défaut</span><span class="sxs-lookup"><span data-stu-id="ff3c0-137">Use : Default</span></span>

<span data-ttu-id="ff3c0-138">En règle générale, les principaux problèmes liés aux certificats de serveur Lync concernent les dates et les heures, par exemple lorsque les certificats prennent effet (NotBefore) ou qu’ils arrivent à expiration (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="ff3c0-139">Étant donné que ces dates et heures sont si importantes, il est possible que vous souhaitiez limiter les données renvoyées à des informations telles que l’utilisation du certificat, le numéro de série du certificat et la date d’expiration du certificat ; vous pouvez ensuite consulter rapidement tous les certificats et leur date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="ff3c0-140">Pour renvoyer uniquement ces informations, utilisez la commande conjointement avec les options proposées :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="ff3c0-141">Cette commande renvoie des données similaires à ce qui suit, avec les certificats triés dans l’ordre de leur date d’expiration :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="ff3c0-142">Utiliser SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="ff3c0-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="ff3c0-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="ff3c0-143">\--- ------------ --------</span></span>

<span data-ttu-id="ff3c0-144">Par défaut 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="ff3c0-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="ff3c0-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="ff3c0-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="ff3c0-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="ff3c0-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="ff3c0-147">Si vous rencontrez des problèmes de certificat, vous pouvez consulter le AlternativeNames configuré pour un certificat.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="ff3c0-148">Tout d’abord, il semble y avoir un problème.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="ff3c0-149">Par défaut, et en fonction de la taille de la fenêtre de la console, Get-CsCertificate peut ne pas être en mesure d’afficher tous les noms :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="ff3c0-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="ff3c0-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="ff3c0-151">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="ff3c0-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="ff3c0-152">Pour afficher tous les noms de remplacement attribués à un certificat, utilisez une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="ff3c0-153">Cela doit afficher tous les noms secondaires sur le certificat :</span><span class="sxs-lookup"><span data-stu-id="ff3c0-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="ff3c0-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-154">sip.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-156">meet.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-157">admin.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="ff3c0-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ff3c0-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff3c0-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff3c0-160">See Also</span></span>


[<span data-ttu-id="ff3c0-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="ff3c0-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

