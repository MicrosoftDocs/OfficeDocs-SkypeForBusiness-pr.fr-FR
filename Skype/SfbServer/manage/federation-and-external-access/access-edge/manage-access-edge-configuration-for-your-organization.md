---
title: Gestion de la configuration du serveur Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818345"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="2e11b-103">Gestion de la configuration du serveur Edge d’accès pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="2e11b-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="2e11b-104">Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2e11b-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="2e11b-105">Ces options incluent les types d’accès suivants qui peuvent être configurés par le biais de la page **configuration de Microsoft Edge** :</span><span class="sxs-lookup"><span data-stu-id="2e11b-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="2e11b-106">**Activer la connectivité**   de Fédération et de messagerie instantanée publique activez cette opération si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="2e11b-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="2e11b-107">Ce paramètre s’applique aux fédérations SIP configurées pour les étendues globales, de sites ou d’utilisateurs sur la page de **stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="2e11b-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="2e11b-108">Pour que les paramètres de Fédération s’appliquent, vous devez configurer la prise en charge de la Fédération sur les deux pages.</span><span class="sxs-lookup"><span data-stu-id="2e11b-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="2e11b-109">Il existe deux options qui sont des paramètres facultatifs pour la façon dont les partenaires fédérés sont détectés, et si les exclusions de responsabilité en matière d’archivage (notification à des contacts fédérés avec lesquels vous communiquez avec votre déploiement est activée et que les communications les détails seront archivés) seront envoyés aux contacts :</span><span class="sxs-lookup"><span data-stu-id="2e11b-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="2e11b-110">**Activer la découverte**   de domaine partenaire la sélection de cette option permet la découverte automatique des domaines avec lesquels vous pouvez être fédérer.</span><span class="sxs-lookup"><span data-stu-id="2e11b-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="2e11b-111">Skype entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant des partenaires fédérés détectés et en limitant ou en bloquant ce trafic en fonction de l’approbation. le niveau, le volume et les paramètres d’administration.</span><span class="sxs-lookup"><span data-stu-id="2e11b-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="2e11b-112">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="2e11b-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="2e11b-113">Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="2e11b-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="2e11b-114">Pour plus d’informations, voir [configurer la prise en charge des domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="2e11b-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="2e11b-115">**Envoyer un message d’exclusion d’archivage aux partenaires**   fédérés cette option permet d’envoyer un message d’exclusion d’archivage aux partenaires fédérés qui les recommandent que les détails des communications sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="2e11b-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="2e11b-116">Si vous archivez des communications externes avec des domaines partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité pour signaler aux partenaires que leurs messages et leurs coordonnées sont archivés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="2e11b-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="2e11b-117">Pour plus d’informations sur l’archivage, voir [activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage au partenaire fédéré](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="2e11b-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="2e11b-118">**Activer l’accès**   des utilisateurs distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, des télétravailleurs et des utilisateurs qui voyagent) puissent se connecter à Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2e11b-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="2e11b-119">Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2e11b-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="2e11b-120">**Permettre aux utilisateurs anonymes d’accéder aux conférences**   activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs externes anonymes à des conférences qu’ils organisent.</span><span class="sxs-lookup"><span data-stu-id="2e11b-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="2e11b-121">L’activation de ce paramètre n’autorise que les utilisateurs anonymes pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="2e11b-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="2e11b-122">Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous configurez également des stratégies pour contrôler l’utilisation des utilisateurs distants au sein de votre organisation avant d’avoir accès aux utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="2e11b-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="2e11b-123">Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès utilisateur externe, voir gérer les stratégies [d’accès externe pour votre organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="2e11b-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="2e11b-124">**Affichage des informations de configuration de bord d’accès à l’aide des cmdlets Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2e11b-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="2e11b-125">Les informations de configuration de Microsoft Edge peuvent être consultées à l’aide de Windows PowerShell et de l’applet **de passe Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2e11b-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="2e11b-126">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e11b-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="2e11b-127">Pour afficher des informations sur l’ensemble des paramètres de configuration de Edge Access, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="2e11b-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="2e11b-128">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="2e11b-128">That will return information similar to this:</span></span>
    
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

