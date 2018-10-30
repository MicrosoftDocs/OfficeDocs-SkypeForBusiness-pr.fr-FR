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
ms.openlocfilehash: df5fed224484a3c8f8957365f5304095a115b7b1
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839148"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="15115-103">Configurer Skype pour un environnement hybride Business</span><span class="sxs-lookup"><span data-stu-id="15115-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="15115-104">Pour configurer Skype pour hybride d’entreprise, vous devez :</span><span class="sxs-lookup"><span data-stu-id="15115-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="15115-105">Configurer la fédération</span><span class="sxs-lookup"><span data-stu-id="15115-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="15115-106">Configurer un espace d’adressage partagé protocole SIP (Session Initiation)</span><span class="sxs-lookup"><span data-stu-id="15115-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="15115-107">Configurer l’authentification de serveur à serveur, si nécessaire</span><span class="sxs-lookup"><span data-stu-id="15115-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="15115-108">Configurer votre service de périphérie sur site pour la fédération avec Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="15115-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="15115-109">La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="15115-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="15115-110">Pour configurer la fédération, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="15115-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="15115-111">Configurer votre Skype pour Business Online client pour un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="15115-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="15115-112">Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="15115-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="15115-113">Avant d’essayer de déplacer les utilisateurs locaux vers Skype pour Business Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="15115-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="15115-114">S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :</span><span class="sxs-lookup"><span data-stu-id="15115-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="15115-115">Move-CsUser : HostedMigration tolérance : Error=(510), Description = (client de cet utilisateur n’est pas activé pour l’espace d’adressage sip partagé).</span><span class="sxs-lookup"><span data-stu-id="15115-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="15115-116">Pour configurer un espace d’adressage SIP partagé, établir une session PowerShell distante avec Skype pour Business Online, puis exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="15115-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="15115-117">L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="15115-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="15115-118">Pour établir une session PowerShell distante avec Skype pour Business Online, vous devez d’abord installer le Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir [ici](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="15115-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="15115-119">Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="15115-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="15115-120">Pour plus d’informations sur la façon d’établir une session PowerShell distante avec Skype pour Business en ligne et comment utiliser la Skype pour le module Business Connector en ligne, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="15115-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="15115-121">Configurer l’authentification de serveur à serveur, si nécessaire</span><span class="sxs-lookup"><span data-stu-id="15115-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="15115-122">Selon le type d’environnement hybride que vous configurez, vous devrez peut-être configurer l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="15115-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="15115-123">Pour plus d’informations, voir [gérer l’authentification de serveur à serveur dans Skype pour Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span><span class="sxs-lookup"><span data-stu-id="15115-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="15115-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15115-124">See also</span></span>

[<span data-ttu-id="15115-125">Nouvelle-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="15115-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

