---
title: Configuration de votre déploiement local pour la diffusion de réunion Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Résumé : Découvrez les étapes que vous devez effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride de serveur d’entreprise.'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="1eaa1-103">Configuration de votre déploiement local pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="1eaa1-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="1eaa1-104">**Résumé :** Obtenir des informations sur les étapes que vous devez effectuer pour configurer la diffusion de réunion Skype pour votre Skype sur site pour le déploiement hybride de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="1eaa1-105">Diffusion de réunion Skype est un service en ligne qui fait partie d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="1eaa1-106">Si vous exécutez Skype pour Business Server en local et que vous souhaitez utiliser Skype réunion de diffusion dans votre environnement, vous devez suivre les étapes de configuration dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="1eaa1-107">Avant de commencer, votre environnement doit être configuré pour hybride avec Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="1eaa1-108">Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et de [déployer une connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1eaa1-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="1eaa1-109">Configurer votre environnement hybride pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="1eaa1-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="1eaa1-110">Vous devez effectuer les tâches suivantes pour préparer votre environnement pour diffusion de réunion de Skype :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="1eaa1-111">Configurer la fédération avec Skype pour les ressources d’entreprise en ligne</span><span class="sxs-lookup"><span data-stu-id="1eaa1-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="1eaa1-112">Configuration de domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="1eaa1-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="1eaa1-113">Configurer la fédération avec Skype pour les ressources d’entreprise en ligne</span><span class="sxs-lookup"><span data-stu-id="1eaa1-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="1eaa1-114">Pour activer la fédération avec Skype pour les ressources d’entreprise en ligne, vous devez configurer l’accès externe pour un fournisseur SIP de fédéré.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="1eaa1-115">Pour faire cela à l’aide de la Skype pour le panneau de configuration de Business Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="1eaa1-116">Démarrer le Skype pour le panneau de configuration de Business Server et sélectionnez **l’Accès externe** à gauche.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="1eaa1-117">Sélectionnez **Fournisseurs fédérés SIP** et cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="1eaa1-118">Configurez le nouveau fournisseur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="1eaa1-119">**Permettre la communication avec ce fournisseur :**</span><span class="sxs-lookup"><span data-stu-id="1eaa1-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="1eaa1-120">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="1eaa1-120">Selected</span></span>  <br/> |
|<span data-ttu-id="1eaa1-121">**Nom du fournisseur :**</span><span class="sxs-lookup"><span data-stu-id="1eaa1-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="1eaa1-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="1eaa1-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="1eaa1-123">**Service Edge d’accès (nom de domaine complet [FQDN]) :**</span><span class="sxs-lookup"><span data-stu-id="1eaa1-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="1eaa1-124">sipfed.Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1eaa1-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="1eaa1-125">**Niveau de vérification par défaut :**</span><span class="sxs-lookup"><span data-stu-id="1eaa1-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="1eaa1-126">Autorisez les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="1eaa1-127">Vous pouvez également activer la fédération avec Skype pour les ressources d’entreprise en ligne en exécutant la cmdlet suivante dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="1eaa1-128">Configuration de domaines fédérés SIP</span><span class="sxs-lookup"><span data-stu-id="1eaa1-128">Configure SIP federated domains</span></span>

<span data-ttu-id="1eaa1-129">Ensuite, vous devez ajouter des domaines de SIP fédéré à la liste de domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="1eaa1-130">Répétez cette procédure pour chacun des domaines répertoriés, en créant quatre domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="1eaa1-131">Ces domaines sont notamment pour les données régionales centres utilisés dans Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="1eaa1-132">Démarrer le Skype pour le panneau de configuration de Business Server et sélectionnez **l’Accès externe** à gauche.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="1eaa1-133">Sélectionnez **Domaines fédérés SIP** et cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="1eaa1-134">Dans le champ **Nom de domaine (ou nom de domaine complet) :**, entrez le domaine, en répétant cette procédure pour chacun des domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="1eaa1-135">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1eaa1-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="1eaa1-136">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1eaa1-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="1eaa1-137">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1eaa1-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="1eaa1-138">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="1eaa1-138">resources.lync.com</span></span>
    
<span data-ttu-id="1eaa1-139">Vous pouvez également configurer l’accès externe pour les domaines SIP fédéré en exécutant les applets de commande suivantes dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1eaa1-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="1eaa1-140">Une fois que vous avez terminé ces étapes de configuration, vous pouvez démarrer à l’aide de Skype réunion de diffusion dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="1eaa1-141">Pour plus d’informations sur la diffusion de réunion Skype, consultez [ce qu’est une diffusion de réunion Skype ?](https://go.microsoft.com/fwlink/?LinkId=617071) et [Guide de l’administrateur de diffusion Skype réunion](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="1eaa1-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

