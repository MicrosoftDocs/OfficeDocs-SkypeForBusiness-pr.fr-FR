---
title: Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé: Découvrez comment démarrer, arrêter et surveiller les services de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279290"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="5b2fe-103">Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5b2fe-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5b2fe-104">**Résumé:** Découvrez comment démarrer, arrêter et surveiller les services de chat permanent dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5b2fe-105">Les services de chat permanent et de conformité des conversations permanent font partie de la topologie de Skype entreprise Server et peuvent donc être surveillés, arrêtés et démarrés en utilisant les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="5b2fe-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5b2fe-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="5b2fe-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="5b2fe-107">Renvoie des informations détaillées sur les composants de Skype entreprise Server 2015 qui s’exécutent en tant que services Windows.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="5b2fe-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="5b2fe-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="5b2fe-109">Démarre le service.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="5b2fe-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="5b2fe-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="5b2fe-111">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="5b2fe-112">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5b2fe-113">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="5b2fe-114">Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="5b2fe-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="5b2fe-115">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5b2fe-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="5b2fe-116">Pour plus d’informations sur la manière d’utiliser les applets de commande, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="5b2fe-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

