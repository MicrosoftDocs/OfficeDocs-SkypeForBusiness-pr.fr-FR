---
title: Configurer et gérer Skype Entreprise, version Cloud Connector
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
description: Découvrez comment configurer Skype Entreprise, version Cloud Connector, une topologie locale minimale pour permettre l’intégration de votre infrastructure vocale locale aux services vocaux du système téléphonique (CLOUD PBX) dans Skype Entreprise Online.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094872"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="c1699-103">Configurer et gérer Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="c1699-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="c1699-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c1699-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c1699-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="c1699-106">Découvrez comment configurer Skype Entreprise, version Cloud Connector, une topologie locale minimale pour permettre l’intégration de votre infrastructure vocale locale aux services vocaux du système téléphonique (CLOUD PBX) dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="c1699-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="c1699-107">Avant de commencer, vous devez passer en revue les conditions préalables dans [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="c1699-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c1699-108">Les étapes de cette rubrique s’appliquent uniquement aux éditions Cloud Connector 1.4.1 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="c1699-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="c1699-109">Si vous n’avez pas encore mis à niveau vers Cloud Connector Edition 2.1, voir Mise à niveau vers une [nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c1699-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="c1699-110">Vous pouvez télécharger le fichier d’installation à partir [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) de .</span><span class="sxs-lookup"><span data-stu-id="c1699-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="c1699-111">Étapes de configuration de Skype Entreprise, version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="c1699-112">Le tableau suivant répertorie les étapes nécessaires pour installer et configurer Cloud Connector Edition :</span><span class="sxs-lookup"><span data-stu-id="c1699-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="c1699-113">**Étape**</span><span class="sxs-lookup"><span data-stu-id="c1699-113">**Step**</span></span>|<span data-ttu-id="c1699-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="c1699-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c1699-115">Préparation de votre appliance Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="c1699-116">Téléchargez le fichier d’installation, préparez les certificats, configurez Hyper-V et préparez votre environnement pour le déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c1699-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="c1699-117">Déployer un seul site dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="c1699-118">Créez un site dans votre déploiement Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c1699-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="c1699-119">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="c1699-120">Ajoutez des sites à votre déploiement et découvrez les différences entre les déploiements sur un seul site et sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="c1699-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="c1699-121">Configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="c1699-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="c1699-122">Ajoutez des enregistrements DNS, configurez un système hybride, configurez des passerelles PSTN et activez les utilisateurs pour la messagerie vocale du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="c1699-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="c1699-123">Validation de votre déploiement de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="c1699-124">Assurez-vous que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="c1699-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="c1699-125">Effectuer une mise à niveau vers une nouvelle version de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="c1699-126">Mettre à niveau votre déploiement Cloud Connector existant vers la version 2.1.</span><span class="sxs-lookup"><span data-stu-id="c1699-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="c1699-127">Modifier la configuration d’un déploiement Cloud Connector existant</span><span class="sxs-lookup"><span data-stu-id="c1699-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="c1699-128">Modifier les paramètres dans Cloud Connector une fois qu’il est déjà déployé.</span><span class="sxs-lookup"><span data-stu-id="c1699-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="c1699-129">Déployer le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c1699-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="c1699-130">Découvrez comment déployer le contournement de média dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c1699-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="c1699-131">Référence de cmdlet Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="c1699-132">Découvrez les cmdlets PowerShell utilisées dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c1699-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="c1699-133">Résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1699-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="c1699-134">Solutions aux problèmes courants rencontrés avec un déploiement Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c1699-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
