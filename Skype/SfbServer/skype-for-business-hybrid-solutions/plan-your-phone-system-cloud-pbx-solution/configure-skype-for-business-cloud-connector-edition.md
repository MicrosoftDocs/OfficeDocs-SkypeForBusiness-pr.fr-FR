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
ms.openlocfilehash: e30fcb4cad44bffed495f1191e5e5cae73bb18cc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358790"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="be1d7-103">Configuration et gestion de Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="be1d7-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="be1d7-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="be1d7-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="be1d7-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="be1d7-106">Découvrez comment configurer Skype entreprise version Cloud Connector, une topologie locale minimale pour permettre l’intégration de votre infrastructure vocale locale aux services vocaux de système téléphonique (PBX Cloud) dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="be1d7-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="be1d7-107">Avant de commencer, passez en revue les conditions préalables dans [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="be1d7-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be1d7-108">Les étapes de cette rubrique s’appliquent uniquement à la version de Cloud Connector 1.4.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="be1d7-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="be1d7-109">Si vous n’avez pas encore effectué la mise à niveau vers Cloud Connector Edition 2,1, consultez [la rubrique Upgrade to a New version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="be1d7-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="be1d7-110">Vous pouvez télécharger le fichier d’installation à partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="be1d7-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="be1d7-111">Étapes de configuration de Skype entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="be1d7-112">Le tableau suivant répertorie les étapes nécessaires à l’installation et la configuration de la version Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="be1d7-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="be1d7-113">**Étape**</span><span class="sxs-lookup"><span data-stu-id="be1d7-113">**Step**</span></span>|<span data-ttu-id="be1d7-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="be1d7-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="be1d7-115">Préparation de votre appliance Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="be1d7-116">Téléchargez le fichier d’installation, préparez les certificats, configurez Hyper-V et préparez votre environnement pour votre déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be1d7-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-117">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="be1d7-118">Créez un site dans votre déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be1d7-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-119">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="be1d7-120">Ajoutez des sites à votre déploiement et découvrez les différences entre les déploiements sur un ou plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="be1d7-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-121">Configuration de l’intégration de Cloud Connector à votre organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="be1d7-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="be1d7-122">Ajoutez des enregistrements DNS, configurez hybride, configurez les passerelles PSTN et activez les utilisateurs pour la messagerie vocale du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="be1d7-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-123">Validation de votre déploiement de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be1d7-124">Assurez-vous que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="be1d7-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-125">Effectuer une mise à niveau vers une nouvelle version de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="be1d7-126">Mettez à niveau votre déploiement Cloud Connector existant vers la version 2,1.</span><span class="sxs-lookup"><span data-stu-id="be1d7-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-127">Modifier la configuration d’un déploiement Cloud Connector existant</span><span class="sxs-lookup"><span data-stu-id="be1d7-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be1d7-128">Modifier les paramètres dans Cloud Connector après son déploiement.</span><span class="sxs-lookup"><span data-stu-id="be1d7-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-129">Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="be1d7-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="be1d7-130">Découvrez comment déployer la déviation du trafic multimédia dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be1d7-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-131">Référence de cmdlet Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="be1d7-132">Découvrez les applets de commande PowerShell utilisées dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be1d7-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="be1d7-133">Résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be1d7-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be1d7-134">Solutions aux problèmes courants rencontrés avec un déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be1d7-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

