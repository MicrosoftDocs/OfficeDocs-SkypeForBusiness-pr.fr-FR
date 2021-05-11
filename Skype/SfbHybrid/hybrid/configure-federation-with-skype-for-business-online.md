---
title: Configurer Skype Entreprise hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305968"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="a68c7-103">Configurer Skype Entreprise hybride</span><span class="sxs-lookup"><span data-stu-id="a68c7-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="a68c7-104">Pour configurer Skype Entreprise hybride, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a68c7-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="a68c7-105">[Configurez votre service Edge local](#configure-your-on-premises-edge-service-to-federate-with-teams)pour la fédération avec Teams .</span><span class="sxs-lookup"><span data-stu-id="a68c7-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="a68c7-106">[Configurez votre environnement local pour qu’il Teams et activez l’espace d’adressan SIP partagé.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)</span><span class="sxs-lookup"><span data-stu-id="a68c7-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="a68c7-107">[Activez l’espace d’adressa ment SIP](#enable-shared-sip-address-space-in-your-organization)partagé dans Teams organisation.</span><span class="sxs-lookup"><span data-stu-id="a68c7-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="a68c7-108">Si vous avez Exchange local, vous pouvez configurer OAuth entre vos environnements Exchange local et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="a68c7-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="a68c7-109">Pour plus d’informations, voir Gérer l’authentification de serveur à serveur dans [Skype Entreprise Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) et planifier l’intégration Skype Entreprise [et Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="a68c7-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="a68c7-110">Configurer votre service Edge local pour la fédération avec Teams</span><span class="sxs-lookup"><span data-stu-id="a68c7-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="a68c7-111">La fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs Teams et Skype Entreprise Online de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a68c7-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="a68c7-112">Pour configurer la fédération, exécutez la cmdlet suivante dans l’Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a68c7-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="a68c7-113">Si la valeur « -EnablePartnerDiscovery » est définie sur $True, Skype Entreprise Server utilise les enregistrements DNS pour essayer de découvrir les domaines partenaires non répertoriés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="a68c7-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="a68c7-114">Si la valeur est définie sur $False , Skype Entreprise Server fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="a68c7-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="a68c7-115">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="a68c7-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="a68c7-116">Pour plus d’informations sur l’activation de la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’une organisation Microsoft 365, voir Configuration de la prise en charge de la fédération pour un client Microsoft 365 dans [Skype Entreprise Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span><span class="sxs-lookup"><span data-stu-id="a68c7-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="a68c7-117">Configurez votre environnement local pour activer l’espace d’adressan SIP partagé avec Teams</span><span class="sxs-lookup"><span data-stu-id="a68c7-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="a68c7-118">Vous devez également configurer votre environnement local pour qu’il soit Teams et activer l’espace d’adressan SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="a68c7-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="a68c7-119">Cette configuration signifie que Teams peut potentiellement héberger des comptes d’utilisateur pour le même ensemble de domaines SIP que votre environnement local, et que les messages peuvent être acheminés entre les utilisateurs hébergés sur site et en ligne.</span><span class="sxs-lookup"><span data-stu-id="a68c7-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="a68c7-120">Vous configurez un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a68c7-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="a68c7-121">Tout d’abord, vérifiez si vous avez déjà un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a68c7-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="a68c7-122">S’il en existe un, supprimez-le à l’aide de la commande suivante dans Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a68c7-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="a68c7-123">Créez ensuite un fournisseur d’hébergement à l’aide New-CsHostingProvider cmdlet comme suit :</span><span class="sxs-lookup"><span data-stu-id="a68c7-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="a68c7-124">Activer l’espace d’adressa ment SIP partagé dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="a68c7-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="a68c7-125">En plus de la modification que vous avez faite dans votre déploiement local, vous devez apporter la modification correspondante dans votre organisation Teams pour activer l’espace d’adressan SIP partagé avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="a68c7-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="a68c7-126">Pour activer l’espace d’adressale SIP partagé dans votre organisation, établissez une session PowerShell distante avec Teams, puis exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="a68c7-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="a68c7-127">L’attribut SharedSipAddressSpace doit rester « True » jusqu’à ce que le passage en ligne soit final et qu’aucun utilisateur ne reste en local.</span><span class="sxs-lookup"><span data-stu-id="a68c7-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="a68c7-128">Pour établir une session PowerShell distante avec Teams (ou Skype Entreprise Online), vous devez d’abord installer Teams [module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="a68c7-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="a68c7-129">Le Teams Module PowerShell remplace le module Skype Busines Online Connector, qui a été retiré.</span><span class="sxs-lookup"><span data-stu-id="a68c7-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="a68c7-130">Après avoir installé le module, vous pouvez établir une session à distance avec les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="a68c7-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="a68c7-131">Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Teams et sur l’utilisation du module Teams PowerShell, voir Configurer votre ordinateur pour [Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a68c7-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="a68c7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a68c7-132">See also</span></span>

[<span data-ttu-id="a68c7-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="a68c7-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
