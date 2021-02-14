---
title: Installer des composants de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Résumé : Lisez cette rubrique pour découvrir comment utiliser l’Assistant Déploiement de Skype Entreprise Server pour installer les composants et services Skype Entreprise Server 2015.'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802084"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="cbb55-103">Installer des composants de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="cbb55-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbb55-104">**Résumé :** Lisez cette rubrique pour découvrir comment utiliser l’Assistant Déploiement de Skype Entreprise Server pour installer les composants et services Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cbb55-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="cbb55-105">Avant d’installer les composants de conversation permanente, assurez-vous que vous avez déjà installé le matériel et les logiciels prérequis et créé la topologie appropriée pour prendre en charge le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="cbb55-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="cbb55-106">Pour plus d’informations sur la planification et les conditions requises, voir [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and Plan for Persistent Chat Server in Skype for Business Server [2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cbb55-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="cbb55-107">Pour plus d’informations sur la mise à jour et la publication de votre topologie pour inclure un serveur de conversation permanente, voir Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise [Server 2015.](add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="cbb55-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="cbb55-108">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cbb55-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cbb55-109">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cbb55-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="cbb55-110">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="cbb55-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="cbb55-111">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cbb55-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="cbb55-112">Installer et démarrer des services</span><span class="sxs-lookup"><span data-stu-id="cbb55-112">Install and start services</span></span>

<span data-ttu-id="cbb55-113">À l’aide de l’Assistant Déploiement de Skype Entreprise Server, choisissez Installer ou mettre à jour le système Skype Entreprise Server pour effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbb55-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="cbb55-114">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="cbb55-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="cbb55-115">Installer ou supprimer des composants Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cbb55-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="cbb55-116">Demander, installer ou assigner des certificats</span><span class="sxs-lookup"><span data-stu-id="cbb55-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="cbb55-117">Démarrer les services</span><span class="sxs-lookup"><span data-stu-id="cbb55-117">Start services</span></span>
    
<span data-ttu-id="cbb55-118">Pour plus d’informations sur l’utilisation de l’Assistant Déploiement pour installer des composants, affecter des certificats et démarrer des services, voir Installer Skype Entreprise [Server 2015](../../deploy/install/install.md) et Installer Skype Entreprise [Server 2015](../../deploy/install/install-skype-for-business-server.md)sur les serveurs de la topologie.</span><span class="sxs-lookup"><span data-stu-id="cbb55-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

