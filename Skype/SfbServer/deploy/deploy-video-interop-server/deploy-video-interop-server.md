---
title: Déployer le serveur interopérabilité vidéo dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Résumé : Déployez le rôle de serveur VIS Skype pour Business Server.'
ms.openlocfilehash: 0576596d40def9470e46984c525a9add4423d1f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894562"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="13215-103">Déployer le serveur interopérabilité vidéo dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="13215-104">**Résumé :** Déployer le rôle de serveur VIS Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="13215-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="13215-105">Skype pour Business Server peut maintenant s’intégrer directement aux systèmes de téléconférence Cisco (VTCs) tels que Cisco C60 ou Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="13215-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="13215-106">Cela nécessite l’introduction d’un nouveau rôle de serveur appelée bonne configuration de la VIS et du matériel vidéo Interop Server (pouces) et avec qu'il interagit.</span><span class="sxs-lookup"><span data-stu-id="13215-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="13215-107">Un VTC s’inscrit auprès de l’infrastructure Cisco existante, telle que le Cisco Unified Communication Manager (CUCM), et une jonction SIP vidéo est utilisée entre le CUCM et le pool VIS.</span><span class="sxs-lookup"><span data-stu-id="13215-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="13215-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="13215-108">In this section</span></span>

<span data-ttu-id="13215-109">La configuration de l’interopérabilité entre un serveur ou un pool VIS et des systèmes VTC requiert la réalisation des cinq procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="13215-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="13215-110">Créer un pool VIS dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="13215-111">Déployer le rôle de serveur VIS Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="13215-112">Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="13215-113">Configurer CUCM pour l’interopérabilité avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="13215-114">Configurer un VTC pour l’interopérabilité avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="13215-115">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="13215-115">Related sections</span></span>

[<span data-ttu-id="13215-116">Planification de serveur interopérabilité vidéo dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="13215-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

