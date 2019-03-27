---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre Skype pour Business Server 2019 environnement après avoir fait migrer vos pools frontaux. Toutefois, si l’archivage et la fonctionnalité d’analyse sont critiques pour votre organisation, vous devez ajouter l’archivage et d’analyse à votre Skype pour le pool pilote Business Server 2019 avant de migrer afin que la fonctionnalité est disponible pendant le processus de migration.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896091"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="54504-104">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="54504-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="54504-105">Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre Skype pour Business Server 2019 environnement après avoir fait migrer vos pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="54504-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="54504-106">Toutefois, si l’archivage et la fonctionnalité d’analyse sont critiques pour votre organisation, vous devez ajouter l’archivage et d’analyse à votre Skype pour le pool pilote Business Server 2019 avant de migrer afin que la fonctionnalité est disponible pendant le processus de migration.</span><span class="sxs-lookup"><span data-stu-id="54504-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="54504-107">Si vous souhaitez que les fonctionnalités d’archivage et de surveillance au cours du processus de migration, gardez les points suivants à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="54504-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="54504-108">Données d’archivage et de données de surveillance ne sont pas déplacés vers le Skype pour le déploiement de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54504-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="54504-109">Les données à que sauvegarder avant de désactiver l’ancien environnement sera votre historique des activités dans l’ancien environnement.</span><span class="sxs-lookup"><span data-stu-id="54504-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="54504-110">La version héritée de serveur d’archivage et le serveur de surveillance peut être associée qu’avec un pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="54504-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="54504-111">Dans Skype pour Business Server 2019, d’archivage et de surveillance ne sont plus rôles de serveur, mais les services intégrés le Skype pour Business Server 2019 un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="54504-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="54504-112">Lors de la période que votre hérité et Skype pour les déploiements Business Server 2019 coexistent, la version héritée de serveur d’archivage et le serveur de surveillance recueillir des données pour les utilisateurs hébergés sur les pools hérités.</span><span class="sxs-lookup"><span data-stu-id="54504-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="54504-113">Archivage et surveillance dans Skype pour Business Server 2019 rassembler des données pour les utilisateurs hébergement sur Skype pour les pools d’entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54504-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54504-114">Pendant la phase de migration lorsque vous avez toujours à l’aide de votre serveur Edge hérité avec le nouveau Skype pour Business Server 2019 pool pilote, la version héritée de serveur d’archivage continue à recueillir des données pour les utilisateurs hébergé sur les pools hérités et archivage dans Skype pour les entreprises Serveur 2019 recueille des données pour les utilisateurs hébergement sur Skype pour les pools d’entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54504-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="54504-115">Si vous utilisez un tiers à l’archivage et surveillance solution conjointement avec archivage et de surveillance dans Skype pour Business Server 2019, consultez votre fournisseur quand et comment vous souhaitez intégrer la solution tierce avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="54504-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

