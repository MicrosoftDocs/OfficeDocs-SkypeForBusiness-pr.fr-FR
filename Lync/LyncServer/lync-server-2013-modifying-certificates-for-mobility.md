---
title: 'Lync Server 2013 : Modification des certificats pour la mobilité'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="1756a-102">Modification des certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1756a-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1756a-103">_**Dernière modification de la rubrique :** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="1756a-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="1756a-104">Pour prendre en charge les connexions sécurisées entre votre environnement Lync et vos clients mobiles, les certificats SSL (Secure Socket Layer) pour votre pool de Directors, votre pool frontal et votre proxy inverse doivent être mis à jour avec un autre nom d’objet supplémentaire ( SAN).</span><span class="sxs-lookup"><span data-stu-id="1756a-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="1756a-105">Pour plus d’informations sur les exigences en matière de certificats pour la mobilité, voir la section exigences relatives aux certificats dans les [exigences techniques de mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mais de manière générale, vous devez obtenir de nouveaux certificats auprès de l’autorité de certification et ajouter ces certificats en suivant les étapes de cet article.</span><span class="sxs-lookup"><span data-stu-id="1756a-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="1756a-106">Bien entendu, avant de commencer, il est généralement judicieux de savoir quel autre nom de l’objet possède déjà vos certificats.</span><span class="sxs-lookup"><span data-stu-id="1756a-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="1756a-107">Si vous n’êtes pas sûr de ce que vous avez déjà configuré, il existe de nombreux moyens de le découvrir. Même si l’option est là pour exécuter la commande **Get-CsCertificate** et les autres commandes PowerShell pour afficher ces informations, (ce que nous allons voir ci-dessous) par défaut, les données sont tronquées de façon à ce que vous n’obteniez pas toutes les propriétés dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="1756a-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="1756a-108">Pour obtenir une vue d’ensemble du certificat et de toutes ses propriétés, vous pouvez accéder à Microsoft Management Console (MMC) et charger le composant logiciel enfichable Certificats (que nous allons également suivre ci-dessous), ou vous pouvez simplement consulter l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1756a-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="1756a-109">Comme indiqué plus haut, les étapes suivantes vous guident dans la mise à jour des certificats à l’aide de Lync Server Management Shell et de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="1756a-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="1756a-110">Si vous êtes intéressé par l’utilisation de l’Assistant certificat dans l’Assistant Déploiement de Lync Server pour ce faire, vous pouvez cocher [configurer des certificats pour le directeur de Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) pour le directeur ou le pool de réalisateur, si vous en avez configuré un (vous ne l’avez peut-être pas).</span><span class="sxs-lookup"><span data-stu-id="1756a-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="1756a-111">Pour le serveur frontal ou le pool frontal, vous pouvez voir [configurer des certificats pour les serveurs dans Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1756a-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="1756a-112">En dernier lieu, il est possible que vous disposiez d’un seul certificat par défaut dans votre environnement Lync Server 2013 ou que vous ayez des certificats séparés par défaut (tout sauf les services Web), WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="1756a-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="1756a-113">Quelle que soit la configuration, suivez les étapes ci-dessous pour vous aider.</span><span class="sxs-lookup"><span data-stu-id="1756a-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="1756a-114">Pour mettre à jour les certificats avec d’autres noms d’objet à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1756a-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="1756a-115">Vous devez vous connecter à votre serveur Lync Server 2013 à l’aide d’un compte disposant de droits d’administrateur local et d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="1756a-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="1756a-116">Par ailleurs, si vous exécutez la requête PowerShell **-CsCertificate** au cours des étapes 12 et ultérieures, le compte doit disposer de droits d’autorité de certification spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1756a-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="1756a-117">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1756a-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1756a-118">Pour pouvoir attribuer un certificat mis à jour, vous devez identifier les certificats qui ont été attribués au serveur et le type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1756a-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="1756a-119">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1756a-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="1756a-120">Passez en revue la sortie de l’étape précédente pour voir si un seul certificat a été attribué pour plusieurs usages ou si un certificat différent est attribué à chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="1756a-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="1756a-121">Dans le paramètre use, recherchez le mode d’utilisation d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="1756a-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="1756a-122">Comparez le paramètre d’empreinte numérique pour les certificats affichés pour déterminer si le même certificat a des usages multiples.</span><span class="sxs-lookup"><span data-stu-id="1756a-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="1756a-123">Restez au coeur du paramètre d’empreinte numérique.</span><span class="sxs-lookup"><span data-stu-id="1756a-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="1756a-124">Mettez à jour le certificat.</span><span class="sxs-lookup"><span data-stu-id="1756a-124">Update the certificate.</span></span> <span data-ttu-id="1756a-125">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1756a-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="1756a-126">Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat utilisant la valeur par défaut, une autre avec une utilisation de WebServicesInternal, et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte numérique, sur la ligne de commande, vous devez taper :</span><span class="sxs-lookup"><span data-stu-id="1756a-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="1756a-127">**Important :**</span><span class="sxs-lookup"><span data-stu-id="1756a-127">**Important:**</span></span>
    
    <span data-ttu-id="1756a-128">Si un certificat distinct est attribué à chaque utilisation (de sorte que la valeur de l’empreinte numérique que vous avez examinée ci-dessus est différente pour chaque certificat), il est essentiel que vous n’exécutiez **pas** l’applet de contrôle **Set-CsCertificate** avec plusieurs types, comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1756a-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="1756a-129">Dans ce cas, exécutez l’applet de la cmdlet **Set-CsCertificate** séparément pour chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="1756a-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="1756a-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1756a-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="1756a-131">Pour afficher le certificat (ou les certificats), cliquez sur **Démarrer**, puis sur **exécuter..**..</span><span class="sxs-lookup"><span data-stu-id="1756a-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="1756a-132">Tapez MMC pour ouvrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="1756a-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="1756a-133">Dans le menu MMC, sélectionnez **fichier**, choisissez **Ajouter/supprimer un composant logiciel enfichable...**, puis sélectionnez certificats.</span><span class="sxs-lookup"><span data-stu-id="1756a-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="1756a-134">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1756a-134">Click **Add**.</span></span> <span data-ttu-id="1756a-135">Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1756a-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="1756a-136">S’il s’agit du serveur sur lequel se trouve le certificat, sélectionnez **ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="1756a-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="1756a-137">Si le certificat se trouve sur un autre ordinateur, vous devez sélectionner **un autre ordinateur**, puis taper le nom de domaine complet de l’ordinateur ou cliquer sur **Parcourir** dans **entrer le nom de l’objet pour le sélectionner**, puis taper le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1756a-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="1756a-138">Cliquez sur **vérifier les noms**.</span><span class="sxs-lookup"><span data-stu-id="1756a-138">Click **Check Names**.</span></span> <span data-ttu-id="1756a-139">Lorsque le nom de l’ordinateur est résolu, il est souligné.</span><span class="sxs-lookup"><span data-stu-id="1756a-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="1756a-140">Cliquez sur **OK**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1756a-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="1756a-141">Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants additionnels** .</span><span class="sxs-lookup"><span data-stu-id="1756a-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="1756a-142">Pour afficher les propriétés du certificat, développez **certificats**, **personnel**, puis sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="1756a-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="1756a-143">Sélectionnez le certificat que vous voulez afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="1756a-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="1756a-144">Dans l’affichage **certificat** , sélectionnez **Détails**.</span><span class="sxs-lookup"><span data-stu-id="1756a-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="1756a-145">À partir de cet emplacement, vous pouvez sélectionner le nom du sujet du certificat en sélectionnant **objet** et le nom de l’objet affecté ainsi que les propriétés associées apparaissent.</span><span class="sxs-lookup"><span data-stu-id="1756a-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="1756a-146">Pour afficher les noms de remplacement de l’objet affecté, sélectionnez **autre nom**de l’objet.</span><span class="sxs-lookup"><span data-stu-id="1756a-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="1756a-147">Les noms de remplacement de l’objet affecté apparaissent ici.</span><span class="sxs-lookup"><span data-stu-id="1756a-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="1756a-148">Le nom de remplacement de l’objet indiqué ici est de type **nom DNS** par défaut.</span><span class="sxs-lookup"><span data-stu-id="1756a-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="1756a-149">Les membres suivants doivent s’afficher (qui doivent correspondre à des noms de domaine complets tels qu’ils sont représentées dans l’hôte DNS (A ou, si vous avez des enregistrements IPv6 AAAA) :</span><span class="sxs-lookup"><span data-stu-id="1756a-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="1756a-150">Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool</span><span class="sxs-lookup"><span data-stu-id="1756a-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="1756a-151">Nom du serveur auquel le certificat est affecté</span><span class="sxs-lookup"><span data-stu-id="1756a-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="1756a-152">Enregistrements d’URL simples, en règle générale et en ligne</span><span class="sxs-lookup"><span data-stu-id="1756a-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="1756a-153">Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.</span><span class="sxs-lookup"><span data-stu-id="1756a-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="1756a-154">S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="1756a-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="1756a-155">Le dernier élément correspond à ce que vous êtes le plus intéressé par le biais d’une entrée SAN lyncdiscover et lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="1756a-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="1756a-156">Répétez ces étapes si vous avez plusieurs certificats à vérifier.</span><span class="sxs-lookup"><span data-stu-id="1756a-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="1756a-157">Une fois que vous disposez de ces informations, vous pouvez fermer l’affichage du certificat et la console MMC.</span><span class="sxs-lookup"><span data-stu-id="1756a-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="1756a-158">Si un autre nom de l’objet du service de découverte automatique est manquant et que vous utilisez un certificat par défaut unique pour les types WebServicesInternal et WebServiceExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1756a-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="1756a-159">Dans l’invite de la ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="1756a-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1756a-160">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="1756a-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1756a-161">À la place, vous devez utiliser le paramètre NomDomaine.</span><span class="sxs-lookup"><span data-stu-id="1756a-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1756a-162">Lorsque vous utilisez le paramètre nom_domaine, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="1756a-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="1756a-163">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1756a-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="1756a-164">Pour attribuer le certificat, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1756a-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="1756a-165">Où « empreinte » est l’empreinte digitale affichée pour le certificat nouvellement émis.</span><span class="sxs-lookup"><span data-stu-id="1756a-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="1756a-166">Pour un SAN de découverte automatique absent manquant lors de l’utilisation de certificats séparés par défaut, WebServicesInternal et WebServicesExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1756a-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="1756a-167">Dans l’invite de la ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="1756a-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1756a-168">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="1756a-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1756a-169">À la place, vous devez utiliser le paramètre NomDomaine.</span><span class="sxs-lookup"><span data-stu-id="1756a-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1756a-170">Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le nom de domaine complet (FQDN) du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="1756a-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="1756a-171">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1756a-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="1756a-172">Pour un autre nom d’objet de découverte automatique externe manquant, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1756a-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="1756a-173">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="1756a-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="1756a-174">À la place, vous devez utiliser le paramètre NomDomaine.</span><span class="sxs-lookup"><span data-stu-id="1756a-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="1756a-175">Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le nom de domaine complet (FQDN) du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="1756a-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="1756a-176">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1756a-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="1756a-177">Pour attribuer les types de certificats individuels, tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1756a-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="1756a-178">Où « empreinte » est l’empreinte digitale affichée pour les certificats individuels émis.</span><span class="sxs-lookup"><span data-stu-id="1756a-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1756a-179">Remarque : les étapes 12 et 13 doivent être exécutées uniquement si le compte qui les exécute a accès à l’autorité de certification avec les autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="1756a-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="1756a-180">Si vous ne parvenez pas à vous connecter avec un compte qui dispose de ces autorisations, ou si vous utilisez une autorité de certification publique ou à distance pour vos certificats, vous devez les demander via l’Assistant Déploiement de Lync Server, qui a été touché en haut du bis.</span><span class="sxs-lookup"><span data-stu-id="1756a-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

