---
title: Configuration et gestion de Skype Entreprise, version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Découvrez comment configurer Skype pour l’édition de connecteur Business Cloud, une topologie minimale locale pour activer l’intégration de votre infrastructure de voix sur site avec un système téléphonique dans Office 365 (en nuage PBX) des services de téléphonie dans Skype pour Business Online.
ms.openlocfilehash: 5d057a299e51bfb83bd6711fcf1fbe8b4ee98f02
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897997"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="7b891-103">Configuration et gestion de Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="7b891-104">Découvrez comment configurer Skype pour l’édition de connecteur Business Cloud, une topologie minimale locale pour activer l’intégration de votre infrastructure de voix sur site avec un système téléphonique dans Office 365 (en nuage PBX) des services de téléphonie dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="7b891-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="7b891-105">Avant de commencer, vous devez examiner les conditions préalables décrites dans [Plan for Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="7b891-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7b891-106">Les étapes de cette rubrique s'appliquent uniquement à la version 1.4.1 et suivantes de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7b891-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="7b891-107">Si vous n'avez pas encore effectué la mise à niveau vers Cloud Connector Edition 2.1, consultez [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7b891-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="7b891-108">Vous pouvez télécharger le fichier d’installation à partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="7b891-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="7b891-109">Étapes à suivre pour la configuration de Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="7b891-110">Le tableau suivant établit la liste des étapes que vous aurez à suivre pour installer et configurer la version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="7b891-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="7b891-111">**Étape**</span><span class="sxs-lookup"><span data-stu-id="7b891-111">**Step**</span></span>|<span data-ttu-id="7b891-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="7b891-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7b891-113">Préparation de votre appliance Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="7b891-114">Télécharger le fichier d’installation, préparer des certificats, configurer Hyper-V et préparer votre environnement à votre déploiement en nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="7b891-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="7b891-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="7b891-116">Créer un site dans votre déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7b891-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="7b891-117">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="7b891-118">Ajouter des sites à votre déploiement de la version CC et découvrir les différences entre les déploiement sur site unique et ceux sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="7b891-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="7b891-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="7b891-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="7b891-120">Ajoutez des enregistrements DNS, configurez l'hybridité, organisez les passerelles PSTN et activez la messagerie vocale du système téléphonique d'Office 365 pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b891-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="7b891-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="7b891-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="7b891-122">S'assurer que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="7b891-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="7b891-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="7b891-124">Effectuez une mise à niveau de votre déploiement Cloud Connector vers la version 2.1.</span><span class="sxs-lookup"><span data-stu-id="7b891-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="7b891-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="7b891-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="7b891-126">Modifier les paramètres dans le nuage connecteur après avoir été déjà déployé.</span><span class="sxs-lookup"><span data-stu-id="7b891-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="7b891-127">Déployer le contournement de média dans le nuage connecteur Edition</span><span class="sxs-lookup"><span data-stu-id="7b891-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="7b891-128">Apprenez à déployer la déviation du trafic multimédia dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="7b891-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="7b891-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="7b891-130">Découvrir les applets de commande PowerShell utilisées dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7b891-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="7b891-131">Résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7b891-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="7b891-132">Solutions aux problèmes courants rencontrés avec un déploiement en nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="7b891-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

