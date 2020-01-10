---
title: Configuration de votre déploiement local pour la diffusion de réunion Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride de Skype entreprise Server sur site.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002804"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="d7579-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="d7579-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="d7579-104">**Résumé :** Découvrez les étapes à suivre pour configurer la diffusion de réunion Skype pour votre déploiement hybride de Skype entreprise Server sur site.</span><span class="sxs-lookup"><span data-stu-id="d7579-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="d7579-105">La diffusion de réunion Skype est un service en ligne intégré à Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7579-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="d7579-106">Si vous utilisez Skype entreprise Server en local et souhaitez utiliser la diffusion de réunion Skype dans votre environnement, vous devez suivre les étapes de configuration de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d7579-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="d7579-107">Avant de commencer, votre environnement doit être configuré pour une connexion hybride avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="d7579-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="d7579-108">Pour plus d’informations, reportez-vous aux rubriques [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) et [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="d7579-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="d7579-109">Configurer votre environnement hybride pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="d7579-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="d7579-110">Pour préparer votre environnement pour la diffusion de réunion Skype, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7579-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="d7579-111">Configurer la Fédération avec des ressources Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d7579-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="d7579-112">Configuration de domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="d7579-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="d7579-113">Configurer la Fédération avec des ressources Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d7579-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="d7579-114">Pour activer la Fédération avec des ressources Skype entreprise Online, vous devez configurer l’accès externe pour un fournisseur fédéré SIP.</span><span class="sxs-lookup"><span data-stu-id="d7579-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="d7579-115">Pour cela, utilisez le panneau de configuration Skype entreprise Server en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="d7579-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="d7579-116">Démarrez le panneau de configuration Skype entreprise Server et sélectionnez **accès externe** à gauche.</span><span class="sxs-lookup"><span data-stu-id="d7579-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="d7579-117">Sélectionnez **Fournisseurs fédérés SIP** et cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d7579-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="d7579-118">Configurez le nouveau fournisseur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="d7579-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="d7579-119">**Activer les communications avec ce fournisseur :**</span><span class="sxs-lookup"><span data-stu-id="d7579-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="d7579-120">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="d7579-120">Selected</span></span>  <br/> |
|<span data-ttu-id="d7579-121">**Nom du fournisseur :**</span><span class="sxs-lookup"><span data-stu-id="d7579-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="d7579-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="d7579-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="d7579-123">**Service Edge d’accès (nom de domaine complet [FQDN]) :**</span><span class="sxs-lookup"><span data-stu-id="d7579-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="d7579-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="d7579-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="d7579-125">**Niveau de vérification par défaut :**</span><span class="sxs-lookup"><span data-stu-id="d7579-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="d7579-126">Autorisez les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d7579-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="d7579-127">Vous pouvez également activer la Fédération avec des ressources Skype entreprise Online en exécutant l’applet de commande suivante dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="d7579-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="d7579-128">Configuration de domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="d7579-128">Configure SIP federated domains</span></span>

<span data-ttu-id="d7579-129">Ensuite, vous devez ajouter des domaines fédérés SIP à la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="d7579-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="d7579-130">Répétez cette procédure pour chacun des domaines répertoriés, en créant quatre domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="d7579-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="d7579-131">Ces domaines incluent les centres de données régionaux utilisés dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="d7579-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="d7579-132">Démarrez le panneau de configuration Skype entreprise Server et sélectionnez **accès externe** à gauche.</span><span class="sxs-lookup"><span data-stu-id="d7579-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="d7579-133">Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d7579-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="d7579-134">Dans le champ **Nom de domaine (ou nom de domaine complet) :**, entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="d7579-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="d7579-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d7579-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="d7579-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d7579-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="d7579-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d7579-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="d7579-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="d7579-138">resources.lync.com</span></span>
    
<span data-ttu-id="d7579-139">Vous pouvez également configurer l’accès externe pour les domaines fédérés SIP en exécutant les applets de commande suivantes dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="d7579-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="d7579-140">Une fois ces étapes de configuration terminées, vous pouvez commencer à utiliser la diffusion de réunion Skype dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d7579-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="d7579-141">Pour plus d’informations sur la diffusion de réunion Skype, voir [qu’est-ce qu’une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et guide d’administration de la [diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="d7579-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

