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
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Skype entreprise online.'
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780103"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="596bc-103">Configurer Skype Entreprise hybride</span><span class="sxs-lookup"><span data-stu-id="596bc-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="596bc-104">Pour configurer Skype Entreprise hybride, vous devez :</span><span class="sxs-lookup"><span data-stu-id="596bc-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="596bc-105">[Configurez votre service Edge local de sorte qu’il se fédérer avec Office 365 ou une autre organisation](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span><span class="sxs-lookup"><span data-stu-id="596bc-105">[Configure your on-premises Edge service to federate with Office 365 or another organization](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span></span>
- <span data-ttu-id="596bc-106">[Configurez votre environnement local pour qu’il approuve office 365 et activez l’espace d’adressage SIP partagé avec office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="596bc-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="596bc-107">[Activez l’espace d’adressage SIP partagé dans votre organisation Office 365](#enable-shared-sip-address-space-in-your-office-365-organization).</span><span class="sxs-lookup"><span data-stu-id="596bc-107">[Enable shared SIP address space in your Office 365 organization](#enable-shared-sip-address-space-in-your-office-365-organization).</span></span>

<span data-ttu-id="596bc-108">Notez que si vous disposez d’Exchange en local, vous pouvez configurer OAuth entre votre environnement Exchange local et Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="596bc-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="596bc-109">Pour plus d’informations, consultez la rubrique [Manage Server-to-Server Authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) et [envisagez d’intégrer Skype entreprise et Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="596bc-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a><span data-ttu-id="596bc-110">Configurer votre service Edge local de sorte qu’il se fédérer avec Office 365 ou une autre organisation</span><span class="sxs-lookup"><span data-stu-id="596bc-110">Configure your on-premises Edge service to federate with Office 365 or another organization</span></span>

<span data-ttu-id="596bc-111">La Fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs de Microsoft 365 ou Office 365 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="596bc-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="596bc-112">Pour configurer la Fédération, exécutez l’applet de commande suivante dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="596bc-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="596bc-113">Si la valeur « -EnablePartnerDiscovery » est définie sur $True, Skype entreprise Server utilisera des enregistrements DNS pour essayer de découvrir des domaines partenaires non répertoriés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="596bc-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="596bc-114">Si la valeur est définie sur $False, Skype entreprise Server se fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="596bc-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="596bc-115">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="596bc-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="596bc-116">Pour plus d’informations sur l’activation de la Fédération entre les utilisateurs de votre déploiement Skype entreprise local et les utilisateurs d’une organisation Skype entreprise Online, voir Configuration de la [prise en charge de la Fédération pour un client Skype entreprise Online dans Skype entreprise Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="596bc-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="596bc-117">Configuration de votre environnement local pour activer l’espace d’adressage SIP partagé avec Office 365</span><span class="sxs-lookup"><span data-stu-id="596bc-117">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="596bc-118">Vous devez aussi configurer votre environnement local pour approuver Office 365 et activer l’espace d’adressage SIP partagé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="596bc-118">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="596bc-119">Cela signifie qu’Office 365 peut potentiellement héberger des comptes d’utilisateurs pour le même ensemble de domaines SIP que votre environnement local et que les messages peuvent être routés entre les utilisateurs hébergés sur site et en ligne.</span><span class="sxs-lookup"><span data-stu-id="596bc-119">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="596bc-120">Pour ce faire, configurez un fournisseur d’hébergement avec ProxyFqdn = sipfed. online. Lync. com, comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="596bc-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="596bc-121">Tout d’abord, vérifiez si vous disposez déjà d’un fournisseur d’hébergement avec ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="596bc-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="596bc-122">S’il en existe un, supprimez-le à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="596bc-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="596bc-123">Créez ensuite un fournisseur d’hébergement, utilisez la cmdlet New-CsHostingProvider comme suit :</span><span class="sxs-lookup"><span data-stu-id="596bc-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a><span data-ttu-id="596bc-124">Activer l’espace d’adressage SIP partagé dans votre organisation Office 365</span><span class="sxs-lookup"><span data-stu-id="596bc-124">Enable shared SIP address space in your Office 365 organization</span></span>
  
<span data-ttu-id="596bc-125">Outre les modifications que vous avez apportées dans votre déploiement local, vous devrez apporter la modification correspondante dans votre organisation Office 365 pour activer l’espace d’adressage SIP partagé avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="596bc-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="596bc-126">Pour activer l’espace d’adressage SIP partagé dans votre organisation Office 365, établissez une session PowerShell distante avec Skype entreprise Online, puis exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="596bc-126">To enable shared SIP address space in your Office 365 organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="596bc-127">L’attribut SharedSipAddressSpace doit rester « true » jusqu’à ce que le déplacement vers Online soit définitif et qu’aucun utilisateur ne reste en local.</span><span class="sxs-lookup"><span data-stu-id="596bc-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="596bc-128">Pour établir une session PowerShell distante avec teams ou Skype entreprise Online, vous devez d’abord installer le module du connecteur Skype entreprise Online pour Windows PowerShell, que vous pouvez obtenir [ici](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="596bc-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="596bc-129">Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="596bc-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="596bc-130">Pour plus d’informations sur l’établissement d’une session PowerShell à distance avec Skype entreprise Online et sur l’utilisation du module connecteur Skype entreprise Online, consultez la rubrique [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="596bc-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="596bc-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="596bc-131">See also</span></span>

[<span data-ttu-id="596bc-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="596bc-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
