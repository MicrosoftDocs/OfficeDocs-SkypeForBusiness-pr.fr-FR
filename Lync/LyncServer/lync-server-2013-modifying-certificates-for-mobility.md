---
title: 'Lync Server 2013 : modification des certificats pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b10ea662d055812b9fccaa730a936033aaea077c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515161"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="0716a-102">Modification des certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0716a-102">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0716a-103">_**Dernière modification de la rubrique :** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="0716a-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="0716a-104">Pour prendre en charge les connexions sécurisées entre votre environnement Lync et vos clients mobiles, les certificats SSL (Secure Socket Layer) de votre pool de directeurs, de votre pool frontal et de votre proxy inverse doivent être mis à jour avec certaines entrées de SAN (autre nom de sujet) supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0716a-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="0716a-105">Pour plus d’informations sur les exigences de certificat pour la mobilité, voir la section relative aux exigences de certificat dans la rubrique [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mais vous devez essentiellement obtenir de nouveaux certificats auprès de l’autorité de certification avec les entrées San supplémentaires incluses, puis ajouter ces certificats en suivant les étapes de cet article.</span><span class="sxs-lookup"><span data-stu-id="0716a-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="0716a-106">Bien entendu avant de commencer, il est généralement judicieux de savoir quels sont les autres noms de sujet que vos certificats possèdent déjà.</span><span class="sxs-lookup"><span data-stu-id="0716a-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="0716a-107">Si vous n’êtes pas sûr de ce qui a déjà été configuré, il existe de nombreuses façons de le découvrir. Alors que l’option permet d’exécuter les commandes **Get-CsCertificate** et d’autres commandes PowerShell pour afficher ces informations, (ce qui est décrit ci-dessous) par défaut, les données sont tronquées, de sorte que vous ne pouvez pas voir toutes les propriétés dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="0716a-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="0716a-108">Pour obtenir un bon aperçu du certificat et de toutes ses propriétés, vous pouvez accéder à la console MMC (Microsoft Management Console) et charger le composant logiciel enfichable Certificats (que nous allons également suivre ci-dessous), ou vous pouvez simplement vérifier l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0716a-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="0716a-109">Comme indiqué ci-dessus, les étapes suivantes vous guideront tout au long du processus de mise à jour des certificats à l’aide de Lync Server Management Shell et de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="0716a-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="0716a-110">Si vous souhaitez plutôt utiliser l’Assistant certificat dans l’Assistant Déploiement de Lync Server pour cela, vous pouvez vérifier la [Configuration des certificats pour le directeur dans Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) pour le directeur ou le pool Directeur, si vous en avez configuré un (vous n’avez peut-être pas utilisé).</span><span class="sxs-lookup"><span data-stu-id="0716a-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="0716a-111">Pour le serveur frontal ou le pool frontal, consultez la rubrique [configure Certificates for Servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="0716a-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="0716a-112">Pour en savoir plus, il est possible que vous disposiez d’un seul certificat par défaut dans votre environnement Lync Server 2013 ou que vous disposiez de certificats distincts pour la valeur par défaut (tout sauf les services Web), WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="0716a-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="0716a-113">Quelle que soit votre configuration, ces étapes doivent vous aider.</span><span class="sxs-lookup"><span data-stu-id="0716a-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="0716a-114">Pour mettre à jour les certificats avec de nouveaux noms de sujet alternatifs à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0716a-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="0716a-115">Vous devez vous connecter à votre serveur Lync Server 2013 à l’aide d’un compte disposant de droits et d’autorisations d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="0716a-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="0716a-116">En outre, si vous exécutez la requête PowerShell **-CsCertificate** aux étapes 12 et ultérieures, le compte doit disposer de droits sur l’autorité de certification (ca) spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0716a-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="0716a-117">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0716a-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0716a-118">Avant de pouvoir attribuer un certificat mis à jour, vous devez déterminer les certificats qui ont été attribués au serveur et le type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="0716a-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="0716a-119">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="0716a-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="0716a-120">Passez en revue la sortie de l’étape précédente pour voir si un seul certificat a été affecté à plusieurs utilisations ou si un certificat différent est affecté à chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="0716a-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="0716a-121">Recherchez le mode d’utilisation d’un certificat dans le paramètre use.</span><span class="sxs-lookup"><span data-stu-id="0716a-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="0716a-122">Comparez le paramètre Thumbprint des certificats affichés pour savoir si le même certificat a plusieurs utilisations.</span><span class="sxs-lookup"><span data-stu-id="0716a-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="0716a-123">Gardez votre oeil sur le paramètre empreinte numérique.</span><span class="sxs-lookup"><span data-stu-id="0716a-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="0716a-124">Mettez à jour le certificat.</span><span class="sxs-lookup"><span data-stu-id="0716a-124">Update the certificate.</span></span> <span data-ttu-id="0716a-125">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0716a-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="0716a-126">Par exemple, si la cmdlet **Get-CsCertificate** affiche un certificat avec utilisation de la valeur par défaut, une autre avec une utilisation de WebServicesInternal et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte, sur la ligne de commande, vous devez taper :</span><span class="sxs-lookup"><span data-stu-id="0716a-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="0716a-127">**Important :**</span><span class="sxs-lookup"><span data-stu-id="0716a-127">**Important:**</span></span>
    
    <span data-ttu-id="0716a-128">Si un certificat distinct est affecté à chaque utilisation (la valeur d’empreinte numérique que vous avez vérifiée ci-dessus est donc différente pour chaque certificat), il est vital que vous n’exécutiez **pas** la cmdlet **Set-CsCertificate** avec plusieurs types, comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="0716a-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="0716a-129">Exécutez plutôt l’applet de commande **Set-CsCertificate** séparément pour chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="0716a-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="0716a-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0716a-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="0716a-131">Pour afficher le ou les certificats, cliquez sur **Démarrer**, puis sur **exécuter..**..</span><span class="sxs-lookup"><span data-stu-id="0716a-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="0716a-132">Tapez MMC pour ouvrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="0716a-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="0716a-133">Dans le menu de Microsoft Management Console, sélectionnez **Fichier**, **Ajouter/Supprimer un composant logiciel enfichable**, puis Certificats.</span><span class="sxs-lookup"><span data-stu-id="0716a-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="0716a-134">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0716a-134">Click **Add**.</span></span> <span data-ttu-id="0716a-135">Quand vous y êtes invité, sélectionnez **Compte d’ordinateur**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0716a-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="0716a-136">S’il s’agit du serveur où se trouve le certificat, sélectionnez **ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="0716a-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="0716a-137">Si le certificat se trouve sur un autre ordinateur, vous devez sélectionner **un autre ordinateur**, puis taper le nom de domaine complet de l’ordinateur ou cliquer sur **Parcourir** dans **Entrez le nom de l’objet à sélectionner**, puis tapez le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0716a-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="0716a-138">Cliquez sur **Vérifier les noms**.</span><span class="sxs-lookup"><span data-stu-id="0716a-138">Click **Check Names**.</span></span> <span data-ttu-id="0716a-139">Lorsque le nom de l’ordinateur est résolu, il est souligné.</span><span class="sxs-lookup"><span data-stu-id="0716a-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="0716a-140">Cliquez sur **OK**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="0716a-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="0716a-141">Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** .</span><span class="sxs-lookup"><span data-stu-id="0716a-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="0716a-p113">Pour afficher les propriétés du certificat, développez **Certificats**, développez **Personnel**, puis sélectionnez **Certificats**. Sélectionnez le certificat à afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="0716a-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="0716a-p114">Dans l’affichage **Certificat**, sélectionnez **Détails**. Vous pouvez ensuite sélectionner le nom d’objet du certificat en sélectionnant **Sujet** afin d’afficher le nom affecté et les propriétés associées.</span><span class="sxs-lookup"><span data-stu-id="0716a-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="0716a-146">Pour afficher les autres noms de l’objet affectés, sélectionnez **Autre nom de l’objet**.</span><span class="sxs-lookup"><span data-stu-id="0716a-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="0716a-147">Tous les autres noms de sujet affectés sont affichés ici.</span><span class="sxs-lookup"><span data-stu-id="0716a-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="0716a-148">Les autres noms du sujet trouvés ici sont de type **nom DNS** par défaut.</span><span class="sxs-lookup"><span data-stu-id="0716a-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="0716a-149">Vous devriez voir les membres suivants (tous devraient correspondre à des noms de domaine complets tels qu’ils sont représentés dans les enregistrements d’hôte DNS, à savoir A ou AAAA si IPv6 est en vigueur) :</span><span class="sxs-lookup"><span data-stu-id="0716a-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="0716a-150">Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool</span><span class="sxs-lookup"><span data-stu-id="0716a-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="0716a-151">Nom du serveur auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="0716a-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="0716a-152">Enregistrements d’URL simples, généralement meet et dialin.</span><span class="sxs-lookup"><span data-stu-id="0716a-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="0716a-153">Noms externes des services Web et des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web remplacés.</span><span class="sxs-lookup"><span data-stu-id="0716a-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="0716a-154">S’il est déjà attribué, le lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0716a-154">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="0716a-155">et lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0716a-155">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="0716a-156">présents.</span><span class="sxs-lookup"><span data-stu-id="0716a-156">records.</span></span>
    
    <span data-ttu-id="0716a-157">Le dernier élément est celui qui intéresse le plus, s’il existe une entrée SAN lyncdiscover et lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="0716a-157">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="0716a-158">Répétez ces étapes si vous avez plusieurs certificats à vérifier.</span><span class="sxs-lookup"><span data-stu-id="0716a-158">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="0716a-159">Une fois que vous avez ces informations, vous pouvez fermer l’affichage du certificat et MMC.</span><span class="sxs-lookup"><span data-stu-id="0716a-159">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="0716a-160">S’il manque un autre nom de l’objet pour le service de découverte automatique et si vous utilisez un certificat par défaut unique pour les types Default, WebServicesInternal et WebServiceExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0716a-160">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="0716a-161">À l’invite de ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="0716a-161">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0716a-162">Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="0716a-162">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="0716a-163">Au lieu de cela, vous devez utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="0716a-163">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="0716a-164">Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="0716a-164">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="0716a-165">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0716a-165">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="0716a-166">Pour affecter le certificat, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0716a-166">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="0716a-167">Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour le certificat qui vient d’être émis.</span><span class="sxs-lookup"><span data-stu-id="0716a-167">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="0716a-168">Pour un SAN de découverte automatique interne manquant lors de l’utilisation de certificats distincts pour default, WebServicesInternal et WebServicesExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0716a-168">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="0716a-169">À l’invite de ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="0716a-169">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0716a-170">Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="0716a-170">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="0716a-171">Au lieu de cela, vous devez utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="0716a-171">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="0716a-172">Lorsque vous utilisez le paramètre DomainName, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="0716a-172">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="0716a-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0716a-173">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="0716a-174">Pour un autre nom de sujet du service de découverte automatique externe manquant, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="0716a-174">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0716a-175">Si vous avez un grand nombre de domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="0716a-175">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="0716a-176">Au lieu de cela, vous devez utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="0716a-176">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="0716a-177">Lorsque vous utilisez le paramètre DomainName, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="0716a-177">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="0716a-178">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0716a-178">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="0716a-179">Pour affecter les types de certificat individuel, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0716a-179">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="0716a-180">Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour les certificats individuels qui viennent d’être émis.</span><span class="sxs-lookup"><span data-stu-id="0716a-180">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0716a-181">Pour noter, les étapes 12 et 13 doivent être exécutées uniquement si le compte qui les exécute a accès à l’autorité de certification avec les autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="0716a-181">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="0716a-182">Si vous ne parvenez pas à vous connecter avec un compte qui dispose de ces autorisations, ou si vous utilisez une autorité de certification publique ou distante pour vos certificats, vous devez les demander via l’Assistant Déploiement Lync Server, qui a été touché en haut de l’article.</span><span class="sxs-lookup"><span data-stu-id="0716a-182">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

