---
title: Gestion de la configuration du serveur Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types de domaine externe ou fournisseur l’accès, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs de périphérie qui sera prise en charge pour votre organisation.
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199919"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="19084-103">Gestion de la configuration du serveur Edge d’accès pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="19084-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="19084-104">Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types de domaine externe ou fournisseur l’accès, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs de périphérie qui sera prise en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="19084-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="19084-105">Ces options comprennent les types d’accès qui peuvent être configurés par le biais de la page **Configuration du serveur Edge d’accès** suivants :</span><span class="sxs-lookup"><span data-stu-id="19084-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="19084-106">**Activer la fédération et la connectivité PIC**   activez-le si vous souhaitez prendre en charge de l’accès des utilisateurs aux domaines de partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="19084-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="19084-107">Ce paramètre s’applique aux SIP fédération configurée pour globale, site ou utilisateur étendues dans la page **Stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="19084-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="19084-108">Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.</span><span class="sxs-lookup"><span data-stu-id="19084-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="19084-109">Il existe deux options qui sont des paramètres facultatifs pour les partenaires fédérés sont découverts et si l’archivage des notifications d’exclusion (notification par les contacts fédérés avec lesquelles vous communiquez que votre déploiement a l’archivage activé et que les communications plus d’informations seront archivées) sont envoyés à des contacts :</span><span class="sxs-lookup"><span data-stu-id="19084-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="19084-110">**Activer la découverte du domaine partenaire**   cette option permet la découverte automatique des domaines que vous pouvez vous fédérer avec.</span><span class="sxs-lookup"><span data-stu-id="19084-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="19084-111">Skype pour Business Server utilise les enregistrements de nom de domaine DNS (Domain Name System) pour tenter de découvrir les domaines non répertoriés dans la liste des domaines autorisés, évaluer le trafic entrant provenant des partenaires fédérés découverts automatiquement et limitant ou bloquer ce trafic en fonction de gestion de la confidentialité niveau, la quantité de trafic et les paramètres de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="19084-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="19084-112">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activée uniquement pour les utilisateurs dans les domaines que vous incluez dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="19084-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="19084-113">Si vous sélectionnez cette option, vous pouvez spécifier cette personne domaines à être bloquée ou autorisée, y compris la restriction de l’accès à un serveur spécifique exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="19084-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="19084-114">Pour plus d’informations, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="19084-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="19084-115">**Envoyer la notification d’exclusion d’archivage aux partenaires fédérés**   cette option permet l’envoi d’un message de notification d’exclusion d’archivage aux partenaires fédérés leur indiquant que les détails de communication sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="19084-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="19084-116">Si vous archivez les communications externes avec les domaines de partenaire fédéré, vous devez activer la notification d’exclusion relative d’archivage prévenir vos partenaires que leurs détails communications et les messages sont archivés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="19084-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="19084-117">Pour plus d’informations sur l’archivage, voir [Activer ou désactiver l’envoi d’une notification d’exclusion d’archivage partenaire fédéré](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="19084-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="19084-118">**Activer l’accès des utilisateurs distants**   activer cette option si vous souhaitez que les utilisateurs situés en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, pour être en mesure de se connecter à Skype pour Business Server dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="19084-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="19084-119">Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="19084-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="19084-120">**Permettre aux utilisateurs anonymes d’accéder aux conférences**   activer cette option si vous souhaitez que les utilisateurs internes d’inviter des utilisateurs anonymes externes aux conférences qu’ils organisent.</span><span class="sxs-lookup"><span data-stu-id="19084-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="19084-121">L’activation de ce paramètre permet uniquement aux utilisateurs anonymes pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="19084-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="19084-122">Outre l’activation de l’accès des utilisateurs externes prennent en charge, vous également configurez des stratégies de contrôle de l’utilisation de l’accès des utilisateurs distants de votre organisation avant de n’importe quel type d’accès des utilisateurs externes est accessible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19084-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="19084-123">Pour plus d’informations sur la création, la configuration et l’application des stratégies pour l’accès des utilisateurs externes, voir [Gérer la stratégie de l’accès externe pour votre organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="19084-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="19084-124">**Affichage des informations de configuration de serveur Edge d’accès à l’aide des applets de commande Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="19084-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="19084-125">Accéder aux informations de configuration Edge peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="19084-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="19084-126">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19084-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="19084-127">Pour afficher des informations sur tous vos paramètres de configuration de serveur Edge d’accès, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="19084-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="19084-128">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="19084-128">That will return information similar to this:</span></span>
    
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

