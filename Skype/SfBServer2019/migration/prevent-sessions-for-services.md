---
title: Empêcher l’exécution de sessions de services
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
description: Vous pouvez utiliser le panneau de configuration des installations héritées pour empêcher les nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher l’exécution de nouvelles sessions pour un service hérité spécifique.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752286"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="58fe7-103">Empêcher l’exécution de sessions de services</span><span class="sxs-lookup"><span data-stu-id="58fe7-103">Prevent sessions for services</span></span>

<span data-ttu-id="58fe7-104">Vous pouvez utiliser le panneau de configuration des installations héritées pour empêcher les nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher l’exécution de nouvelles sessions pour un service hérité spécifique.</span><span class="sxs-lookup"><span data-stu-id="58fe7-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="58fe7-105">Pour empêcher l’activation de nouvelles sessions pour les services sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="58fe7-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="58fe7-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="58fe7-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="58fe7-107">Ouvrez le panneau de configuration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="58fe7-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="58fe7-108">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="58fe7-109">Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="58fe7-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="58fe7-110">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="58fe7-111">Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="58fe7-112">Pour empêcher l’exécution de nouvelles sessions d’un service spécifique</span><span class="sxs-lookup"><span data-stu-id="58fe7-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="58fe7-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="58fe7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="58fe7-114">Ouvrez le panneau de configuration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="58fe7-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="58fe7-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="58fe7-116">Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="58fe7-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="58fe7-117">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="58fe7-118">Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.</span><span class="sxs-lookup"><span data-stu-id="58fe7-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="58fe7-119">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="58fe7-120">Cliquez sur **Empêcher de nouvelles sessions pour le service**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="58fe7-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="58fe7-121">Click **Close**.</span></span>
    

