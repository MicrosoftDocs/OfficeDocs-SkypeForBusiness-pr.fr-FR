---
title: Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé : Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814134"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="8ac48-103">Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ac48-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ac48-104">**Résumé :** Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8ac48-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8ac48-105">Les services de conversation permanente et les services de conformité de conversation permanente font partie de la topologie Skype Entreprise Server et peuvent donc être surveillés, arrêtés et démarrés à l’aide des cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ac48-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8ac48-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8ac48-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8ac48-107">Retourne des informations détaillées sur les composants Skype Entreprise Server 2015 qui s’exécutent en tant que services Windows.</span><span class="sxs-lookup"><span data-stu-id="8ac48-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="8ac48-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8ac48-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8ac48-109">Démarre le service.</span><span class="sxs-lookup"><span data-stu-id="8ac48-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="8ac48-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8ac48-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8ac48-111">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="8ac48-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="8ac48-112">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8ac48-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8ac48-113">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8ac48-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="8ac48-114">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="8ac48-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="8ac48-115">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8ac48-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="8ac48-116">Pour plus d’informations sur l’utilisation des cmdlets, voir [Skype Entreprise Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="8ac48-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

