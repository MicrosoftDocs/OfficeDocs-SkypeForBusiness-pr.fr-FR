---
title: Déploiement de Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Résumé : Apprenez à déployer des Voix Entreprise pour Skype pour 2015 de serveur d’entreprise sur un site central.'
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="7025c-103">Déploiement de Voix Entreprise dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7025c-104">**Résumé :** Apprenez à déployer des Voix Entreprise pour Skype pour 2015 de serveur d’entreprise sur un site central.</span><span class="sxs-lookup"><span data-stu-id="7025c-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="7025c-105">Utilisez cette rubrique pour le déploiement de Voix Entreprise dans un site central.</span><span class="sxs-lookup"><span data-stu-id="7025c-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="7025c-106">Pour déployer la Voix Entreprise sur un site de la succursale, passez à [Déployer des Sites de succursales](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="7025c-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="7025c-107">Cette section inclut des procédures pour les déploiements dans lequel un serveur de médiation se trouve sur chaque serveur serveur frontal ou Standard Edition, comme recommandé et également pour les déploiements avec un pool de serveur de médiation autonome. Vous pouvez ignorer le contenu suivant si vous avez utilisé le Générateur de topologies pour définir et publier une topologie qui collocates un serveur de médiation sur chaque serveur Standard Edition ou de serveur frontal, car l’Assistant Déploiement installé déjà automatiquement les fichiers pour Serveur de médiation lorsque vous avez installé les fichiers pour votre pool de serveur frontal ou un serveur Standard Edition server :</span><span class="sxs-lookup"><span data-stu-id="7025c-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="7025c-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="7025c-108">In this section</span></span>

- [<span data-ttu-id="7025c-109">Conditions préalables à la configuration et de sécurité pour les Voix Entreprise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="7025c-110">Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="7025c-111">Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="7025c-112">Définir des troncs supplémentaires dans le Générateur de topologie dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="7025c-113">Installer les fichiers de serveur de médiation dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="7025c-114">Configurer des puits dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="7025c-115">Créer ou modifier une règle de traduction pour une présentation des ID de l’appelant dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="7025c-116">Créer ou modifier une règle de traduction appelé ID présentation dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="7025c-117">Créer ou modifier une règle de normalisation dans Skype pour entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="7025c-118">Créer ou modifier un plan de numérotation dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="7025c-119">Configurer les stratégies de voix, les enregistrements d’utilisation de TLS et les itinéraires de voix dans Skype pour entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="7025c-120">Permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="7025c-121">Déployer des fonctionnalités avancées de Voix Entreprise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="7025c-122">Déployer des fonctionnalités de gestion d’appel dans Skype pour entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="7025c-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7025c-123">See also</span></span>

#### 

[<span data-ttu-id="7025c-124">Plan de Voix Entreprise dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7025c-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

