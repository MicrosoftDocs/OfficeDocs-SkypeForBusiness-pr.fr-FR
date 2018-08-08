---
title: Déployer le serveur de périphérie dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Résumé : Découvrez comment déployer un serveur de périphérie ou un pool de serveurs Edge dans votre Skype pour un environnement de serveur d’entreprise.'
ms.openlocfilehash: cf379e9586b093c6aa5b09121edbc90990417de6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015161"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="754d7-103">Déployer le serveur de périphérie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="754d7-104">**Résumé :** Découvrez comment déployer un serveur de périphérie ou un pool de serveurs Edge dans votre Skype pour un environnement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="754d7-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="754d7-105">Raisons pour lesquelles déployer un serveur de périphérie ou un pool de serveurs Edge dans votre Skype pour un environnement Business Server ?</span><span class="sxs-lookup"><span data-stu-id="754d7-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="754d7-106">C’est nécessaire si vous avez besoin que des utilisateurs externes non connectés à votre réseau interne puissent interagir avec des utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="754d7-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="754d7-107">Ces utilisateurs externes peuvent être authentifiés comme des utilisateurs distants anonymes, des partenaires fédérés ou d’autres clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="754d7-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="754d7-108">Liste de vérification du déploiement du bord, pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="754d7-109">Comme mentionné ci-dessus, beaucoup est placé dans un déploiement de serveur Edge pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="754d7-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="754d7-110">Cette liste de vérification vous donne une vue d’ensemble des tâches que vous devrez faire et des liens vers des procédures plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="754d7-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="754d7-111">Nous espérons que vous avez commencé dans la section [Planifier pour les déploiements de serveur de transport Edge dans Skype pour Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="754d7-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="754d7-112">Si ce n’est pas le cas, beaucoup des choses que nous faisons référence à sont détaillées il.</span><span class="sxs-lookup"><span data-stu-id="754d7-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="754d7-113">La section déploiement contient uniquement des procédures, si vous souhaitez connaître le raisonnement sous-jacent à ces étapes, la planification est le point de départ.</span><span class="sxs-lookup"><span data-stu-id="754d7-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="754d7-114">Cette documentation suppose également que vous avez fait également le déploiement de base de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="754d7-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="754d7-115">Vous pouvez le faire ce déploiement côte à côte avec le bord, mais vous n’avez pas besoin d’effectuer ces étapes tout d’abord, vous serez alors en mesure d’apporter les modifications de topologie du bord décrits ici.</span><span class="sxs-lookup"><span data-stu-id="754d7-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="754d7-116">Il s’agit des étapes de niveau supérieur que vous devez suivre, et des emplacements où vous trouverez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="754d7-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="754d7-117">Edge requise serveur dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="754d7-118">Edge exigences Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="754d7-119">Créer votre topologie du périmètre pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="754d7-120">Déployer des serveurs de périphérie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="754d7-121">Valider votre déploiement Edge dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="754d7-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

