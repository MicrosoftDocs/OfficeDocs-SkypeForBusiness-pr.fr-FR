---
title: Déploiement de Edge Server dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Résumé: Découvrez comment déployer un serveur Edge ou un pool Edge dans votre environnement Skype entreprise Server.'
ms.openlocfilehash: 03cb3f1bc4a938a698c28332b4781d08434bc52f
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "36492971"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="da127-103">Déploiement de Edge Server dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="da127-104">**Résumé:** Découvrez comment déployer un serveur Edge ou un pool Edge dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da127-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="da127-105">Pourquoi déployer un serveur Edge ou un pool Edge dans votre environnement Skype entreprise Server?</span><span class="sxs-lookup"><span data-stu-id="da127-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="da127-106">Il est nécessaire de faire en sorte que les utilisateurs externes qui ne sont pas connectés au réseau interne de votre organisation puissent interagir avec les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="da127-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="da127-107">Ces utilisateurs externes peuvent être authentifiés comme des utilisateurs distants anonymes, des partenaires fédérés ou d’autres clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="da127-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="da127-108">Liste de contrôle du déploiement pour Microsoft Edge pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="da127-109">Comme indiqué plus haut, il est important de procéder à un déploiement de serveur Edge pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da127-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="da127-110">Cette liste de vérification vous donne une vue d’ensemble des tâches que vous devez effectuer, ainsi que des liens vers des étapes plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="da127-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="da127-111">Nous espérons que vous avez entamé le [plan de déploiement de serveur Edge dans la section Skype entreprise Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="da127-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="da127-112">Si ce n’est pas le cas, un grand nombre des éléments qui nous font référence sont détaillés.</span><span class="sxs-lookup"><span data-stu-id="da127-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="da127-113">La section déploiement ne contenant que des procédures, si vous souhaitez connaître le raisonnement de ces étapes, la planification est l’endroit où commencer.</span><span class="sxs-lookup"><span data-stu-id="da127-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="da127-114">Cette documentation suppose également que vous avez déjà effectué le déploiement de base de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da127-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="da127-115">Vous pouvez effectuer ce déploiement côte à côte avec le bord, mais vous devez d’abord suivre ces étapes pour que vous puissiez apporter les modifications de topologie pour le bord qui sont décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="da127-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="da127-116">Il s’agit des étapes de niveau supérieur que vous devez suivre, et des emplacements où vous trouverez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="da127-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="da127-117">Configuration requise pour le serveur Edge dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="da127-118">Configuration requise pour l’environnement du serveur Edge dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="da127-119">Créer votre topologie Edge pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="da127-120">Déploiement de serveurs Edge dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="da127-121">Valider votre déploiement Edge dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="da127-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

