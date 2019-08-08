---
title: Déploiement d’un serveur de technologie d’interopérabilité vidéo dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Résumé: déploiement du rôle serveur sur Skype entreprise Server.'
ms.openlocfilehash: 790030e3ef0b88473f6fc1750c054db5cdd74b4a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235585"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="cf14e-103">Déploiement d’un serveur de technologie d’interopérabilité vidéo dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="cf14e-104">**Résumé:** Déploiement du rôle serveur sur Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cf14e-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="cf14e-105">Skype entreprise Server peut désormais être intégré aux systèmes de visioconférence Cisco (VTCs) tels que Cisco C60 ou Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="cf14e-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="cf14e-106">Pour cela, vous devez disposer d’un nouveau rôle de serveur appelé Video Interop Server (à) et d’une configuration correcte de l’écran et de l’équipement avec lesquels il fonctionne.</span><span class="sxs-lookup"><span data-stu-id="cf14e-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="cf14e-107">Un VTC s’inscrit auprès de l’infrastructure Cisco existante, telle que le Cisco Unified Communication Manager (CUCM), et une jonction SIP vidéo est utilisée entre le CUCM et le pool VIS.</span><span class="sxs-lookup"><span data-stu-id="cf14e-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cf14e-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="cf14e-108">In this section</span></span>

<span data-ttu-id="cf14e-109">La configuration de l’interopérabilité entre un serveur ou un pool VIS et des systèmes VTC requiert la réalisation des cinq procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf14e-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="cf14e-110">Créer un pool d’objets dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="cf14e-111">Déploiement du rôle serveur sur Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="cf14e-112">Configurer le serveur Video Interop dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="cf14e-113">Configurer CUCM pour l’interopérabilité avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="cf14e-114">Configurer une VTC pour l’interopérabilité avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="cf14e-115">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="cf14e-115">Related sections</span></span>

[<span data-ttu-id="cf14e-116">Planifier le serveur Video Interop dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cf14e-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

