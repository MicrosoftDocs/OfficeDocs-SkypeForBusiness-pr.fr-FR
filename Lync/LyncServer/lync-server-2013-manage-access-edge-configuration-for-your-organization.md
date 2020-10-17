---
title: 'Lync Server 2013 : gestion de la configuration du serveur Edge d’accès pour votre organisation'
description: 'Lync Server 2013 : gestion de la configuration du serveur Edge d’accès pour votre organisation.'
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
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550640"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="fec4f-103">Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-103">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec4f-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fec4f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fec4f-105">Cette documentation est préliminaire et sujette à modification.</span><span class="sxs-lookup"><span data-stu-id="fec4f-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="fec4f-106">Des rubriques vides sont incluses comme espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="fec4f-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="fec4f-107">Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès au domaine externe ou au fournisseur, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fec4f-107">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="fec4f-108">Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès** :</span><span class="sxs-lookup"><span data-stu-id="fec4f-108">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="fec4f-109">**Activer la Fédération et la connectivité PIC**     Activez-le si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="fec4f-109">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="fec4f-110">Cette option s’applique à la fédération SIP et à la fédération XMPP configurées globalement, pour un site ou un utilisateur dans la page **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="fec4f-110">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="fec4f-111">Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.</span><span class="sxs-lookup"><span data-stu-id="fec4f-111">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="fec4f-112">Il existe deux options facultatives concernant le mode de découverte des partenaires fédérés et l’envoi ou non d’une notification d’exclusion (notification indiquant aux contacts fédérés, avec lesquels vous communiquez, que l’archivage est activé sur votre déploiement et que les détails des communications seront archivés) aux contacts</span><span class="sxs-lookup"><span data-stu-id="fec4f-112">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="fec4f-113">**Activer la découverte**     du domaine partenaire La sélection de cette option active la découverte automatique des domaines avec lesquels vous pouvez fédérer.</span><span class="sxs-lookup"><span data-stu-id="fec4f-113">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="fec4f-114">Lync Server 2013 utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant en provenance des partenaires fédérés découverts et en limitant ou bloquant le trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="fec4f-114">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="fec4f-115">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="fec4f-115">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="fec4f-116">Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="fec4f-116">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="fec4f-117">Pour plus d’informations, reportez-vous à la rubrique [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="fec4f-117">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="fec4f-118">**Envoyer la clause d’exclusion de responsabilité d’archivage aux partenaires fédérés**     La sélection de cette option permet d’envoyer un message de notification d’exclusion d’archivage aux partenaires fédérés qui les avertit que les communications sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="fec4f-118">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="fec4f-119">Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="fec4f-119">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="fec4f-120">Pour plus d’informations sur l’archivage, reportez-vous à [la rubrique définition de la configuration requise pour l’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="fec4f-120">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="fec4f-121">**Activer l’accès**     des utilisateurs distants Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, puissent se connecter à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fec4f-121">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="fec4f-122">Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="fec4f-122">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="fec4f-123">**Autoriser les utilisateurs anonymes à accéder aux conférences**     Activez cette option si vous souhaitez que les utilisateurs internes invitent les utilisateurs anonymes externes à des conférences qu’ils organisent.</span><span class="sxs-lookup"><span data-stu-id="fec4f-123">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="fec4f-124">Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences.</span><span class="sxs-lookup"><span data-stu-id="fec4f-124">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="fec4f-125">Pour configurer l’expérience de conférence et les options qui définissent comment et ce que vos utilisateurs peuvent faire avec des conférences et pour l’inclusion des utilisateurs anonymes, consultez les détails de la rubrique [créer ou modifier l’expérience utilisateur de conférence pour un site ou des utilisateurs](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) et des [paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fec4f-125">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec4f-126">En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe ne soit disponible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fec4f-126">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="fec4f-127">Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestion de la stratégie d’accès externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fec4f-127">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fec4f-128">**Affichage des informations de configuration du serveur Edge d’accès à l’aide des applets de commande Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fec4f-128">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="fec4f-129">Les informations de configuration du serveur Edge d’accès peuvent être affichées à l’aide de Windows PowerShell et de la cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fec4f-129">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="fec4f-130">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fec4f-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fec4f-131">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="fec4f-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="fec4f-132">Pour afficher des informations sur tous les paramètres de configuration du serveur Edge d’accès, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="fec4f-132">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="fec4f-133">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fec4f-133">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="fec4f-134">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="fec4f-134">In This Section</span></span>

  - [<span data-ttu-id="fec4f-135">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-135">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="fec4f-136">Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-136">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="fec4f-137">Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-137">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="fec4f-138">Activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-138">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="fec4f-139">Activer ou désactiver l’accès des utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-139">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="fec4f-140">Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fec4f-140">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

