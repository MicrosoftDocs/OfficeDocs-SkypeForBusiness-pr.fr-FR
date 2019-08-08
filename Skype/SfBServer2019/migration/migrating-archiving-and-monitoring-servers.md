---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous avez déployé le serveur d’archivage et surveillé votre serveur dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement 2019 Skype entreprise Server après la migration de vos pools front-end. En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’ajouter l’archivage et la surveillance à votre liste de pilotes de pilotes 2019 Skype entreprise Server avant de procéder à la migration de manière à ce que la fonctionnalité soit disponible pendant le processus de migration.
ms.openlocfilehash: f259a08d25c93467c79fdaf3550288c6208607c3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237890"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="c4e8e-104">Migration des serveurs d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="c4e8e-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="c4e8e-105">Si vous avez déployé le serveur d’archivage et surveillé votre serveur dans votre environnement hérité, vous pouvez déployer ces serveurs dans votre environnement 2019 Skype entreprise Server après la migration de vos pools front-end.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="c4e8e-106">En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’ajouter l’archivage et la surveillance à votre liste de pilotes de pilotes 2019 Skype entreprise Server avant de procéder à la migration de manière à ce que la fonctionnalité soit disponible pendant le processus de migration.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="c4e8e-107">Si vous voulez utiliser les fonctionnalités d’archivage et de surveillance pendant le processus de migration, tenez compte des points suivants:</span><span class="sxs-lookup"><span data-stu-id="c4e8e-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="c4e8e-108">Les données d’archivage et de surveillance ne sont pas déplacées vers le déploiement 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="c4e8e-109">Les données que vous sauvegardez avant de désactiver l’environnement hérité seront votre historique d’activités dans l’environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="c4e8e-110">La version héritée du serveur d’archivage et de la surveillance du serveur peut être associée uniquement à un pool frontal hérité.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="c4e8e-111">Dans Skype entreprise Server 2019, l’archivage et la surveillance ne constituent plus de rôles de serveur, mais les services intégrés au pool frontal 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="c4e8e-112">Pendant la période de coexistence de vos déploiements d’anciens et de Skype entreprise Server 2019, la version héritée du serveur d’archivage et la surveillance du serveur collectent des données pour les utilisateurs hébergés sur des pools hérités.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="c4e8e-113">Archivage et surveillance dans Skype entreprise Server 2019 rassemblez les données des utilisateurs hébergés sur les pools 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4e8e-114">Pendant la phase de migration lorsque vous utilisez toujours votre serveur de bord traditionnel avec le nouveau Skype entreprise Server 2019, la version héritée du serveur d’archivage continue de rassembler les données pour les utilisateurs hébergés sur des listes héritées et l’archivage dans Skype entreprise. Server 2019 recueille des données pour les utilisateurs hébergés sur des pools 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="c4e8e-115">Si vous utilisez une solution tierce d’archivage et de surveillance conjointement avec l’archivage et la surveillance dans Skype entreprise Server 2019, contactez votre revendeur pour savoir quand et comment vous devez intégrer la solution tierce dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

