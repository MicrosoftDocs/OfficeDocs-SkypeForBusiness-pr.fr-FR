---
title: 'Lync Server 2013 : résolution des problèmes dans le panneau de configuration Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87ad05798dab0f324a44a4c41807e8acb6105927
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="d1c72-102">Dépannage du panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c72-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c72-103">_**Dernière modification de la rubrique :** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d1c72-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d1c72-104">Cette rubrique fournit des informations et des procédures qui peuvent vous aider à résoudre les problèmes liés à l’accès au panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1c72-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="d1c72-105">Configuration requise du navigateur Internet</span><span class="sxs-lookup"><span data-stu-id="d1c72-105">Internet Browser Requirements</span></span>

<span data-ttu-id="d1c72-106">Le panneau de configuration Lync Server nécessite l’installation du plug-in de navigateur Microsoft Silverlight version 4.0.50524.0 ou de la dernière version.</span><span class="sxs-lookup"><span data-stu-id="d1c72-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="d1c72-107">Si Silverlight n’est pas installé ou si une version antérieure est installée, suivez les instructions du message pour installer la version requise.</span><span class="sxs-lookup"><span data-stu-id="d1c72-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1c72-108">La section autres logiciels requis pour le panneau de configuration Lync Server se rapporte au système d’exploitation sur lequel le panneau de configuration Lync Server et tous les autres outils d’administration Lync Server 2013 peuvent être installés.</span><span class="sxs-lookup"><span data-stu-id="d1c72-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="d1c72-109">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-server-and-tools-operating-system-support.md">serveur and Tools Operating System Support in Lync Server 2013</A> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d1c72-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="d1c72-110">Si votre navigateur Internet bloque l’installation de Silverlight en raison de considérations de sécurité, ajoutez l’URL (Uniform Resource Locator) qui ouvre le panneau de configuration Lync Server à la liste des sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="d1c72-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="d1c72-111">Dans les paramètres de sécurité d’Internet Explorer, vérifiez que **Exécuter les contrôles ActiveX et les plugins** est défini comme **Activé**.</span><span class="sxs-lookup"><span data-stu-id="d1c72-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="d1c72-112">Pour plus d’informations [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060), reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="d1c72-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="d1c72-113">De plus, vérifiez que le navigateur est configuré pour utiliser SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="d1c72-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="d1c72-p104">Si le navigateur Internet est configuré de sorte d’utiliser un serveur proxy, vérifiez qu’il est configuré pour contourner le serveur proxy pour les sites qui sont automatiquement détectés comme des sites internes. Vous pouvez aussi ajouter l’adresse à la liste d’exception du navigateur dans les paramètres de configuration du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="d1c72-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="d1c72-116">Spécifications des certificats et enregistrements DNS pour l’URL d’accès administratif</span><span class="sxs-lookup"><span data-stu-id="d1c72-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="d1c72-117">Si vous avez configuré une URL simple pour accéder au panneau de configuration Lync Server, vérifiez que vous avez également configuré l’enregistrement de ressource A (Domain Name System) statique et le certificat nécessaire à l’utilisation de cette URL d’accès administratif.</span><span class="sxs-lookup"><span data-stu-id="d1c72-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="d1c72-118">Si vous modifiez l’URL de base à tout moment, assurez-vous que la modification est reflétée dans l’enregistrement DNS et le certificat appropriés et que vous exécutez l' *CsComputer* sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="d1c72-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="d1c72-119">Pour des détails, consultez les rubriques suivantes dans la documentation de planification :</span><span class="sxs-lookup"><span data-stu-id="d1c72-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="d1c72-120">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c72-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="d1c72-121">Configuration DNS requise pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c72-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="d1c72-122">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c72-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="d1c72-123">Pour obtenir des procédures pas à pas sur la configuration de l’URL d’accès administratif, voir [modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d1c72-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="d1c72-124">Exigences relatives aux services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="d1c72-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="d1c72-125">Le panneau de configuration Lync Server est l’un des composants de Lync Server 2013 qui nécessitent Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d1c72-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="d1c72-126">Vérifiez en particulier que les fonctionnalités de redirection HTTP et d’authentification Windows sont activées, et que le service de publication World Wide Web (W3SVC) est exécuté.</span><span class="sxs-lookup"><span data-stu-id="d1c72-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="d1c72-127">Dépendance du service de publication World Wide Web (Service Windows)</span><span class="sxs-lookup"><span data-stu-id="d1c72-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="d1c72-128">Lorsque le service de publication sur le Web est arrêté, vous ne pouvez pas accéder au panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1c72-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="d1c72-129">Vous pouvez redémarrer le service en utilisant la console MMC (Microsoft Management Console) Services Windows.</span><span class="sxs-lookup"><span data-stu-id="d1c72-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="d1c72-130">**Pour démarrer le service de publication World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="d1c72-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="d1c72-131">Ouvrez une session sur l’ordinateur sur lequel le service de publication World World-Web est installé dans le cadre d’Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d1c72-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="d1c72-132">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Services**.</span><span class="sxs-lookup"><span data-stu-id="d1c72-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="d1c72-133">Cliquez avec le bouton droit sur le **Service de publication World Wide Web**, puis cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="d1c72-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="d1c72-134">Mode Pool d’applications</span><span class="sxs-lookup"><span data-stu-id="d1c72-134">Application Pool Mode</span></span>

<span data-ttu-id="d1c72-135">Configurez IIS de sorte que le pool d’applications CsManagementAppPool utilise le compte Service réseau pour son identité de modèle de processus.</span><span class="sxs-lookup"><span data-stu-id="d1c72-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="d1c72-136">Droits et autorisations de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="d1c72-136">User Rights and Permissions</span></span>

<span data-ttu-id="d1c72-137">Vous devez vous connecter au panneau de configuration Lync Server à l’aide d’un compte de domaine membre du groupe CsAdministrator ou à l’aide d’un compte auquel vous avez délégué des droits d’utilisateur et des autorisations.</span><span class="sxs-lookup"><span data-stu-id="d1c72-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="d1c72-138">Vous ne pouvez pas vous connecter au panneau de configuration Lync Server à l’aide d’un compte d’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d1c72-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="d1c72-139">Pour plus d’informations sur la délégation de tâches administratives via le contrôle d’accès basé sur un rôle (RBAC), voir [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d1c72-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="d1c72-140">Si vous utilisez une URL simple pour accéder au panneau de configuration Lync Server, vérifiez que les serveurs Web sont ajoutés aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="d1c72-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1c72-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1c72-141">See Also</span></span>


[<span data-ttu-id="d1c72-142">Outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c72-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

