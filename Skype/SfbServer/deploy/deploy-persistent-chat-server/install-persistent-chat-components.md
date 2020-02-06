---
title: Installation des composants de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Résumé : cette rubrique vous explique comment utiliser l’Assistant Déploiement de Skype entreprise Server pour installer les composants et services de Skype entreprise Server 2015.'
ms.openlocfilehash: 019700b169c3507540c93a3a152c3741de2681fb
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795685"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="d3b1c-103">Installation des composants de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3b1c-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3b1c-104">**Résumé :** Consultez cette rubrique pour savoir comment utiliser l’Assistant Déploiement de Skype entreprise Server pour installer les composants et services de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3b1c-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="d3b1c-105">Avant d’installer les composants chat persistants, assurez-vous que vous avez déjà installé le matériel et les logiciels requis et que vous avez créé la topologie appropriée pour prendre en charge le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="d3b1c-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="d3b1c-106">Pour plus d’informations sur la planification et la configuration requise, reportez-vous à [la section Configuration requise pour votre environnement Skype entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) et [planifier le serveur de chat permanent dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3b1c-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="d3b1c-107">Pour plus d’informations sur la mise à jour et la publication de votre topologie dans le cas d’inclusion du serveur de chat permanent, voir [Ajouter le serveur de conversation permanente à votre topologie 2015 Skype entreprise Server](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3b1c-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="d3b1c-108">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d3b1c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d3b1c-109">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3b1c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="d3b1c-110">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="d3b1c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="d3b1c-111">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3b1c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="d3b1c-112">Installation et démarrage des services</span><span class="sxs-lookup"><span data-stu-id="d3b1c-112">Install and start services</span></span>

<span data-ttu-id="d3b1c-113">À l’aide de l’Assistant Déploiement de Skype entreprise Server, sélectionnez Installer ou mettre à jour le système Skype entreprise Server pour effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3b1c-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="d3b1c-114">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="d3b1c-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="d3b1c-115">Installer ou supprimer des composants Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d3b1c-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="d3b1c-116">Demander, installer ou assigner des certificats</span><span class="sxs-lookup"><span data-stu-id="d3b1c-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="d3b1c-117">Démarrer les services</span><span class="sxs-lookup"><span data-stu-id="d3b1c-117">Start services</span></span>
    
<span data-ttu-id="d3b1c-118">Pour plus d’informations sur l’utilisation de l’Assistant déploiement pour installer des composants, attribuer des certificats et démarrer des services, reportez-vous à la rubrique [installation de Skype entreprise server 2015](../../deploy/install/install.md) et [installation de skype entreprise Server 2015 sur des serveurs dans la topologie](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3b1c-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

