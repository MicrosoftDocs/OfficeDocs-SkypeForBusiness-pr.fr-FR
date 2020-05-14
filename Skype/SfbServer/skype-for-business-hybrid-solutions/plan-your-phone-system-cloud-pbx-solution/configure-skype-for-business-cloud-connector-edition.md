---
title: Configuration et gestion de Skype entreprise, version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Découvrez comment configurer Skype entreprise version Cloud Connector, une topologie locale minimale pour permettre l’intégration de votre infrastructure vocale locale aux services vocaux de système téléphonique (PBX Cloud) dans Skype entreprise online.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219514"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="62937-103">Configuration et gestion de Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="62937-104">Découvrez comment configurer Skype entreprise version Cloud Connector, une topologie locale minimale pour permettre l’intégration de votre infrastructure vocale locale aux services vocaux de système téléphonique (PBX Cloud) dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="62937-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="62937-105">Avant de commencer, passez en revue les conditions préalables dans [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="62937-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62937-106">Les étapes de cette rubrique s’appliquent uniquement à la version de Cloud Connector 1.4.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="62937-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="62937-107">Si vous n’avez pas encore effectué la mise à niveau vers Cloud Connector Edition 2,1, consultez [la rubrique Upgrade to a New version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="62937-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="62937-108">Vous pouvez télécharger le fichier d’installation à partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="62937-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="62937-109">Étapes de configuration de Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="62937-110">Le tableau suivant répertorie les étapes nécessaires à l’installation et la configuration de la version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="62937-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="62937-111">**Étape**</span><span class="sxs-lookup"><span data-stu-id="62937-111">**Step**</span></span>|<span data-ttu-id="62937-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="62937-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="62937-113">Préparation de votre appliance Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="62937-114">Téléchargez le fichier d’installation, préparez les certificats, configurez Hyper-V et préparez votre environnement pour votre déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="62937-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="62937-115">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="62937-116">Créez un site dans votre déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="62937-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="62937-117">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="62937-118">Ajoutez des sites à votre déploiement et découvrez les différences entre les déploiements sur un ou plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="62937-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="62937-119">Configuration de l’intégration de Cloud Connector à votre organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="62937-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="62937-120">Ajoutez des enregistrements DNS, configurez hybride, configurez les passerelles PSTN et activez les utilisateurs pour la messagerie vocale du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="62937-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="62937-121">Validation de votre déploiement de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62937-122">Assurez-vous que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="62937-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="62937-123">Effectuer une mise à niveau vers une nouvelle version de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="62937-124">Mettez à niveau votre déploiement Cloud Connector existant vers la version 2,1.</span><span class="sxs-lookup"><span data-stu-id="62937-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="62937-125">Modifier la configuration d’un déploiement Cloud Connector existant</span><span class="sxs-lookup"><span data-stu-id="62937-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62937-126">Modifier les paramètres dans Cloud Connector après son déploiement.</span><span class="sxs-lookup"><span data-stu-id="62937-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="62937-127">Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="62937-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="62937-128">Découvrez comment déployer la déviation du trafic multimédia dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="62937-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="62937-129">Référence de cmdlet Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="62937-130">Découvrez les applets de commande PowerShell utilisées dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="62937-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="62937-131">Résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="62937-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="62937-132">Solutions aux problèmes courants rencontrés avec un déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="62937-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

