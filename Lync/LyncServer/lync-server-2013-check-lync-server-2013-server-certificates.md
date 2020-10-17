---
title: 'Lync Server 2013 : Vérifiez les certificats de serveur Lync Server 2013'
description: 'Lync Server 2013 : Vérifiez les certificats de serveur Lync Server 2013.'
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
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543590"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="b0233-103">Vérifier les certificats de serveur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0233-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0233-104">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b0233-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0233-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="b0233-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b0233-106">Mensuelle</span><span class="sxs-lookup"><span data-stu-id="b0233-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0233-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b0233-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b0233-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0233-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0233-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b0233-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b0233-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b0233-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b0233-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="b0233-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="b0233-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b0233-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b0233-113">Description</span><span class="sxs-lookup"><span data-stu-id="b0233-113">Description</span></span>

<span data-ttu-id="b0233-114">L’applet de commande Get-CsCertificate vous permet de récupérer des informations sur chacun de vos certificats Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0233-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="b0233-115">Cela est particulièrement important, car les certificats ont une date d’expiration intégrée.</span><span class="sxs-lookup"><span data-stu-id="b0233-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="b0233-116">Par exemple, les certificats émis en privé expirent généralement après 12 mois.</span><span class="sxs-lookup"><span data-stu-id="b0233-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="b0233-117">Si l’un de vos certificats Lync Server arrive à expiration, vous perdrez les fonctionnalités associées jusqu’à ce que ce certificat soit renouvelé ou remplacé.</span><span class="sxs-lookup"><span data-stu-id="b0233-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b0233-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b0233-118">Running the test</span></span>

<span data-ttu-id="b0233-119">Pour renvoyer des informations sur chacun de vos certificats Lync Server, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b0233-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="b0233-120">Ou, vous pouvez filtrer les informations de certificat de retour en fonction de la date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="b0233-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="b0233-121">Par exemple, cette commande limite les données renvoyées aux certificats qui expirent (qui ne peuvent pas être utilisés après) le 1er juin 2014 :</span><span class="sxs-lookup"><span data-stu-id="b0233-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="b0233-122">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="b0233-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="b0233-123">Notez que, bien que la cmdlet Test-CsCertificateConfiguration existe, elle n’est pas très utile pour les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="b0233-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="b0233-124">(À la place, cette applet de commande est principalement utilisée par l’Assistant certificat.) Bien que l’applet de commande fonctionne, les informations qu’elle renvoie sont de valeur minimale, comme illustré dans l’exemple de sortie suivant :</span><span class="sxs-lookup"><span data-stu-id="b0233-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="b0233-125">Utilisation de l’empreinte numérique</span><span class="sxs-lookup"><span data-stu-id="b0233-125">Thumbprint Use</span></span>

<span data-ttu-id="b0233-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="b0233-126">\---------- ---</span></span>

<span data-ttu-id="b0233-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 par défaut</span><span class="sxs-lookup"><span data-stu-id="b0233-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="b0233-128">Révision de la sortie</span><span class="sxs-lookup"><span data-stu-id="b0233-128">Reviewing the output</span></span>

<span data-ttu-id="b0233-129">L’applet de commande Get-CsCertificate renvoie des informations semblables aux suivantes pour chacun de vos certificats Lync Server :</span><span class="sxs-lookup"><span data-stu-id="b0233-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="b0233-130">Émetteur : CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="b0233-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="b0233-131">NotAfter : 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="b0233-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="b0233-132">NotBefore : 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="b0233-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="b0233-133">SerialNumber : 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="b0233-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="b0233-134">Objet : CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b0233-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="b0233-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="b0233-136">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="b0233-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="b0233-137">Empreinte numérique : A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="b0233-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="b0233-138">Utiliser : par défaut</span><span class="sxs-lookup"><span data-stu-id="b0233-138">Use : Default</span></span>

<span data-ttu-id="b0233-139">En règle générale, les principaux problèmes liés aux certificats Lync Server concernent des dates et des heures, par exemple lorsque des certificats prennent effet (NotBefore) ou lorsqu’ils arrivent à expiration (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="b0233-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="b0233-140">Étant donné que ces dates et heures sont tellement importantes, vous souhaiterez peut-être limiter les données renvoyées à des informations telles que l’utilisation du certificat, le numéro de série du certificat et la date d’expiration du certificat ; vous pouvez ensuite passer rapidement en revue tous les certificats et leur date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="b0233-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="b0233-141">Pour renvoyer uniquement ces informations, utilisez la commande avec les options indiquées :</span><span class="sxs-lookup"><span data-stu-id="b0233-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="b0233-142">Cette commande renvoie des données semblables aux suivantes, dont les certificats sont triés dans l’ordre de leur date d’expiration :</span><span class="sxs-lookup"><span data-stu-id="b0233-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="b0233-143">Utiliser le SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="b0233-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="b0233-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="b0233-144">\--- ------------ --------</span></span>

<span data-ttu-id="b0233-145">Valeur par défaut 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="b0233-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="b0233-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="b0233-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="b0233-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="b0233-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="b0233-148">Si vous avez des problèmes de certificat, vous pouvez consulter la AlternativeNames configurée pour un certificat.</span><span class="sxs-lookup"><span data-stu-id="b0233-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="b0233-149">À première vue, il semblerait qu’il s’agit d’un problème.</span><span class="sxs-lookup"><span data-stu-id="b0233-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="b0233-150">Par défaut, en fonction de la taille de la fenêtre de votre console, Get-CsCertificate risque de ne pas pouvoir afficher tous les noms :</span><span class="sxs-lookup"><span data-stu-id="b0233-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="b0233-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="b0233-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="b0233-152">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="b0233-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="b0233-153">Pour afficher tous les autres noms attribués à un certificat, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b0233-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="b0233-154">Cela doit vous indiquer tous les autres noms du certificat :</span><span class="sxs-lookup"><span data-stu-id="b0233-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="b0233-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-155">sip.fabrikam.com</span></span>

<span data-ttu-id="b0233-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="b0233-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-157">meet.fabrikam.com</span></span>

<span data-ttu-id="b0233-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-158">admin.fabrikam.com</span></span>

<span data-ttu-id="b0233-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b0233-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b0233-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0233-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0233-161">See Also</span></span>


[<span data-ttu-id="b0233-162">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="b0233-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

