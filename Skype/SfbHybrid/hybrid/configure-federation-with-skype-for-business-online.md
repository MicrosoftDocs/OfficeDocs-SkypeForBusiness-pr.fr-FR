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
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Skype Entreprise Online.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569216"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="466f5-103">Configurer Skype Entreprise hybride</span><span class="sxs-lookup"><span data-stu-id="466f5-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="466f5-104">Pour configurer Skype Entreprise hybride, vous devez :</span><span class="sxs-lookup"><span data-stu-id="466f5-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="466f5-105">Configurez votre service Edge local pour la fédération avec [Microsoft 365 ou Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)</span><span class="sxs-lookup"><span data-stu-id="466f5-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="466f5-106">Configurez votre environnement local pour qu’il utilise [Microsoft 365 ou Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)et activez l’espace d’adressare SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="466f5-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="466f5-107">[Activez l’espace d’adressare SIP partagé dans votre organisation Microsoft 365 ou Office 365.](#enable-shared-sip-address-space-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="466f5-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="466f5-108">Notez que si vous avez Exchange en local, vous pouvez configurer OAuth entre vos environnements Exchange local et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="466f5-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="466f5-109">Pour plus d’informations, voir Gérer l’authentification de serveur à serveur [dans Skype](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) Entreprise Server et planifier l’intégration de Skype Entreprise [et d’Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)</span><span class="sxs-lookup"><span data-stu-id="466f5-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="466f5-110">Configurer votre service Edge local pour la fédération avec Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="466f5-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="466f5-111">La fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs microsoft 365 ou Office 365 de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="466f5-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="466f5-112">Pour configurer la fédération, exécutez l’cmdlet suivante dans Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="466f5-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="466f5-113">Si la valeur « -EnablePartnerDiscovery » est définie sur $True, Skype Entreprise Server utilise les enregistrements DNS pour essayer de découvrir les domaines partenaires non répertoriés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="466f5-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="466f5-114">Si la valeur est définie sur $False, Skype Entreprise Server se fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="466f5-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="466f5-115">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="466f5-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="466f5-116">Pour plus d’informations sur l’activation de la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’une organisation Skype Entreprise Online, voir Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online dans [Skype Entreprise Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)</span><span class="sxs-lookup"><span data-stu-id="466f5-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="466f5-117">Configurer votre environnement local pour activer l’espace d’adressare SIP partagé avec Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="466f5-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="466f5-118">Vous devez également configurer votre environnement local pour qu’il utilise Microsoft 365 ou Office 365 et activer l’espace d’adressare SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="466f5-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="466f5-119">Cela signifie que Microsoft 365 ou Office 365 peut potentiellement héberger des comptes d’utilisateur pour le même ensemble de domaines SIP que votre environnement local, et que les messages peuvent être acheminés entre les utilisateurs hébergés en local et en ligne.</span><span class="sxs-lookup"><span data-stu-id="466f5-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="466f5-120">Pour ce faire, configurez un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="466f5-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="466f5-121">Tout d’abord, vérifiez si vous avez déjà un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="466f5-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="466f5-122">S’il en existe un, supprimez-le à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="466f5-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="466f5-123">Ensuite, créez un fournisseur d’hébergement, New-CsHostingProvider cmdlet comme suit :</span><span class="sxs-lookup"><span data-stu-id="466f5-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="466f5-124">Activer l’espace d’adressa ment SIP partagé dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="466f5-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="466f5-125">Outre les changements que vous avez apportés dans votre déploiement local, vous devez apporter la modification correspondante dans votre organisation Microsoft 365 ou Office 365 pour activer l’espace d’adressare SIP partagé avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="466f5-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="466f5-126">Pour activer l’espace d’adressale SIP partagé dans votre organisation, établissez une session PowerShell distante avec Skype Entreprise Online, puis exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="466f5-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="466f5-127">L’attribut SharedSipAddressSpace doit rester « True » jusqu’à ce que le passage en ligne soit final et qu’aucun utilisateur ne reste en local.</span><span class="sxs-lookup"><span data-stu-id="466f5-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="466f5-128">Pour établir une session PowerShell distante avec Teams ou Skype Entreprise Online, vous devez d’abord installer le [module PowerShell Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="466f5-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="466f5-129">Après avoir installé le module, vous pouvez établir une session à distance avec les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="466f5-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="466f5-130">Pour plus d’informations sur l’établissement d’une session PowerShell à distance avec Skype Entreprise Online et sur l’utilisation du module Connecteur Skype Entreprise Online, voir Configurer votre ordinateur pour [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="466f5-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="466f5-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="466f5-131">See also</span></span>

[<span data-ttu-id="466f5-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="466f5-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
