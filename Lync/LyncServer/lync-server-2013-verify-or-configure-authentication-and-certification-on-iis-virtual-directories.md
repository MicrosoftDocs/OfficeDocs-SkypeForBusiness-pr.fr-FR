---
title: 'Lync Server 2013 : vérification ou configuration de l’authentification et de la certification sur les répertoires virtuels IIS'
description: 'Lync Server 2013 : Vérifiez ou configurez l’authentification et la certification sur les répertoires virtuels IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4d583eda7f0c7fb32b51dd5df6eb48af9b20d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560210"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="37c6e-103">Vérifier ou configurer l’authentification et la certification sur les répertoires virtuels IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37c6e-103">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c6e-104">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="37c6e-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="37c6e-105">Utilisez la procédure suivante pour configurer le certificat sur vos répertoires virtuels IIS (Internet Information Services) ou vérifier que le certificat est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="37c6e-105">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="37c6e-106">Effectuez la procédure suivante sur chaque serveur qui exécute les services Internet (IIS) dans votre pool Lync Server interne et dans les serveurs de pools facultatifs Director.</span><span class="sxs-lookup"><span data-stu-id="37c6e-106">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37c6e-107">La procédure suivante définit une procédure pour demander un certificat combiné qui est utilisé à des fins telles que Lync Server, le site Web interne et le site Web externe dans les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="37c6e-107">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="37c6e-108">Lync Server 2010 a introduit un ensemble d’applets de commande Windows PowerShell Lync Server Management Shell &nbsp; pour l’objectif de la gestion de la demande de certificat, de l’importation et de l’affectation.</span><span class="sxs-lookup"><span data-stu-id="37c6e-108">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="37c6e-109">La procédure part du principe qu’une autorité de certification capable de traiter la demande a été déployée en interne.</span><span class="sxs-lookup"><span data-stu-id="37c6e-109">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="37c6e-110">Si vous utilisez des certificats publics pour votre serveur Lync Server ou si votre autorité de certification requiert une demande hors connexion, consultez la syntaxe détaillée dans cette rubrique pour plus d’informations sur le paramètre – OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="37c6e-110">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="37c6e-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="37c6e-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="37c6e-112">Pour configurer l’authentification et les certificats au niveau des répertoires virtuels IIS</span><span class="sxs-lookup"><span data-stu-id="37c6e-112">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="37c6e-113">Pour effectuer correctement les opérations suivantes, vous devez être connecté à l’ordinateur (serveur frontal ou directeur) où les services Web sont installés et être administrateur local.</span><span class="sxs-lookup"><span data-stu-id="37c6e-113">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="37c6e-114">Vous devez disposer des autorisations de **lecture** et d’**inscription** sur l’autorité de certification à laquelle vous demanderez les certificats, si l’autorité de certification est l’autorité de certification de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="37c6e-114">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="37c6e-115">Vous n’avez pas besoin d’autorisations sur l’autorité de certification si vous prévoyez de configurer et d’adresser une demande de certificat hors connexion.</span><span class="sxs-lookup"><span data-stu-id="37c6e-115">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="37c6e-116">Cliquez sur **Démarrer**, sélectionnez **Tous les programmes**, **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-116">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="37c6e-p104">Dans le **Gestionnaire des services Internet (IIS)**, sélectionnez **NomServeur**. Dans **Affichage des fonctionnalités**, sélectionnez **Certificats de serveur**, cliquez avec le bouton droit, puis sélectionnez **Ouvrir la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="37c6e-p105">Si des certificats sont assignés au serveur, ils figurent parmi les certificats de serveur de l’affichage des fonctionnalités. Si un certificat répond aux conditions requises pour le site web externe dans IIS, vous pouvez réutiliser ce certificat. Pour afficher un certificat, cliquez avec le bouton droit sur le certificat et sélectionnez <STRONG>Afficher…</STRONG></span><span class="sxs-lookup"><span data-stu-id="37c6e-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="37c6e-122">Sur le serveur frontal ou directeur pour lequel vous demandez le certificat, cliquez sur **Démarrer**, sélectionnez **tous les programmes**, **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-122">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="37c6e-123">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="37c6e-123">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="37c6e-p106">Vous obtenez alors la liste des certificats actuellement présents sur le serveur, dans le magasin de certificats personnel de l’ordinateur. À noter que dans le certificat combiné (c’est-à-dire, quand les services web internes et les services web externes par défaut utilisent le même certificat), vous constaterez que la propriété Use affiche les valeurs Default, WebServicesInternal et WebServicesExternal. De même, la propriété Thumbprint a la même valeur pour chaque type Use. Un exemple de résultat de Get-CsCertificate est fourni dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="37c6e-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="37c6e-128">![Get-CsCertificate informations sur l’état actuel de scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informations Get-CsCertificate sur l’état actuel de scert")</span><span class="sxs-lookup"><span data-stu-id="37c6e-128">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="37c6e-129">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="37c6e-129">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="37c6e-130">La commande complète apparaîtra comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="37c6e-130">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="37c6e-p107">Par défaut, Request-CsCertificate renseigne le nom du sujet avec le nom du serveur ou du pool et remplit l’autre nom du sujet avec des entrées constituées du nom de domaine complet du serveur, du nom de domaine complet du pool, des noms de domaine complets d’URL simples et des noms de domaine complets des services web interne et externe. Pour cela, l’applet de commande se réfère aux documents de topologie de votre déploiement. S’il manque une valeur et que vous avez spécifié le paramètre –Verbose, elle vous signale que les valeurs calculées et réelles des autres noms sont différentes, mais elle ne vous indique pas la valeur manquante. Elle vous fournit la valeur calculée complète à laquelle l’applet de commande se réfère. Utilisez la chaîne des autres noms calculés figurant dans le résultat pour faire une nouvelle demande de certificat qui comportera toutes les valeurs.</span><span class="sxs-lookup"><span data-stu-id="37c6e-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="37c6e-136">![Sortie de la demande de certificat à l’aide de request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Sortie de la demande de certificat à l’aide de Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="37c6e-136">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="37c6e-137">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="37c6e-137">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="37c6e-138">La commande complète apparaîtra comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="37c6e-138">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="37c6e-139">La sortie de l’applet de commande Set-CsCertificate vous montre que le même certificat (identifié par l’empreinte numérique du certificat) est assigné pour l’utilisation de Default, WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="37c6e-139">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="37c6e-140">![Sortie d' Set-CsCertificate sur IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Sortie d' Set-CsCertificate sur IIS WebExt")</span><span class="sxs-lookup"><span data-stu-id="37c6e-140">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="37c6e-141">Pour vérifier ou configurer l’authentification et les certificats au niveau des répertoires virtuels IIS</span><span class="sxs-lookup"><span data-stu-id="37c6e-141">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="37c6e-142">Cliquez sur **Démarrer**, sélectionnez **Tous les programmes**, **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-142">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="37c6e-143">Dans le **Gestionnaire des services Internet (IIS)**, développez **ServerName**, puis **sites**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-143">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="37c6e-144">Cliquez avec le bouton droit sur **Lync Server External Web Site**, puis cliquez sur **Modifier les liaisons**</span><span class="sxs-lookup"><span data-stu-id="37c6e-144">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="37c6e-145">Vérifiez que https est associé au port 4443, puis cliquez sur **https**.</span><span class="sxs-lookup"><span data-stu-id="37c6e-145">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="37c6e-146">Sélectionnez l’entrée HTTPs, cliquez sur **modifier**, puis vérifiez que Lync Server WebServicesExternalCertificate est lié à ce protocole.</span><span class="sxs-lookup"><span data-stu-id="37c6e-146">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="37c6e-147">Comparez l’empreinte numérique de l’applet de commande Set-CsCertificate pour vous assurer que le certificat attendu est correctement associé à la liaison HTTPS.</span><span class="sxs-lookup"><span data-stu-id="37c6e-147">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37c6e-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37c6e-148">See Also</span></span>


[<span data-ttu-id="37c6e-149">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="37c6e-149">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="37c6e-150">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="37c6e-150">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

