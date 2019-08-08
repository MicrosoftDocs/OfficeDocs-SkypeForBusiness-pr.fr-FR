---
title: Déploiement de voix entreprise dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Résumé: Découvrez comment déployer Enterprise Voice pour Skype entreprise Server sur un site central.'
ms.openlocfilehash: 3e85ac96415788e8e15ba1ed11786864b6fc3124
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245426"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="a5c57-103">Déploiement de voix entreprise dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="a5c57-104">**Résumé:** Découvrez comment déployer Enterprise Voice pour Skype entreprise Server sur un site central.</span><span class="sxs-lookup"><span data-stu-id="a5c57-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="a5c57-105">Utilisez cette rubrique pour déployer Enterprise Voice sur un site central.</span><span class="sxs-lookup"><span data-stu-id="a5c57-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="a5c57-106">Pour déployer Enterprise Voice sur une succursale, passez à la partie [déploiement de sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)de succursales.</span><span class="sxs-lookup"><span data-stu-id="a5c57-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="a5c57-107">Cette section contient des procédures pour les déploiements dans lesquels un serveur de médiation est colocalisé sur chaque serveur frontal ou serveur Standard Edition, selon les recommandations et également pour les déploiements avec un pool de serveurs de médiation autonome. Vous pouvez ignorer le contenu suivant si vous avez utilisé le générateur de topologie pour définir et publier une topologie qui collocates un serveur de médiation sur chaque serveur frontal ou serveur Standard Edition, car l’Assistant déploiement a déjà installé automatiquement les fichiers pour Serveur de médiation lors de l’installation de fichiers pour votre pool de serveurs principal ou votre serveur Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="a5c57-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="a5c57-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="a5c57-108">In this section</span></span>

- [<span data-ttu-id="a5c57-109">Conditions préalables à la sécurité et à la configuration d’Enterprise voix dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="a5c57-110">Déploiement d’un serveur de médiation dans le générateur de topologies dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="a5c57-111">Définir une passerelle dans le générateur de topologies dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="a5c57-112">Définition de lignes supplémentaires dans le générateur de topologies de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="a5c57-113">Installer les fichiers du serveur de médiation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="a5c57-114">Configuration de Trunks dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="a5c57-115">Création ou modification d’une règle de traduction pour une présentation d’identification d’appelant dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="a5c57-116">Création ou modification d’une règle de traduction pour appeler une présentation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="a5c57-117">Création ou modification d’une règle de normalisation dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a5c57-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="a5c57-118">Création ou modification d’un plan de numérotation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="a5c57-119">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a5c57-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="a5c57-120">Activer les utilisateurs pour voix entreprise dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="a5c57-121">Déploiement de fonctionnalités avancées d’entreprise voix dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="a5c57-122">Déploiement de fonctionnalités de gestion des appels dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a5c57-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="a5c57-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5c57-123">See also</span></span>

[<span data-ttu-id="a5c57-124">Planifier l’entreprise voix dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a5c57-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

