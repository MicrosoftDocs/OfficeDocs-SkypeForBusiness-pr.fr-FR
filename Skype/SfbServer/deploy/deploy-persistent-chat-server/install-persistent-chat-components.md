---
title: Installation des composants de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Résumé : Lisez cette rubrique pour savoir comment utiliser le Skype pour l’Assistant de déploiement Business Server pour installer Skype pour les services et composants Business Server 2015.'
ms.openlocfilehash: 78fb134ef8db5b0c47c890db9454858ff392a624
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222301"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="b2c48-103">Installation des composants de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b2c48-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b2c48-104">**Résumé :** Lisez cette rubrique pour savoir comment utiliser le Skype pour l’Assistant de déploiement Business Server pour installer Skype pour les services et composants Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b2c48-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="b2c48-105">Avant d’installer les composants de conversation permanente, veillez à avoir déjà installé les logiciels et le matériel requis et créé la topologie appropriée pour prendre en charge des serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b2c48-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="b2c48-106">Pour plus d’informations sur la planification et la configuration requise, voir [Configuration requise pour votre Skype pour un environnement d’entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) et à [planifier des serveurs de conversation permanente dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2c48-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="b2c48-107">Pour plus d’informations sur la façon de mettre à jour et publier votre topologie pour inclure des serveurs de conversation permanente, voir [Ajouter des serveurs de conversation permanente à votre Skype pour topologie Business Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2c48-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="b2c48-108">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b2c48-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b2c48-109">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="b2c48-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="b2c48-110">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="b2c48-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="b2c48-111">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b2c48-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="b2c48-112">Installation et démarrage des services</span><span class="sxs-lookup"><span data-stu-id="b2c48-112">Install and start services</span></span>

<span data-ttu-id="b2c48-113">À l’aide de la Skype pour l’Assistant de déploiement Business Server, cliquez sur Installer ou mise à jour Skype pour le système de serveur d’entreprise pour effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2c48-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="b2c48-114">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="b2c48-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="b2c48-115">Installer ou supprimer des composants Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b2c48-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="b2c48-116">Demander, installer ou assigner des certificats</span><span class="sxs-lookup"><span data-stu-id="b2c48-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="b2c48-117">Démarrer les services</span><span class="sxs-lookup"><span data-stu-id="b2c48-117">Start services</span></span>
    
<span data-ttu-id="b2c48-118">Pour plus d’informations sur la façon d’utiliser l’Assistant de déploiement pour installer les composants, assigner des certificats et démarrer les services, voir [Installer de Skype pour Business Server 2015](../../deploy/install/install.md) et [Installer le Skype pour Business Server 2015 sur les serveurs de la topologie](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2c48-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

