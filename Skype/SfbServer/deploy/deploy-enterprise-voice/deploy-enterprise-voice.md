---
title: Déployer Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Résumé : Découvrez comment déployer Voix Entreprise pour Skype Entreprise Server sur un site central.'
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104970"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2df69-103">Déployer Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="2df69-104">**Résumé :** Découvrez comment déployer Voix Entreprise pour Skype Entreprise Server sur un site central.</span><span class="sxs-lookup"><span data-stu-id="2df69-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="2df69-105">Utilisez cette rubrique pour déployer des Voix Entreprise sur un site central.</span><span class="sxs-lookup"><span data-stu-id="2df69-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="2df69-106">Pour déployer Voix Entreprise site de succursale, passez [au déploiement des sites de succursale.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites)</span><span class="sxs-lookup"><span data-stu-id="2df69-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="2df69-107">Cette section inclut des procédures pour les déploiements dans lesquels un serveur de médiation est coqueté sur chaque serveur frontal ou serveur Standard Edition Server, comme recommandé, ainsi que pour les déploiements avec un pool de serveurs de médiation autonome. Vous pouvez ignorer le contenu suivant si vous avez utilisé le Générateur de topologie pour définir et publier une topologie qui colocate un serveur de médiation sur chaque serveur frontal ou serveur Standard Edition Server, car l’Assistant Déploiement a déjà installé automatiquement les fichiers pour le serveur de médiation lorsque vous avez installé des fichiers pour votre pool de serveurs frontaux ou votre serveur Standard Edition Server :</span><span class="sxs-lookup"><span data-stu-id="2df69-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="2df69-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2df69-108">In this section</span></span>

- [<span data-ttu-id="2df69-109">Conditions préalables de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="2df69-110">Déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="2df69-111">Définir une passerelle dans le Générateur de topologies dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="2df69-112">Définir des branches supplémentaires dans le Générateur de topologies dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="2df69-113">Installer les fichiers pour le serveur de médiation dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="2df69-114">Configurer des trunks dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="2df69-115">Créer ou modifier une règle de traduction pour la présentation de l’ID d’appelant dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="2df69-116">Créer ou modifier une règle de traduction pour la présentation de l’ID appelé dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="2df69-117">Créer ou modifier une règle de normalisation dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="2df69-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="2df69-118">Créer ou modifier un plan de numérotation dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="2df69-119">Configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="2df69-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="2df69-120">Activer les utilisateurs Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="2df69-121">Déployer des fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="2df69-122">Déploiement des fonctionnalités de gestion des appels dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="2df69-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="2df69-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2df69-123">See also</span></span>

[<span data-ttu-id="2df69-124">Planifier la Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2df69-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)