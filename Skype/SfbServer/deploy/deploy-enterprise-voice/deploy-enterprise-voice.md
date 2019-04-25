---
title: Déploiement d’Enterprise Voice dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Résumé : Découvrez comment déployer Enterprise Voice pour Skype pour Business Server sur un site central.'
ms.openlocfilehash: 463eb0a7fce174a33116bcb63f129aa59c8eba9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223119"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="fa059-103">Déploiement d’Enterprise Voice dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="fa059-104">**Résumé :** Apprenez à déployer Enterprise Voice pour Skype pour Business Server sur un site central.</span><span class="sxs-lookup"><span data-stu-id="fa059-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="fa059-105">Utilisez cette rubrique pour déployer Enterprise Voice sur un site central.</span><span class="sxs-lookup"><span data-stu-id="fa059-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="fa059-106">Pour déployer Enterprise Voice sur un site de succursale, passez à [Déployer des Sites de succursale](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa059-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="fa059-107">Cette section inclut des procédures pour les déploiements dans lesquels un serveur de médiation est colocalisé sur chaque serveur Standard Edition ou serveur frontal, comme indiqué, ainsi que pour les déploiements avec un pool de serveur de médiation autonome. Vous pouvez ignorer le contenu suivant si vous avez utilisé le Générateur de topologie pour définir et publier une topologie qui COLOCALISE un serveur de médiation sur chaque serveur Standard Edition ou serveur frontal, car l’Assistant Déploiement déjà installé automatiquement les fichiers Serveur de médiation lors de l’installation des fichiers de votre pool de serveurs frontaux ou le serveur Standard Edition server :</span><span class="sxs-lookup"><span data-stu-id="fa059-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="fa059-108">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="fa059-108">In this section</span></span>

- [<span data-ttu-id="fa059-109">Sécurité et configuration requises pour Enterprise Voice sur Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="fa059-110">Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="fa059-111">Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="fa059-112">Définition de jonctions supplémentaires dans le Générateur de topologie dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="fa059-113">Installer les fichiers pour le serveur de médiation dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="fa059-114">Configurer des jonctions Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="fa059-115">Créer ou modifier une règle de traduction pour la présentation des ID de l’appelant dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="fa059-116">Créer ou modifier une règle de traduction pour présentation ID appelée Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="fa059-117">Créer ou modifier une règle de normalisation dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="fa059-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="fa059-118">Créer ou modifier un plan de numérotation dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="fa059-119">Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="fa059-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="fa059-120">Activer les utilisateurs pour Enterprise Voice sur Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="fa059-121">Déployer les fonctionnalités voix entreprise dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa059-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="fa059-122">Déployer des fonctionnalités de gestion des appels dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="fa059-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="fa059-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa059-123">See also</span></span>

[<span data-ttu-id="fa059-124">Planifier Business Server pour Enterprise Voice sur Skype</span><span class="sxs-lookup"><span data-stu-id="fa059-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

