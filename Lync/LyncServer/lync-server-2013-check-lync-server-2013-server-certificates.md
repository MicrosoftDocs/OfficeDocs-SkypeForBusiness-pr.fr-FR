---
title: 'Lync Server 2013 : Vérifiez les certificats de serveur Lync Server 2013'
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
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="ed574-102">Vérifier les certificats de serveur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed574-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed574-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ed574-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed574-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="ed574-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ed574-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="ed574-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed574-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="ed574-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ed574-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed574-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed574-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="ed574-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ed574-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ed574-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ed574-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="ed574-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="ed574-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ed574-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ed574-112">Description</span><span class="sxs-lookup"><span data-stu-id="ed574-112">Description</span></span>

<span data-ttu-id="ed574-113">La cmdlet Get-CsCertificate vous permet d’extraire des informations sur chacun de vos certificats Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed574-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="ed574-114">Cela est particulièrement important, car les certificats ont une date d’expiration intégrée.</span><span class="sxs-lookup"><span data-stu-id="ed574-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="ed574-115">Par exemple, les certificats émis en privé expirent généralement après 12 mois.</span><span class="sxs-lookup"><span data-stu-id="ed574-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="ed574-116">Si l’un de vos certificats Lync Server arrive à expiration, vous perdrez les fonctionnalités associées jusqu’à ce que ce certificat soit renouvelé ou remplacé.</span><span class="sxs-lookup"><span data-stu-id="ed574-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ed574-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="ed574-117">Running the test</span></span>

<span data-ttu-id="ed574-118">Pour renvoyer des informations sur chacun de vos certificats Lync Server, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ed574-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="ed574-119">Ou, vous pouvez filtrer les informations de certificat de retour en fonction de la date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ed574-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="ed574-120">Par exemple, cette commande limite les données renvoyées aux certificats qui expirent (qui ne peuvent pas être utilisés après) le 1er juin 2014 :</span><span class="sxs-lookup"><span data-stu-id="ed574-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="ed574-121">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="ed574-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="ed574-122">Notez que, bien que la cmdlet Test-CsCertificateConfiguration existe, elle n’est pas très utile pour les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="ed574-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="ed574-123">(À la place, cette applet de commande est principalement utilisée par l’Assistant certificat.) Bien que l’applet de commande fonctionne, les informations qu’elle renvoie sont de valeur minimale, comme illustré dans l’exemple de sortie suivant :</span><span class="sxs-lookup"><span data-stu-id="ed574-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="ed574-124">Utilisation de l’empreinte numérique</span><span class="sxs-lookup"><span data-stu-id="ed574-124">Thumbprint Use</span></span>

<span data-ttu-id="ed574-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="ed574-125">\---------- ---</span></span>

<span data-ttu-id="ed574-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 par défaut</span><span class="sxs-lookup"><span data-stu-id="ed574-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="ed574-127">Révision de la sortie</span><span class="sxs-lookup"><span data-stu-id="ed574-127">Reviewing the output</span></span>

<span data-ttu-id="ed574-128">L’applet de commande Get-CsCertificate renvoie des informations semblables aux suivantes pour chacun de vos certificats Lync Server :</span><span class="sxs-lookup"><span data-stu-id="ed574-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="ed574-129">Émetteur : CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="ed574-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="ed574-130">NotAfter : 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="ed574-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="ed574-131">NotBefore : 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="ed574-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="ed574-132">SerialNumber : 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="ed574-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="ed574-133">Objet : CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="ed574-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="ed574-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="ed574-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="ed574-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="ed574-136">Empreinte numérique : A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="ed574-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="ed574-137">Utiliser : par défaut</span><span class="sxs-lookup"><span data-stu-id="ed574-137">Use : Default</span></span>

<span data-ttu-id="ed574-138">En règle générale, les principaux problèmes liés aux certificats Lync Server concernent des dates et des heures, par exemple lorsque des certificats prennent effet (NotBefore) ou lorsqu’ils arrivent à expiration (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="ed574-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="ed574-139">Étant donné que ces dates et heures sont tellement importantes, vous souhaiterez peut-être limiter les données renvoyées à des informations telles que l’utilisation du certificat, le numéro de série du certificat et la date d’expiration du certificat ; vous pouvez ensuite passer rapidement en revue tous les certificats et leur date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ed574-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="ed574-140">Pour renvoyer uniquement ces informations, utilisez la commande avec les options indiquées :</span><span class="sxs-lookup"><span data-stu-id="ed574-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="ed574-141">Cette commande renvoie des données semblables aux suivantes, dont les certificats sont triés dans l’ordre de leur date d’expiration :</span><span class="sxs-lookup"><span data-stu-id="ed574-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="ed574-142">Utiliser le SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="ed574-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="ed574-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="ed574-143">\--- ------------ --------</span></span>

<span data-ttu-id="ed574-144">Valeur par défaut 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="ed574-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="ed574-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="ed574-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="ed574-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="ed574-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="ed574-147">Si vous avez des problèmes de certificat, vous pouvez consulter la AlternativeNames configurée pour un certificat.</span><span class="sxs-lookup"><span data-stu-id="ed574-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="ed574-148">À première vue, il semblerait qu’il s’agit d’un problème.</span><span class="sxs-lookup"><span data-stu-id="ed574-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="ed574-149">Par défaut, en fonction de la taille de votre fenêtre de console, Get-CsCertificate peut ne pas être en mesure d’afficher tous les noms :</span><span class="sxs-lookup"><span data-stu-id="ed574-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="ed574-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="ed574-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="ed574-151">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="ed574-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="ed574-152">Pour afficher tous les autres noms attribués à un certificat, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ed574-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="ed574-153">Cela doit vous indiquer tous les autres noms du certificat :</span><span class="sxs-lookup"><span data-stu-id="ed574-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="ed574-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-154">sip.fabrikam.com</span></span>

<span data-ttu-id="ed574-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="ed574-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-156">meet.fabrikam.com</span></span>

<span data-ttu-id="ed574-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-157">admin.fabrikam.com</span></span>

<span data-ttu-id="ed574-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="ed574-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ed574-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed574-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed574-160">See Also</span></span>


[<span data-ttu-id="ed574-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="ed574-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

