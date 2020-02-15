---
title: 'Lync Server 2013 : configuration logicielle requise supplémentaire'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4eb8bb73a94ad9fb833aa2d44b0ce6c14447b9d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="fe22c-102">Configuration logicielle requise supplémentaire pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe22c-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe22c-103">_**Dernière modification de la rubrique :** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="fe22c-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="fe22c-104">Outre le matériel et le système d’exploitation requis pour les plateformes serveur, Lync Server 2013 nécessite l’installation de logiciels supplémentaires sur les serveurs que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="fe22c-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe22c-105">Pour plus d’informations sur la configuration requise pour la plateforme pour les serveurs exécutant Lync Server, consultez la rubrique <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A> et <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fe22c-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="fe22c-106">Pour plus d’informations sur la configuration système requise pour les ordinateurs clients et les périphériques, voir <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="fe22c-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="fe22c-107">Pour plus d’informations sur la configuration logicielle requise pour les outils d’administration, consultez la rubrique <A href="lync-server-2013-administrative-tools-software-requirements.md">configuration logicielle requise pour les outils d’administration dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fe22c-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="fe22c-108">Logiciels supplémentaires nécessaires pour tous les rôles serveur internes</span><span class="sxs-lookup"><span data-stu-id="fe22c-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="fe22c-109">Cette section répertorie les logiciels nécessaires sur tous les rôles serveur internes, qui sont tous les rôles serveur Lync Server, à l’exception du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="fe22c-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="fe22c-110">La configuration requise pour les serveurs Edge et les pools de serveurs Edge est indiquée plus loin dans cette rubrique sous **logiciels supplémentaires pour les serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="fe22c-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="fe22c-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="fe22c-112">La version correcte de Windows PowerShell 3,0 doit être installée sur chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="fe22c-113">Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="fe22c-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="fe22c-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="fe22c-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="fe22c-115">Lync Server requiert Microsoft .NET Framework 4,5 sur tous les rôles serveur internes et sur tout ordinateur sur lequel vous allez exécuter les outils d’administration Lync Server ou l’outil de planification Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="fe22c-116">Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="fe22c-117">Pour l’installer manuellement, téléchargez Microsoft .NET 4,5 Framework à partir du centre de téléchargement Microsoft à l’adresse[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="fe22c-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="fe22c-118">Installation de Microsoft .NET Framework 4,5 sur des serveurs exécutant Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fe22c-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="fe22c-119">Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs qui exécuteront Lync Server 2013 et Windows Server 2012, vous devez effectuer une étape supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fe22c-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="fe22c-120">Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.</span><span class="sxs-lookup"><span data-stu-id="fe22c-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="fe22c-121">**Pour installer .NET 4,5 HTTP activation sur Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="fe22c-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="fe22c-122">Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="fe22c-123">Dans le gestionnaire de serveur, sous **Résumé des fonctionnalités**, sélectionnez **Ajouter des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="fe22c-124">Développez **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="fe22c-125">Sélectionnez **activation WCF** si elle n’est pas déjà sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fe22c-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="fe22c-126">Ensuite, sélectionnez **activation http**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="fe22c-127">Cliquez sur **suivant** et suivez les invites pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="fe22c-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="fe22c-128">Windows Identity Foundation</span></span>

<span data-ttu-id="fe22c-129">**Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="fe22c-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="fe22c-130">Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="fe22c-131">Sélectionnez votre système d’exploitation serveur dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="fe22c-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="fe22c-132">Windows Server 2008 R2 pour Windows Server 2008 R2, vérifiez si elle a déjà été installée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fe22c-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="fe22c-133">Pour ce faire, accédez à **Ajout/suppression de programmes**, **Affichez les mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="fe22c-134">Pour plus d’informations sur l’installation de Windows [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Identity Foundation, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="fe22c-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="fe22c-135">Windows Server 2012 pour Windows Server 2012, vous utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="fe22c-136">Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="fe22c-137">Sélectionnez **Windows Identity Foundation 3,5** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="fe22c-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="fe22c-138">Cliquez sur **suivant**, puis sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="fe22c-139">Logiciels supplémentaires pour tous les serveurs frontaux et les serveurs Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fe22c-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="fe22c-140">Tous les serveurs frontaux et les serveurs Standard Edition Server doivent également exécuter les services Internet (IIS) avec certains modules.</span><span class="sxs-lookup"><span data-stu-id="fe22c-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="fe22c-141">De plus, tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences, les applications de parcage d’appel, les annonces ou les groupes Response Group doivent exécuter Windows Media Format Runtime.</span><span class="sxs-lookup"><span data-stu-id="fe22c-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="fe22c-142">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="fe22c-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="fe22c-143">Les serveurs frontaux et les serveurs Standard Edition Server doivent exécuter les services Internet (IIS), avec les modules suivants :</span><span class="sxs-lookup"><span data-stu-id="fe22c-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="fe22c-144">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="fe22c-144">Static Content</span></span>

  - <span data-ttu-id="fe22c-145">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="fe22c-145">Default Document</span></span>

  - <span data-ttu-id="fe22c-146">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="fe22c-146">HTTP Errors</span></span>

  - <span data-ttu-id="fe22c-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe22c-147">ASP.NET</span></span>

  - <span data-ttu-id="fe22c-148">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="fe22c-148">.NET Extensibility</span></span>

  - <span data-ttu-id="fe22c-149">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="fe22c-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="fe22c-150">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="fe22c-150">ISAPI Filters</span></span>

  - <span data-ttu-id="fe22c-151">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="fe22c-151">HTTP Logging</span></span>

  - <span data-ttu-id="fe22c-152">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="fe22c-152">Logging Tools</span></span>

  - <span data-ttu-id="fe22c-153">Analyzer</span><span class="sxs-lookup"><span data-stu-id="fe22c-153">Tracing</span></span>

  - <span data-ttu-id="fe22c-154">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="fe22c-154">Windows Authentication</span></span>

  - <span data-ttu-id="fe22c-155">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="fe22c-155">Request Filtering</span></span>

  - <span data-ttu-id="fe22c-156">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="fe22c-156">Static Content Compression</span></span>

  - <span data-ttu-id="fe22c-157">Compression du contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="fe22c-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="fe22c-158">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="fe22c-158">IIS Management Console</span></span>

  - <span data-ttu-id="fe22c-159">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="fe22c-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="fe22c-160">Authentification anonyme (installée par défaut lors de l’installation d’IIS.)</span><span class="sxs-lookup"><span data-stu-id="fe22c-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="fe22c-161">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="fe22c-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="fe22c-162">Windows Media Format Runtime et expérience de bureau Windows</span><span class="sxs-lookup"><span data-stu-id="fe22c-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="fe22c-163">**Expérience de bureau Windows** Tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences seront déployées doivent avoir installé le runtime de format Windows Media, qui, à l’exception de Windows Server 2012, est installé dans le cadre de l’expérience de bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="fe22c-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="fe22c-164">Windows Server 2012 nécessite Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="fe22c-165">Le module d’exécution du format Windows Media est nécessaire pour exécuter les fichiers audio Windows Media (.wma) qui sont lus pour les annonces et la musique par les applications de parcage d’appel, d’annonce et Response Group.</span><span class="sxs-lookup"><span data-stu-id="fe22c-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="fe22c-166">Nous vous recommandons d’installer expérience Bureau Windows avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="fe22c-167">Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, il vous invite à l’installer, puis vous devez redémarrer le serveur pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="fe22c-168">Logiciels supplémentaires pour les serveurs frontaux et les serveurs Standard Edition s’exécutant sur Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fe22c-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="fe22c-169">Les serveurs frontaux nécessitent .NET 3,5, qui n’est pas installé par défaut sur Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fe22c-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="fe22c-170">Pour l’installer, placez le support d’installation de Windows Server 2012 dans le lecteur D, puis tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fe22c-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="fe22c-171">Pour plus d’informations sur l’installation de .NET 3,5 sur des serveurs exécutant Windows Server 2012, voir « considérations pour le <https://go.microsoft.com/fwlink/p/?linkid=275032>déploiement de Microsoft .net Framework 3,5 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="fe22c-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="fe22c-172">Logiciels supplémentaires pour les directeurs</span><span class="sxs-lookup"><span data-stu-id="fe22c-172">Additional Software for Directors</span></span>

<span data-ttu-id="fe22c-173">Les directeurs doivent exécuter les services Internet (IIS), avec les modules suivants :</span><span class="sxs-lookup"><span data-stu-id="fe22c-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="fe22c-174">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="fe22c-174">Static Content</span></span>

  - <span data-ttu-id="fe22c-175">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="fe22c-175">Default Document</span></span>

  - <span data-ttu-id="fe22c-176">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="fe22c-176">HTTP Errors</span></span>

  - <span data-ttu-id="fe22c-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe22c-177">ASP.NET</span></span>

  - <span data-ttu-id="fe22c-178">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="fe22c-178">.NET Extensibility</span></span>

  - <span data-ttu-id="fe22c-179">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="fe22c-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="fe22c-180">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="fe22c-180">ISAPI Filters</span></span>

  - <span data-ttu-id="fe22c-181">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="fe22c-181">HTTP Logging</span></span>

  - <span data-ttu-id="fe22c-182">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="fe22c-182">Logging Tools</span></span>

  - <span data-ttu-id="fe22c-183">Analyzer</span><span class="sxs-lookup"><span data-stu-id="fe22c-183">Tracing</span></span>

  - <span data-ttu-id="fe22c-184">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="fe22c-184">Windows Authentication</span></span>

  - <span data-ttu-id="fe22c-185">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="fe22c-185">Request Filtering</span></span>

  - <span data-ttu-id="fe22c-186">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="fe22c-186">Static Content Compression</span></span>

  - <span data-ttu-id="fe22c-187">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="fe22c-187">IIS Management Console</span></span>

  - <span data-ttu-id="fe22c-188">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="fe22c-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="fe22c-189">Authentification anonyme (installée par défaut à l’installation d’IIS).</span><span class="sxs-lookup"><span data-stu-id="fe22c-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="fe22c-190">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="fe22c-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="fe22c-191">Logiciels supplémentaires pour les serveurs frontaux de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fe22c-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="fe22c-192">Les serveurs frontaux de conversation permanente doivent exécuter Message Queuing (également appelé MSMQ), qui est un composant de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fe22c-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="fe22c-193">Pour plus d’informations sur l’activation de MSMQ, [cliquez ici.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe22c-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="fe22c-194">Logiciels supplémentaires pour les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="fe22c-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="fe22c-195">Les serveurs Edge requièrent les logiciels suivants :</span><span class="sxs-lookup"><span data-stu-id="fe22c-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="fe22c-196">La version correcte de Windows PowerShell 3,0 doit être installée sur chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="fe22c-197">Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="fe22c-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="fe22c-198">Lync Server requiert Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="fe22c-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="fe22c-199">Pour Lync Server 2013 installé sur Windows Server 2008 R2, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe22c-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="fe22c-200">Pour l’installer manuellement, téléchargez Microsoft .NET 4,5 Framework à partir du centre de téléchargement Microsoft à l’adresse[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="fe22c-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="fe22c-201">**Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="fe22c-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="fe22c-202">Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="fe22c-203">Sélectionnez votre système d’exploitation serveur dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="fe22c-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="fe22c-204">Windows Server 2008 R2 pour Windows Server 2008 R2, vérifiez si elle a déjà été installée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fe22c-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="fe22c-205">Pour ce faire, accédez à **Ajout/suppression de programmes**, **Affichez les mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="fe22c-206">Pour plus d’informations sur l’installation de Windows [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Identity Foundation, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="fe22c-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="fe22c-207">Windows Server 2012 pour Windows Server 2012, vous utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="fe22c-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="fe22c-208">Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="fe22c-209">Sélectionnez **Windows Identity Foundation 3,5** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="fe22c-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="fe22c-210">Cliquez sur **suivant**, puis sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="fe22c-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="fe22c-211">N’installez pas les LSP (Layered Socket Provider) sur les serveurs multimédias</span><span class="sxs-lookup"><span data-stu-id="fe22c-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="fe22c-212">N’installez pas de logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ni aucun autre logiciel de fournisseurs de services en couche (LSP) Winsock, sur un serveur frontal ou un serveur de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="fe22c-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="fe22c-213">L’installation de ce logiciel pourrait entraîner des performances de trafic multimédia médiocres.</span><span class="sxs-lookup"><span data-stu-id="fe22c-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe22c-214">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe22c-214">See Also</span></span>


[<span data-ttu-id="fe22c-215">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe22c-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

