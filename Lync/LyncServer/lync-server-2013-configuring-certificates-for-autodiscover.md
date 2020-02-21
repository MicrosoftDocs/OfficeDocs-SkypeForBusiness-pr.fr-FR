---
title: 'Lync Server 2013 : configuration des certificats pour la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d414a998fcce0f68186fbf9a6e42d6075dfb991c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="57b31-102">Configuration de certificats pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57b31-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57b31-103">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="57b31-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="57b31-104">Les certificats de votre pool Directeur, de votre pool frontal et de votre proxy inverse requièrent des entrées de l’autre nom de l’objet pour prendre en charge les connexions sécurisées avec les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="57b31-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57b31-105">Vous pouvez utiliser l’applet de commande <STRONG>Get-CsCertificate</STRONG> pour afficher des informations sur les certificats actuellement affectés.</span><span class="sxs-lookup"><span data-stu-id="57b31-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="57b31-106">Toutefois, l’affichage par défaut tronque les propriétés du certificat et n’affiche pas toutes les valeurs de la propriété SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="57b31-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="57b31-107">Vous pouvez utiliser les applets de commande <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate et <STRONG>Set-CsCertificate</STRONG> pour afficher certaines informations, ainsi que pour demander et affecter des certificats.</span><span class="sxs-lookup"><span data-stu-id="57b31-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="57b31-108">Cependant, ce n’est pas la meilleure méthode à utiliser si vous n’êtes pas sûr des propriétés des autres noms de l’objet (SAN) pour le certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="57b31-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="57b31-109">Pour afficher le certificat et tous les membres de propriété, il est recommandé d’utiliser le composant logiciel enfichable Certificats de la <EM>console MMC (Microsoft Management Console)</EM> ou d’utiliser l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57b31-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="57b31-110">Dans l’Assistant Déploiement Lync Server, vous pouvez utiliser l’Assistant Certificat pour afficher les propriétés du certificat.</span><span class="sxs-lookup"><span data-stu-id="57b31-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="57b31-111">Les procédures permettant d’afficher, de demander et d’affecter un certificat à l’aide de Lync Server Management Shell et de la <EM>console MMC (Microsoft Management Console)</EM> sont détaillées dans les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="57b31-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="57b31-112">Pour utiliser l’Assistant Déploiement de Lync Server, consultez les détails ici si vous avez déployé le pool facultatif Director ou Director : <A href="lync-server-2013-configure-certificates-for-the-director.md">configurez les certificats pour le directeur dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57b31-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="57b31-113">Pour le serveur frontal ou le pool frontal, consultez les informations ci-dessous : <A href="lync-server-2013-configure-certificates-for-servers.md">configure Certificates for Servers in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57b31-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="57b31-114">Les étapes initiales de cette procédure sont des étapes de préparation qui vous orientent vers le rôle des certificats actuels.</span><span class="sxs-lookup"><span data-stu-id="57b31-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="57b31-115">Par défaut, les certificats n’ont pas de lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;entrée de nom&gt; de domaine interne, sauf si vous avez déjà installé des services de mobilité ou si vous avez préparé vos certificats à l’avance.</span><span class="sxs-lookup"><span data-stu-id="57b31-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="57b31-116">Cette procédure utilise l’exemple de nom de domaine SIP « contoso.com » et l’exemple de nom de domaine interne « contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="57b31-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="57b31-117">La configuration de certificat par défaut pour Lync Server 2013 et Lync Server 2010 consiste à utiliser un certificat unique (nommé « Default ») avec les rôles par défaut (pour tous les rôles, à l’exception des services Web), WebServicesExternal et WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="57b31-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="57b31-118">La configuration facultative consiste à utiliser des certificats distincts pour chaque finalité.</span><span class="sxs-lookup"><span data-stu-id="57b31-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="57b31-119">Les certificats peuvent être gérés à l’aide des applets de commande Lync Server Management Shell et Windows PowerShell, ou à l’aide de l’Assistant certificat de l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57b31-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="57b31-120">Pour mettre à jour les certificats avec de nouveaux noms de sujet alternatifs à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="57b31-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="57b31-121">Ouvrez une session sur l’ordinateur à l’aide d’un compte disposant de droits et d’autorisations d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="57b31-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="57b31-122">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="57b31-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="57b31-p104">Déterminez les certificats qui ont été assignés au serveur et pour quel type d’utilisation. Vous aurez besoin de ces informations lors de l’étape suivante afin d’assigner le certificat mis à jour. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="57b31-p105">Examinez la sortie de l’étape précédente pour déterminer si un même certificat est assigné à plusieurs utilisations ou si un certificat différent est assigné à chaque utilisation. Observez le paramètre Use pour savoir comment un certificat est utilisé. Comparez le paramètre Thumbprint des certificats affichés pour savoir si le même certificat a plusieurs utilisations.</span><span class="sxs-lookup"><span data-stu-id="57b31-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="57b31-p106">Mettez à jour le certificat. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="57b31-131">Par exemple, si l’applet de commande **Get-CsCertificate** affichait un certificat avec comme utilisation « Default », un autre avec comme utilisation « WebServicesInternal  et un autre avec comme utilisation « WebServicesExternal » et que tous avaient la même valeur Thumbprint, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="57b31-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="57b31-132">**Important :**</span><span class="sxs-lookup"><span data-stu-id="57b31-132">**Important:**</span></span>
    
    <span data-ttu-id="57b31-133">Si un certificat différent est assigné pour chaque utilisation (la valeur de Thumbprint est différent pour chaque certificat), il ne faut surtout pas exécuter l’applet de commande **Set-CsCertificate** avec plusieurs types.</span><span class="sxs-lookup"><span data-stu-id="57b31-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="57b31-134">Exécutez plutôt l’applet de commande **Set-CsCertificate** séparément pour chaque utilisation.</span><span class="sxs-lookup"><span data-stu-id="57b31-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="57b31-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="57b31-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="57b31-p108">Pour afficher le certificat, cliquez sur **Démarrer**, puis sur **Exécuter**. Tapez MMC pour ouvrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="57b31-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="57b31-p109">Dans le menu de Microsoft Management Console, sélectionnez **Fichier**, **Ajouter/Supprimer un composant logiciel enfichable**, puis Certificats. Cliquez sur **Ajouter**. Quand vous y êtes invité, sélectionnez **Compte d’ordinateur**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="57b31-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="57b31-141">Si le certificat se trouve sur cet ordinateur, sélectionnez **ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="57b31-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="57b31-142">Si le certificat se trouve sur un autre ordinateur, sélectionnez **un autre ordinateur**, tapez le nom de domaine complet de l’ordinateur ou cliquez sur **Parcourir** dans **Entrez le nom de l’objet à sélectionner**, tapez le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="57b31-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="57b31-143">Cliquez sur **Vérifier les noms**.</span><span class="sxs-lookup"><span data-stu-id="57b31-143">Click **Check Names**.</span></span> <span data-ttu-id="57b31-144">Lorsque le nom de l’ordinateur est résolu, il est souligné.</span><span class="sxs-lookup"><span data-stu-id="57b31-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="57b31-145">Cliquez sur **OK**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="57b31-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="57b31-146">Cliquez sur **OK** pour valider la sélection et fermer la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** .</span><span class="sxs-lookup"><span data-stu-id="57b31-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="57b31-147">Si le certificat ne s’affiche pas dans la console, vérifiez que vous n’avez pas sélectionné utilisateur ou service.</span><span class="sxs-lookup"><span data-stu-id="57b31-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="57b31-148">Vous devez sélectionner ordinateur, sinon vous ne pourrez pas localiser le certificat probper.</span><span class="sxs-lookup"><span data-stu-id="57b31-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="57b31-p112">Pour afficher les propriétés du certificat, développez **Certificats**, développez **Personnel**, puis sélectionnez **Certificats**. Sélectionnez le certificat à afficher, cliquez avec le bouton droit sur le certificat, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="57b31-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="57b31-p113">Dans l’affichage **Certificat**, sélectionnez **Détails**. Vous pouvez ensuite sélectionner le nom d’objet du certificat en sélectionnant **Sujet** afin d’afficher le nom affecté et les propriétés associées.</span><span class="sxs-lookup"><span data-stu-id="57b31-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="57b31-153">Pour afficher les autres noms de l’objet affectés, sélectionnez **Autre nom de l’objet**.</span><span class="sxs-lookup"><span data-stu-id="57b31-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="57b31-154">Tous les autres noms de l’objet affectés sont affichés.</span><span class="sxs-lookup"><span data-stu-id="57b31-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="57b31-155">Les autres noms de l’objet présents dans la propriété sont de type **Nom DNS** par défaut.</span><span class="sxs-lookup"><span data-stu-id="57b31-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="57b31-156">Vous devriez voir les membres suivants (tous devraient correspondre à des noms de domaine complets tels qu’ils sont représentés dans les enregistrements d’hôte DNS, à savoir A ou AAAA si IPv6 est en vigueur) :</span><span class="sxs-lookup"><span data-stu-id="57b31-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="57b31-157">Nom de pool de ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool.</span><span class="sxs-lookup"><span data-stu-id="57b31-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="57b31-158">Nom du serveur auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="57b31-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="57b31-159">Enregistrements d’URL simples, généralement meet et dialin.</span><span class="sxs-lookup"><span data-stu-id="57b31-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="57b31-160">Noms externes des services Web et des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web remplacés.</span><span class="sxs-lookup"><span data-stu-id="57b31-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="57b31-161">S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="57b31-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="57b31-162">Le dernier élément est celui qui vous intéresse le plus (s’il existe une entrée d’autre nom de l’objet lyncdiscover et lyncdiscoverinternal).</span><span class="sxs-lookup"><span data-stu-id="57b31-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="57b31-163">Une fois que vous avez ces informations, vous pouvez fermer l’affichage du certificat et MMC.</span><span class="sxs-lookup"><span data-stu-id="57b31-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="57b31-164">Si un service de découverte automatique, c’est-à-dire le lyncdiscover. \>nom\> de domaine et lyncdiscoverinternal. \<nom\> de domaine (basé sur s’il s’agit d’un certificat interne ou externe) le autre nom de l’objet est manquant et vous utilisez un seul certificat par défaut pour les types par défaut, WebServicesInternal et WebServiceExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="57b31-165">À l’invite de ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="57b31-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="57b31-166">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="57b31-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="57b31-167">À la place, vous devez utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="57b31-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="57b31-168">Quand vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet des enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="57b31-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="57b31-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="57b31-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="57b31-170">Pour affecter le certificat, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="57b31-171">Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour le certificat qui vient d’être émis.</span><span class="sxs-lookup"><span data-stu-id="57b31-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="57b31-172">S’il manque d’autres noms de l’objet pour la découverte automatique interne quand vous utilisez des certificats distincts pour les types Default, WebServicesInternal et WebServicesExternal, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="57b31-173">À l’invite de ligne de commande Lync Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="57b31-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="57b31-p116">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez ce paramètre, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="57b31-p116">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="57b31-178">Pour un autre nom de sujet du service de découverte automatique externe manquant, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="57b31-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="57b31-p117">Si vous avez de nombreux domaines SIP, vous ne pouvez pas utiliser le nouveau paramètre AllSipDomain. Au lieu de cela, vous devez utiliser le paramètre DomainName. Lorsque vous utilisez ce paramètre, vous devez utiliser un préfixe approprié pour le nom de domaine complet du domaine SIP. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="57b31-p117">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="57b31-183">Pour affecter les types de certificat individuel, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="57b31-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="57b31-184">Où « Thumbprint » est l’empreinte numérique (Thumbprint) affichée pour les certificats individuels qui viennent d’être émis.</span><span class="sxs-lookup"><span data-stu-id="57b31-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

