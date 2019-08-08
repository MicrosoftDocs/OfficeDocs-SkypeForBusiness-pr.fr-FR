---
title: Empêcher l’exécution de sessions de services
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez utiliser le panneau de configuration pour les installations héritées pour empêcher de nouvelles sessions pour tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service hérité spécifique.
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244364"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="6ed8d-103">Empêcher l’exécution de sessions de services</span><span class="sxs-lookup"><span data-stu-id="6ed8d-103">Prevent sessions for services</span></span>

<span data-ttu-id="6ed8d-104">Vous pouvez utiliser le panneau de configuration pour les installations héritées pour empêcher de nouvelles sessions pour tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service hérité spécifique.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="6ed8d-105">Pour empêcher de nouvelles sessions pour les services sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="6ed8d-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="6ed8d-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="6ed8d-107">Ouvrez le panneau de configuration Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="6ed8d-108">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="6ed8d-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="6ed8d-109">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="6ed8d-110">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="6ed8d-111">Cliquez sur **empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="6ed8d-112">Pour empêcher de nouvelles sessions pour un service spécifique</span><span class="sxs-lookup"><span data-stu-id="6ed8d-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="6ed8d-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="6ed8d-114">Ouvrez le panneau de configuration Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="6ed8d-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="6ed8d-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="6ed8d-116">Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="6ed8d-117">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="6ed8d-118">Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="6ed8d-119">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="6ed8d-120">Cliquez sur **empêcher de nouvelles sessions pour le service**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="6ed8d-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="6ed8d-121">Click **Close**.</span></span>
    

