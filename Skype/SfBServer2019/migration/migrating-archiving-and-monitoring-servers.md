---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype Entreprise Server 2019 après avoir migré vos pools frontux. Toutefois, si les fonctionnalités d’archivage et de surveillance sont essentielles pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype Entreprise Server 2019 avant de migrer afin que la fonctionnalité soit disponible pendant le processus de migration.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752666"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="85372-104">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="85372-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="85372-105">Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement Skype Entreprise Server 2019 après avoir migré vos pools frontux.</span><span class="sxs-lookup"><span data-stu-id="85372-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="85372-106">Toutefois, si les fonctionnalités d’archivage et de surveillance sont essentielles pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool pilote Skype Entreprise Server 2019 avant de migrer afin que la fonctionnalité soit disponible pendant le processus de migration.</span><span class="sxs-lookup"><span data-stu-id="85372-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="85372-107">Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="85372-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="85372-108">Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement de Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="85372-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="85372-109">Les données que vous back up avant de désaffecter l’environnement hérité seront votre historique d’activité dans l’environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="85372-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="85372-110">La version héritée du serveur d’archivage et du serveur de surveillance peut être associée uniquement à un pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="85372-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="85372-111">Dans Skype Entreprise Server 2019, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="85372-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="85372-112">Pendant la coexistence de vos déploiements hérités et Skype Entreprise Server 2019, la version héritée du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs qui sont sur des pools hérités.</span><span class="sxs-lookup"><span data-stu-id="85372-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="85372-113">L’archivage et la surveillance dans Skype Entreprise Server 2019 collectent des données pour les utilisateurs qui sont homed on Skype for Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="85372-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85372-114">Au cours de la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Skype Entreprise Server 2019, la version héritée du serveur d’archivage continue de collecter des données pour les utilisateurs d’accueil sur des pools hérités et l’archivage dans Skype Entreprise Server 2019 collecte les données pour les utilisateurs qui sont sur des pools Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="85372-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="85372-115">Si vous utilisez une solution d’archivage et de surveillance tierce conjointement avec l’archivage et la surveillance dans Skype Entreprise Server 2019, consultez votre fournisseur pour savoir quand et comment intégrer la solution tierce à Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="85372-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

