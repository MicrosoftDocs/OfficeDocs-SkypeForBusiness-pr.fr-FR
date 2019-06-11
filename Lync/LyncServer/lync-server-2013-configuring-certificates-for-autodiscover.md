---
title: 'Lync Server 2013: configuration de certificats pour la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f8a90-102">Configuration de certificats pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8a90-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8a90-103">_**Dernière modification de la rubrique:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="f8a90-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="f8a90-104">Les certificats de votre pool de réalisateurs, de votre pool frontal et du proxy inverse requièrent des entrées de nom alternatif supplémentaires pour la prise en charge de connexions sécurisées avec les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="f8a90-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8a90-105">Vous pouvez utiliser l’applet de cmdlet <STRONG>Get-CsCertificate</STRONG> pour afficher des informations sur les certificats actuellement attribués.</span><span class="sxs-lookup"><span data-stu-id="f8a90-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="f8a90-106">Toutefois, le mode par défaut tronque les propriétés du certificat et n’affiche pas toutes les valeurs de la propriété SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="f8a90-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="f8a90-107">Vous pouvez utiliser les applets de requête <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate et <STRONG>Set-CsCertificate</STRONG> pour afficher des informations et pour demander et affecter des certificats.</span><span class="sxs-lookup"><span data-stu-id="f8a90-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="f8a90-108">Néanmoins, il ne s’agit pas de la meilleure méthode à utiliser si vous n’êtes pas sûr des propriétés des autres noms d’objet (SAN) sur le certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="f8a90-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="f8a90-109">Pour afficher le certificat et tous les membres de propriété, il est préférable d’utiliser le composant logiciel enfichable Certificats dans la <EM>console MMC</EM> ou utiliser l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a90-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="f8a90-110">Dans l’Assistant Déploiement de Lync Server, vous pouvez utiliser l’Assistant Certificat pour afficher les propriétés du certificat.</span><span class="sxs-lookup"><span data-stu-id="f8a90-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="f8a90-111">Les procédures d’affichage, de demande et d’attribution d’un certificat à l’aide de Lync Server Management Shell et de <EM>Microsoft Management Console (MMC)</EM> sont décrites dans les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="f8a90-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="f8a90-112">Pour utiliser l’Assistant Déploiement de Lync Server, voir détails ici si vous avez déployé le directeur ou le pool de réalisateurs facultatif: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurer des certificats pour le directeur dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f8a90-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="f8a90-113">Pour le serveur frontal ou le pool frontal, voir les détails ici: <A href="lync-server-2013-configure-certificates-for-servers.md">configurer des certificats pour les serveurs dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f8a90-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="f8a90-114">Les étapes initiales de cette procédure sont des étapes de préparation, qui vous permettent de vous orienter sur le rôle joué par les certificats actuels.</span><span class="sxs-lookup"><span data-stu-id="f8a90-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="f8a90-115">Par défaut, les certificats n’ont pas de lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;nom&gt; de domaine interne, sauf si vous avez déjà installé les services de mobilité ou si vous avez préparé vos certificats à l’avance.</span><span class="sxs-lookup"><span data-stu-id="f8a90-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="f8a90-116">Cette procédure utilise l’exemple de nom de domaine SIP’contoso.com’et l’exemple de nom de domaine interne’contoso.net'.</span><span class="sxs-lookup"><span data-stu-id="f8a90-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="f8a90-117">La configuration de certificat par défaut pour Lync Server 2013 et Lync Server 2010 consiste à utiliser un certificat unique (nommé «par défaut») avec les objectifs par défaut (pour tous les usages sauf pour les services Web), WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="f8a90-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="f8a90-118">Une configuration facultative consiste à utiliser des certificats séparés pour chaque objectif.</span><span class="sxs-lookup"><span data-stu-id="f8a90-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="f8a90-119">Les certificats peuvent être gérés en utilisant les applets de certification Lync Server Management Shell et Windows PowerShell, ou en utilisant l’Assistant certificat dans l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a90-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="f8a90-120">Pour mettre à jour les certificats avec d’autres noms d’objet à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8a90-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f8a90-121">Ouvrez une session sur l’ordinateur à l’aide d’un compte disposant de droits d’administrateur local et d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="f8a90-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="f8a90-122">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f8a90-123">Déterminez les certificats attribués au serveur et le type d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="f8a90-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="f8a90-124">Vous avez besoin de ces informations lors de l’étape suivante pour affecter le certificat mis à jour.</span><span class="sxs-lookup"><span data-stu-id="f8a90-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="f8a90-125">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f8a90-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="f8a90-126">Regardez dans la sortie de l’étape précédente pour voir si un certificat unique est affecté à plusieurs usages ou si un certificat différent est attribué à chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="f8a90-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="f8a90-127">Dans le paramètre use, recherchez le mode d’utilisation d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="f8a90-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="f8a90-128">Comparez le paramètre d’empreinte numérique pour les certificats affichés pour déterminer si le même certificat a des usages multiples.</span><span class="sxs-lookup"><span data-stu-id="f8a90-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="f8a90-129">Mettez à jour le certificat.</span><span class="sxs-lookup"><span data-stu-id="f8a90-129">Update the certificate.</span></span> <span data-ttu-id="f8a90-130">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f8a90-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="f8a90-131">Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat utilisant la valeur par défaut, une autre avec une utilisation de WebServicesInternal, et une autre avec une utilisation de WebServicesExternal, et qu’ils ont tous la même valeur d’empreinte numérique, sur la ligne de commande, tapez:</span><span class="sxs-lookup"><span data-stu-id="f8a90-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="f8a90-132">**Important :**</span><span class="sxs-lookup"><span data-stu-id="f8a90-132">**Important:**</span></span>
    
    <span data-ttu-id="f8a90-133">Si un certificat distinct est attribué à chaque utilisation (la valeur de l’empreinte numérique est différente pour chaque certificat), il est important de ne pas exécuter l’applet de certification **Set-CsCertificate** avec plusieurs types.</span><span class="sxs-lookup"><span data-stu-id="f8a90-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="f8a90-134">Dans ce cas, exécutez l’applet de la cmdlet **Set-CsCertificate** séparément pour chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="f8a90-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="f8a90-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f8a90-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="f8a90-136">Pour afficher le certificat, cliquez sur **Démarrer**, puis sur **exécuter...**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="f8a90-137">Tapez MMC pour ouvrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="f8a90-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="f8a90-138">Dans le menu MMC, sélectionnez **fichier**, choisissez **Ajouter/supprimer un composant logiciel enfichable...**, puis sélectionnez certificats.</span><span class="sxs-lookup"><span data-stu-id="f8a90-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="f8a90-139">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-139">Click **Add**.</span></span> <span data-ttu-id="f8a90-140">Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="f8a90-141">Si le certificat se trouve sur cet ordinateur, sélectionnez **ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="f8a90-142">Si le certificat se trouve sur un autre ordinateur, sélectionnez **un autre ordinateur**, tapez le nom de domaine complet de l’ordinateur ou cliquez sur **Parcourir** dans **entrer le nom de l’objet à sélectionner**, puis tapez le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f8a90-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="f8a90-143">Cliquez sur **vérifier les noms**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-143">Click **Check Names**.</span></span> <span data-ttu-id="f8a90-144">Lorsque le nom de l’ordinateur est résolu, il est souligné.</span><span class="sxs-lookup"><span data-stu-id="f8a90-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="f8a90-145">Cliquez sur **OK**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="f8a90-146">Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants additionnels** .</span><span class="sxs-lookup"><span data-stu-id="f8a90-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8a90-147">Si le certificat n’apparaît pas dans la console, assurez-vous que vous n’avez pas sélectionné d’utilisateur ou de service.</span><span class="sxs-lookup"><span data-stu-id="f8a90-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="f8a90-148">Vous devez sélectionner ordinateur ou vous ne pouvez pas trouver le certificat probper.</span><span class="sxs-lookup"><span data-stu-id="f8a90-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="f8a90-149">Pour afficher les propriétés du certificat, développez **certificats**, **personnel**, puis sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="f8a90-150">Sélectionnez le certificat que vous voulez afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="f8a90-151">Dans l’affichage **certificat** , sélectionnez **Détails**.</span><span class="sxs-lookup"><span data-stu-id="f8a90-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="f8a90-152">À partir de cet emplacement, vous pouvez sélectionner le nom du sujet du certificat en sélectionnant **objet** et le nom de l’objet affecté ainsi que les propriétés associées apparaissent.</span><span class="sxs-lookup"><span data-stu-id="f8a90-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="f8a90-153">Pour afficher les noms de remplacement de l’objet affecté, sélectionnez **autre nom**de l’objet.</span><span class="sxs-lookup"><span data-stu-id="f8a90-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="f8a90-154">Tous les noms de domaine alternatifs attribués sont affichés.</span><span class="sxs-lookup"><span data-stu-id="f8a90-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="f8a90-155">Les noms d’objet alternatifs figurant dans la propriété sont de type **nom DNS** par défaut.</span><span class="sxs-lookup"><span data-stu-id="f8a90-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="f8a90-156">Les membres suivants doivent s’afficher (qui doivent correspondre à des noms de domaine complets tels qu’ils sont représentées dans l’hôte DNS (A ou, si vous avez des enregistrements IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="f8a90-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="f8a90-157">Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool</span><span class="sxs-lookup"><span data-stu-id="f8a90-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="f8a90-158">Nom du serveur auquel le certificat est affecté</span><span class="sxs-lookup"><span data-stu-id="f8a90-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="f8a90-159">Enregistrements d’URL simples, en règle générale et en ligne</span><span class="sxs-lookup"><span data-stu-id="f8a90-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="f8a90-160">Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.</span><span class="sxs-lookup"><span data-stu-id="f8a90-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="f8a90-161">S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="f8a90-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="f8a90-162">Le dernier élément correspond à ce qui est le plus intéressé, s’il y a une entrée lyncdiscover et lyncdiscoverinternal SAN.</span><span class="sxs-lookup"><span data-stu-id="f8a90-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="f8a90-163">Une fois que vous disposez de ces informations, vous pouvez fermer l’affichage du certificat et la console MMC.</span><span class="sxs-lookup"><span data-stu-id="f8a90-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="f8a90-164">S’il s’agit d’un service de découverte automatique, c’est-à-dire le lyncdiscover. \>nom\> de domaine et lyncdiscoverinternal. \<nom\> de domaine (basé sur s’il s’agit d’un certificat externe ou interne) le nom de l’autre nom de l’objet est manquant et que vous utilisez un certificat par défaut unique pour les types WebServicesInternal et WebServiceExternal, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f8a90-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="f8a90-165">Dans l’invite de la ligne de commande Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="f8a90-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="f8a90-166">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="f8a90-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="f8a90-167">À la place, vous devez utiliser le paramètre nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="f8a90-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="f8a90-168">Lorsque vous utilisez le paramètre nom_domaine, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="f8a90-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="f8a90-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f8a90-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="f8a90-170">Pour attribuer le certificat, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="f8a90-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="f8a90-171">Où «empreinte» est l’empreinte digitale affichée pour le certificat nouvellement émis.</span><span class="sxs-lookup"><span data-stu-id="f8a90-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="f8a90-172">Pour les noms de remplacement de l’objet de découverte automatique manquantes lors de l’utilisation de certificats séparés par défaut, WebServicesInternal et WebServicesExternal, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f8a90-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="f8a90-173">Dans l’invite de la ligne de commande Lync Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="f8a90-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="f8a90-174">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="f8a90-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="f8a90-175">À la place, vous devez utiliser le paramètre nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="f8a90-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="f8a90-176">Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le FQDN du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="f8a90-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="f8a90-177">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f8a90-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="f8a90-178">Pour un autre nom d’objet de découverte automatique externe manquant, sur la ligne de commande, tapez:</span><span class="sxs-lookup"><span data-stu-id="f8a90-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="f8a90-179">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="f8a90-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="f8a90-180">À la place, vous devez utiliser le paramètre nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="f8a90-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="f8a90-181">Lorsque vous utilisez le paramètre nom_domaine, vous devez utiliser un préfixe approprié pour le FQDN du domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="f8a90-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="f8a90-182">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f8a90-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="f8a90-183">Pour attribuer les types de certificats individuels, tapez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="f8a90-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="f8a90-184">Où «empreinte» est l’empreinte digitale affichée pour les certificats individuels émis.</span><span class="sxs-lookup"><span data-stu-id="f8a90-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

