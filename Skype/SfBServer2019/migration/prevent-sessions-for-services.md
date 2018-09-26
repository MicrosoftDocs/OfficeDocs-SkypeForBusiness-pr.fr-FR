---
title: Empêcher les sessions de services
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez utiliser l’installation héritée le panneau de configuration afin d’empêcher de nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou de nouvelles sessions d’un service hérité.
ms.openlocfilehash: af4605f65d7cabe187696eda20bd9082ab73ad02
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027213"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="bb376-103">Empêcher les sessions de services</span><span class="sxs-lookup"><span data-stu-id="bb376-103">Prevent sessions for services</span></span>

<span data-ttu-id="bb376-104">Vous pouvez utiliser l’installation héritée le panneau de configuration afin d’empêcher de nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou de nouvelles sessions d’un service hérité.</span><span class="sxs-lookup"><span data-stu-id="bb376-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="bb376-105">Pour empêcher les nouvelles sessions de services sur un ordinateur</span><span class="sxs-lookup"><span data-stu-id="bb376-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="bb376-106">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bb376-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="bb376-107">Ouvrez Skype pour Business le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="bb376-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="bb376-108">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="bb376-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="bb376-109">Sur la page **état** du tri ou recherche par le biais de la liste en tant que nécessaire pour trouver l’ordinateur qui exécute les services pour laquelle vous souhaitez empêcher de nouvelles sessions, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="bb376-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="bb376-110">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="bb376-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="bb376-111">Cliquez sur **empêcher de nouvelles sessions pour tous les services**.</span><span class="sxs-lookup"><span data-stu-id="bb376-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="bb376-112">Pour empêcher les nouvelles sessions pour un service spécifique</span><span class="sxs-lookup"><span data-stu-id="bb376-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="bb376-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bb376-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="bb376-114">Ouvrez Skype pour Business le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="bb376-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="bb376-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="bb376-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="bb376-116">Sur la page **d’état** , de tri ou de recherche par le biais de la liste selon vos besoins pour rechercher l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="bb376-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="bb376-117">Cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bb376-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="bb376-118">Triez la liste des services, si nécessaire, cliquez sur le service pour lequel vous voulez empêcher de nouvelles sessions.</span><span class="sxs-lookup"><span data-stu-id="bb376-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="bb376-119">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="bb376-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="bb376-120">Cliquez sur **empêcher de nouvelles sessions de service**.</span><span class="sxs-lookup"><span data-stu-id="bb376-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="bb376-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="bb376-121">Click **Close**.</span></span>
    

