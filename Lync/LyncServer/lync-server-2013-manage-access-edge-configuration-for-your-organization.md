---
title: 'Lync Server 2013 : Gestion de la configuration du serveur Edge d’accès pour votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4739599f92b9189a208e1bb320a53b82d66a3a9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="955be-102">Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="955be-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="955be-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="955be-104">Il s’agit d’une documentation préliminaire susceptible d’être modifiée.</span><span class="sxs-lookup"><span data-stu-id="955be-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="955be-105">Des rubriques vides sont incluses sous forme d’espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="955be-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="955be-106">Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="955be-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="955be-107">Ces options incluent les types d’accès suivants qui peuvent être configurés par le biais de la page **configuration de Microsoft Edge** :</span><span class="sxs-lookup"><span data-stu-id="955be-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="955be-108">**Activer la connectivité**   de Fédération et de messagerie instantanée publique activez cette opération si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="955be-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="955be-109">Ce paramètre s’applique aussi bien aux fédérations SIP et XMPP qu’aux fédérations qui sont configurées pour les étendues de site ou d’utilisateur globales sur la page de **stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="955be-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="955be-110">Pour que les paramètres de Fédération s’appliquent, vous devez configurer la prise en charge de la Fédération sur les deux pages.</span><span class="sxs-lookup"><span data-stu-id="955be-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="955be-111">Il existe deux options qui sont des paramètres facultatifs pour la façon dont les partenaires fédérés sont détectés, et si les exclusions de responsabilité en matière d’archivage (notification à des contacts fédérés avec lesquels vous communiquez avec votre déploiement est activée et que les communications les détails seront archivés) seront envoyés aux contacts</span><span class="sxs-lookup"><span data-stu-id="955be-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="955be-112">**Activer la découverte**   de domaine partenaire la sélection de cette option permet la découverte automatique des domaines avec lesquels vous pouvez être fédérer.</span><span class="sxs-lookup"><span data-stu-id="955be-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="955be-113">Lync Server 2013 utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés identifiés et en limitant ou en bloquant ce trafic en fonction du niveau de confiance. le volume et les paramètres d’administration.</span><span class="sxs-lookup"><span data-stu-id="955be-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="955be-114">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="955be-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="955be-115">Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="955be-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="955be-116">Pour plus d’informations, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="955be-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="955be-117">**Envoyer un message d’exclusion d’archivage aux partenaires**   fédérés cette option permet d’envoyer un message d’exclusion d’archivage aux partenaires fédérés qui les recommandent que les détails des communications sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="955be-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="955be-118">Si vous archivez des communications externes avec des domaines partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité pour signaler aux partenaires que leurs messages et leurs coordonnées sont archivés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="955be-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="955be-119">Pour plus d’informations sur l’archivage, voir [définir vos exigences d’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="955be-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="955be-120">**Activer l’accès**   des utilisateurs distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, des télétravailleurs et des utilisateurs qui voyagent) puissent se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="955be-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="955be-121">Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="955be-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="955be-122">**Permettre aux utilisateurs anonymes d’accéder aux conférences**   activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs externes anonymes à des conférences qu’ils organisent.</span><span class="sxs-lookup"><span data-stu-id="955be-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="955be-123">L’activation de ce paramètre n’autorise que les utilisateurs anonymes pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="955be-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="955be-124">Pour configurer l’utilisation des conférences et les options qui déterminent la façon dont les utilisateurs peuvent effectuer des conférences et l’inclusion d’utilisateurs anonymes, reportez-vous aux détails de la rubrique [créer ou modifier l’interface utilisateur des conférences pour un site ou des utilisateurs](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) et des [paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="955be-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="955be-125">Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous configurez également des stratégies pour contrôler l’utilisation des utilisateurs distants au sein de votre organisation avant d’avoir accès aux utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="955be-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="955be-126">Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès utilisateur externe, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gérer une stratégie d’accès externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="955be-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="955be-127">**Affichage des informations de configuration de bord d’accès à l’aide des cmdlets Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="955be-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="955be-128">Les informations de configuration de Microsoft Edge peuvent être consultées à l’aide de Windows PowerShell et de l’applet **de passe Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="955be-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="955be-129">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="955be-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="955be-130">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="955be-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="955be-131">Pour afficher des informations sur l’ensemble des paramètres de configuration de Microsoft Edge, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="955be-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="955be-132">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="955be-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="955be-133">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="955be-133">In This Section</span></span>

  - [<span data-ttu-id="955be-134">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="955be-135">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="955be-136">Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="955be-137">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="955be-138">Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="955be-139">Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955be-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

