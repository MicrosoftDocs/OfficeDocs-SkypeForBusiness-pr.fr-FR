---
title: Configurer Skype pour un environnement hybride Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.'
ms.openlocfilehash: b71ea92b5f7ce275dc5d1b5d2b7ece5be3c77ffc
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244003"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="14840-103">Configurer Skype pour un environnement hybride Business</span><span class="sxs-lookup"><span data-stu-id="14840-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="14840-104">Pour configurer Skype pour hybride d’entreprise, vous devez :</span><span class="sxs-lookup"><span data-stu-id="14840-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="14840-105">Configurer votre environnement local à fédérer avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="14840-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="14840-106">Configurer votre environnement local pour la gestion de la confidentialité Office 365 et activer l’espace d’adressage SIP partagé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="14840-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="14840-107">Activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365.</span><span class="sxs-lookup"><span data-stu-id="14840-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

<span data-ttu-id="14840-108">Notez que si vous avez Exchange locale, vous souhaiterez peut-être configurer OAuth entre votre Exchange locale et Skype pour les environnements d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="14840-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="14840-109">Pour plus d’informations, voir [gérer l’authentification serveur à serveur dans Skype pour Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) et [planifier l’intégration Skype pour les entreprises et Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="14840-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="14840-110">Configurer le service Edge de local à fédérer avec Office 365</span><span class="sxs-lookup"><span data-stu-id="14840-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="14840-111">La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14840-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="14840-112">Pour configurer la fédération, exécutez l’applet de commande suivante dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="14840-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="14840-113">Configurer votre environnement local pour permettre l’espace d’adressage SIP partagé avec Office 365</span><span class="sxs-lookup"><span data-stu-id="14840-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="14840-114">Vous devez également configurer votre environnement local pour la gestion de la confidentialité Office 365 et activer l’espace d’adressage SIP partagé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="14840-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="14840-115">Cela signifie Office 365 peuvent potentiellement héberger des comptes d’utilisateurs pour le même ensemble de domaines SIP que votre environnement local et les messages peuvent être routés entre les utilisateurs hébergés sur site et en ligne.</span><span class="sxs-lookup"><span data-stu-id="14840-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="14840-116">Pour cela, en configurant un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="14840-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="14840-117">Tout d’abord, vérifiez si vous disposez déjà d’un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="14840-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="14840-118">Si elle existe, puis supprimez-le à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="14840-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="14840-119">Puis créez un nouveau fournisseur d’hébergement, utilisez l’applet de commande New-CsHostingProvider comme suit :</span><span class="sxs-lookup"><span data-stu-id="14840-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="14840-120">Activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365</span><span class="sxs-lookup"><span data-stu-id="14840-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="14840-121">Outre les modifications apportées dans votre déploiement sur site, vous devez effectuer la modification correspondante dans votre organisation cliente Office 365 à activé espace d’adressage SIP partagé avec votre déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="14840-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="14840-122">Pour activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365, établir une session PowerShell distante avec Skype pour Business Online, puis exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="14840-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="14840-123">L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="14840-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="14840-124">Pour établir une session PowerShell distante avec des équipes ou Skype pour Business Online, vous devez d’abord installer le Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir [ici](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="14840-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="14840-125">Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="14840-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="14840-126">Pour plus d’informations sur la façon d’établir une session PowerShell distante avec Skype pour Business en ligne et comment utiliser la Skype pour le module Business Connector en ligne, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="14840-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="14840-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14840-127">See also</span></span>

[<span data-ttu-id="14840-128">Nouvelle-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="14840-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

