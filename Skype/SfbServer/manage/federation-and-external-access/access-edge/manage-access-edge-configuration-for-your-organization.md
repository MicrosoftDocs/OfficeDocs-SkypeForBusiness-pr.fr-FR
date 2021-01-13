---
title: Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès de domaine ou de fournisseur externe, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817334"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="19a57-103">Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="19a57-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="19a57-104">Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès de domaine ou de fournisseur externe, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="19a57-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="19a57-105">Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès** :</span><span class="sxs-lookup"><span data-stu-id="19a57-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="19a57-106">**Activer la fédération et la connectivité DE MESSAGERIE INSTANTANÉE publique**   Activez-le si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="19a57-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="19a57-107">Ce paramètre s’applique à la fédération SIP configurée pour les étendues globale, de site ou utilisateur dans la page Stratégie **d’accès** externe.</span><span class="sxs-lookup"><span data-stu-id="19a57-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="19a57-108">Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.</span><span class="sxs-lookup"><span data-stu-id="19a57-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="19a57-109">Il existe deux options qui sont facultatives pour la façon dont les partenaires fédérés sont découverts et si les notifications d’exclusion de responsabilité d’archivage (notification aux contacts fédérés avec qui vous communiquez que l’archivage est activé dans votre déploiement et que les détails des communications seront archivés) seront envoyés aux contacts :</span><span class="sxs-lookup"><span data-stu-id="19a57-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="19a57-110">**Activer la découverte de domaine partenaire**   La sélection de cette option permet la découverte automatique des domaines avec qui vous pouvez vous fédérer.</span><span class="sxs-lookup"><span data-stu-id="19a57-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="19a57-111">Skype Entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines non répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés découverts et en limitant ou bloquant ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="19a57-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="19a57-112">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="19a57-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="19a57-113">Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="19a57-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="19a57-114">Pour plus d’informations, voir [Configurer la prise en charge des domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="19a57-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="19a57-115">**Envoyer une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés**   La sélection de cette option permet l’envoi d’un message de clause d’exclusion de responsabilité d’archivage aux partenaires fédérés qui les informe que les détails des communications sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="19a57-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="19a57-116">Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="19a57-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="19a57-117">Pour plus d’informations sur l’archivage, voir Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité [d’archivage au partenaire fédéré.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="19a57-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="19a57-118">**Activer l’accès des utilisateurs distants**   Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui sont en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs en déplacement, puissent se connecter à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="19a57-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="19a57-119">Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="19a57-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="19a57-120">**Permettre aux utilisateurs anonymes d’accéder aux conférences**   Activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs anonymes externes aux conférences qu’ils organisent.</span><span class="sxs-lookup"><span data-stu-id="19a57-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="19a57-121">Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences.</span><span class="sxs-lookup"><span data-stu-id="19a57-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="19a57-122">En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe ne soit disponible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19a57-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="19a57-123">Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir Gérer la stratégie d’accès [externe pour votre organisation.](../external-access-policies/manage-external-access-policy-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="19a57-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="19a57-124">**Affichage des informations de configuration du edge d’accès Windows PowerShell cmdlets**</span><span class="sxs-lookup"><span data-stu-id="19a57-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="19a57-125">Les informations de configuration du edge d’accès peuvent être vues à l’aide Windows PowerShell’une cmdlet **Get-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="19a57-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="19a57-126">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19a57-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="19a57-127">Pour afficher des informations sur tous vos paramètres de configuration du serveur Edge d’accès, tapez la commande suivante dans l’environnement de ligne de commande Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="19a57-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="19a57-128">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="19a57-128">That will return information similar to this:</span></span>
    
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

