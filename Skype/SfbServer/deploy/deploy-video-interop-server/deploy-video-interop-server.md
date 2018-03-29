---
title: Déployer le serveur d’interopérabilité vidéo dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Résumé : Déployer le rôle de serveur de VIS dans Skype pour Business Server 2015.'
ms.openlocfilehash: 0716ce427814c7cf17385074727a7af4f45cfd66
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="f5592-103">Déployer le serveur d’interopérabilité vidéo dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-103">Deploy Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f5592-104">**Résumé :** Déployer le rôle de serveur de VIS dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f5592-104">**Summary:** Deploy the VIS server role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f5592-105">Skype pour Business Server peut désormais intégrer directement aux systèmes de téléconférence (VTCs) Cisco comme Cisco C60 ou Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="f5592-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="f5592-106">Cela requiert l’introduction d’un nouveau rôle de serveur appelée serveur d’interopérabilité vidéo (VIS) et de la configuration correcte de la VIS et l’équipement qu’il fonctionnera avec.</span><span class="sxs-lookup"><span data-stu-id="f5592-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="f5592-107">Un VTC s’inscrit auprès de l’infrastructure Cisco existante, telle que le Cisco Unified Communication Manager (CUCM), et une jonction SIP vidéo est utilisée entre le CUCM et le pool VIS.</span><span class="sxs-lookup"><span data-stu-id="f5592-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f5592-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="f5592-108">In this section</span></span>

<span data-ttu-id="f5592-109">La configuration de l’interopérabilité entre un serveur ou un pool VIS et des systèmes VTC requiert la réalisation des cinq procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5592-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="f5592-110">Créer un pool de VIS dans Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-110">Create a VIS pool in Skype for Business Server 2015</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="f5592-111">Déployer le rôle de serveur de VIS dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-111">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="f5592-112">Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-112">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="f5592-113">Configurer CUCM pour l’interopérabilité avec Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-113">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="f5592-114">Configurer un VTC pour l’interopérabilité avec Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-114">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="f5592-115">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="f5592-115">Related sections</span></span>

[<span data-ttu-id="f5592-116">Plan pour un serveur interopérabilité vidéo dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f5592-116">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  

