---
title: Configurer votre déploiement local pour la diffusion de réunion Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride Skype Entreprise Server local.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820704"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="0c0c7-103">Configurer votre déploiement local pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="0c0c7-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="0c0c7-104">**Résumé :** Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride Skype Entreprise Server local.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="0c0c7-105">Diffusion de réunion Skype est un service en ligne qui fait partie d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="0c0c7-106">Si vous exécutez Skype Entreprise Server en local et que vous souhaitez utiliser diffusion de réunion Skype dans votre environnement, vous devez suivre les étapes de configuration de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="0c0c7-107">Avant de commencer, votre environnement doit être configuré pour un environnement hybride avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="0c0c7-108">Pour plus d’informations, voir [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="0c0c7-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="0c0c7-109">Configurer votre environnement hybride pour diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="0c0c7-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="0c0c7-110">Pour préparer votre environnement pour la diffusion de réunion Skype, vous devez :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="0c0c7-111">Configurer la fédération avec les ressources Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c0c7-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="0c0c7-112">Configurer des domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="0c0c7-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="0c0c7-113">Configurer la fédération avec les ressources Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c0c7-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="0c0c7-114">Pour activer la fédération avec les ressources Skype Entreprise Online, vous devez configurer l’accès externe pour un fournisseur fédéré SIP.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="0c0c7-115">Pour ce faire, à l’aide du Panneau de contrôle Skype Entreprise Server, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="0c0c7-116">Démarrez le Panneau de contrôle Skype Entreprise Server et sélectionnez **Accès** externe sur la gauche.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="0c0c7-117">Sélectionnez **Fournisseurs fédérés SIP,** puis cliquez sur **Nouveau.**</span><span class="sxs-lookup"><span data-stu-id="0c0c7-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="0c0c7-118">Configurez le nouveau fournisseur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="0c0c7-119">**Activez les communications avec ce fournisseur :**</span><span class="sxs-lookup"><span data-stu-id="0c0c7-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="0c0c7-120">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="0c0c7-120">Selected</span></span>  <br/> |
|<span data-ttu-id="0c0c7-121">**Nom du fournisseur :** propriété requise.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="0c0c7-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="0c0c7-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="0c0c7-123">**Service Edge d’accès (FQDN) :** propriété requise.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="0c0c7-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c0c7-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="0c0c7-125">**Niveau de vérification par défaut :**</span><span class="sxs-lookup"><span data-stu-id="0c0c7-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="0c0c7-126">Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="0c0c7-127">Vous pouvez également activer la fédération avec les ressources Skype Entreprise Online en exécutant l’cmdlet suivante dans Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="0c0c7-128">Configurer des domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="0c0c7-128">Configure SIP federated domains</span></span>

<span data-ttu-id="0c0c7-129">Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="0c0c7-130">Répétez ces étapes pour chacun des domaines répertoriés, en créant 4 domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="0c0c7-131">Ces domaines sont inclus pour les centres de données régionaux utilisés dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="0c0c7-132">Démarrez le Panneau de contrôle Skype Entreprise Server et sélectionnez **Accès** externe sur la gauche.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="0c0c7-133">Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau.**</span><span class="sxs-lookup"><span data-stu-id="0c0c7-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="0c0c7-134">Pour le **nom de domaine (ou nom de** domaine complet) : entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="0c0c7-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c0c7-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="0c0c7-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c0c7-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="0c0c7-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c0c7-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="0c0c7-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c0c7-138">resources.lync.com</span></span>
    
<span data-ttu-id="0c0c7-139">Vous pouvez également configurer l’accès externe pour les domaines fédérés SIP en exécutant les cmdlets suivantes dans Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="0c0c7-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="0c0c7-140">Une fois ces étapes de configuration terminées, vous pouvez commencer à utiliser diffusion de réunion Skype dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="0c0c7-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="0c0c7-141">Pour plus d’informations sur diffusion de réunion Skype, voir [Qu’est-ce](https://go.microsoft.com/fwlink/?LinkId=617071) qu’une diffusion de réunion Skype ? et le Guide d’administration de diffusion de réunion [Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="0c0c7-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

