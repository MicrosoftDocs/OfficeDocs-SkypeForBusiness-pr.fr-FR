---
title: 'Lync Server 2013 : Vérification ou configuration de l’authentification et de la certification dans les répertoires virtuels des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="9ce1a-102">Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="9ce1a-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ce1a-103">_**Dernière modification de la rubrique:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="9ce1a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="9ce1a-104">Suivez la procédure ci-dessous pour configurer le certificat sur les répertoires virtuels d’Internet Information Services (IIS) ou vérifier que le certificat est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="9ce1a-105">Appliquez la procédure suivante à chaque serveur exécutant IIS dans votre pool de serveurs Lync interne et au directeur facultatif.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ce1a-106">La procédure suivante définit une procédure permettant de demander un certificat combiné qui est utilisé pour tous les rôles Lync Server, site Web interne et site Web externe dans IIS.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="9ce1a-107">Lync Server 2010 a présenté un ensemble d’applets de&nbsp;certification Windows PowerShell Lync Server Management Shell pour une vue rapide de la gestion de la demande de certificat, de l’importation et de l’affectation.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="9ce1a-108">La procédure suppose qu’il existe une autorité de certification déployée en interne (CA) qui peut traiter la demande.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="9ce1a-109">Si vous utilisez des certificats publics pour votre serveur Lync, ou si votre autorité de certification nécessite une demande hors connexion, voir la syntaxe détaillée de cette rubrique pour plus d’informations sur le paramètre – OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="9ce1a-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Requête-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="9ce1a-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="9ce1a-111">Pour configurer l’authentification et les certificats sur les répertoires virtuels IIS</span><span class="sxs-lookup"><span data-stu-id="9ce1a-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="9ce1a-112">Pour pouvoir effectuer les opérations suivantes, vous devez être connecté à l’ordinateur (serveur frontal ou directeur) sur lequel les services Web sont installés et être un administrateur local.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="9ce1a-113">Vous devez disposer des autorisations de **lecture** et d' **inscription** sur l’autorité de certification auprès desquelles vous demandez des certificats, si celle-ci est l’autorité de certification de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="9ce1a-114">Vous n’avez pas besoin d’autorisations sur l’autorité de certification si vous allez configurer et envoyer une demande de certificat hors connexion.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="9ce1a-115">Cliquez sur **Démarrer**, sur **tous les programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="9ce1a-116">Dans le **Gestionnaire des services Internet (IIS)**, sélectionnez **ServerName**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="9ce1a-117">Dans l' **affichage fonctionnalités**, sélectionnez **certificats de serveur**, cliquez avec le bouton droit, puis sélectionnez Ouvrir la **fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9ce1a-118">Dans l’affichage fonctionnalités des certificats de serveur, si des certificats sont attribués au serveur, ils s’affichent ici.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="9ce1a-119">Si un certificat répond à la configuration requise pour le site Web externe dans IIS, vous pouvez le réutiliser.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="9ce1a-120">Pour afficher un certificat, cliquez avec le bouton droit sur le certificat, puis sélectionnez <STRONG>afficher.</STRONG></span><span class="sxs-lookup"><span data-stu-id="9ce1a-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="9ce1a-121">Sur le serveur frontal ou le directeur pour lequel vous demandez le certificat, cliquez sur **Démarrer**, sélectionnez **tous les programmes**, **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="9ce1a-122">Dans Lync Server Management Shell, tapez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="9ce1a-123">La sortie est une liste des certificats actuellement sur le serveur dans le magasin de certificats personnels de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="9ce1a-124">Notez que dans le certificat combiné (autrement dit, les services Web internes et externes par défaut utilisent le même certificat) vous constaterez que la propriété Use sera remplie avec la valeur par défaut, WebServicesInternal et WebServicesExternal.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="9ce1a-125">Par ailleurs, la propriété d’empreinte est identique pour chaque type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="9ce1a-126">Un exemple de sortie de Get-CsCertificate est illustré dans cet exemple:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="9ce1a-127">![Get-CsCertificate informations sur l’état actuel de scert] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate informations sur l’état actuel de scert")</span><span class="sxs-lookup"><span data-stu-id="9ce1a-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="9ce1a-128">Dans Lync Server Management Shell, tapez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="9ce1a-129">Où la commande complète s’afficherait comme suit:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9ce1a-130">Par défaut, la requête-CsCertificate remplit le nom du sujet avec le nom du serveur ou du pool et les entrées du nom alternatif du serveur et celles du nom de domaine complet (FQDN) du serveur et les noms de domaine complets des services Web internes et externes.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="9ce1a-131">Pour ce faire, elle fait référence au document topologique dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="9ce1a-132">S’il existe une valeur manquante et que vous avez spécifié le paramètre – Verbose, vous serez averti que les valeurs calculées et réelles d’autres noms sont différentes, mais qu’elle ne vous indique pas quelles valeurs sont manquantes.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="9ce1a-133">Elle vous fournit la valeur calculée entière que l’applet de la cmdlet référence.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="9ce1a-134">Utilisez la chaîne de noms alternatifs calculés dans la sortie pour demander à nouveau le certificat qui inclura toutes les valeurs.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="9ce1a-135">![Sortie d’une demande de certificat à l’aide d’une requête-CsCertifica] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Sortie d’une demande de certificat à l’aide d’une requête-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="9ce1a-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="9ce1a-136">Dans Lync Server Management Shell, tapez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="9ce1a-137">Où la commande complète s’afficherait comme suit:</span><span class="sxs-lookup"><span data-stu-id="9ce1a-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="9ce1a-138">La sortie de l’applet de commande Set-CsCertificate indique que le certificat (identifié par l’empreinte numérique du certificat) est attribué à l’utilisation par défaut de WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="9ce1a-139">![Sortie de Set-CsCertificate sur IIS WebEx] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Sortie de Set-CsCertificate sur IIS WebEx")</span><span class="sxs-lookup"><span data-stu-id="9ce1a-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="9ce1a-140">Pour vérifier ou configurer l’authentification et les certificats dans les répertoires virtuels d’IIS</span><span class="sxs-lookup"><span data-stu-id="9ce1a-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="9ce1a-141">Cliquez sur **Démarrer**, sur **tous les programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="9ce1a-142">Dans le **Gestionnaire des services Internet (IIS)**, développez **NomServeur**, puis **sites**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="9ce1a-143">Cliquez avec le bouton droit sur **site Web externe de Lync Server**, puis cliquez sur **modifier les liaisons** .</span><span class="sxs-lookup"><span data-stu-id="9ce1a-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="9ce1a-144">Vérifiez que https est associé au port 4443, puis cliquez sur **https**.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="9ce1a-145">Sélectionnez l’entrée HTTPs, cliquez sur **modifier**, puis vérifiez que Lync Server WebServicesExternalCertificate est lié à ce protocole.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="9ce1a-146">Comparez l’empreinte numérique de l’applet de connexion Set-CsCertificate pour vous assurer que le certificat attendu est associé correctement à la liaison HTTPs.</span><span class="sxs-lookup"><span data-stu-id="9ce1a-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ce1a-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ce1a-147">See Also</span></span>


[<span data-ttu-id="9ce1a-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="9ce1a-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="9ce1a-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="9ce1a-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

