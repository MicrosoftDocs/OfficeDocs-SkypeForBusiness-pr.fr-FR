---
title: Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé : Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4303d4cfc950ca7c57b7f16b31bc66e1ae711397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910353"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="e8b32-103">Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8b32-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8b32-104">**Résumé :** Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e8b32-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e8b32-105">Les services de conversation permanente et conformité de conversation permanente font partie de la Skype pour la topologie du serveur d’entreprise et peut donc être surveillés, arrêté et démarré à l’aide des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="e8b32-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e8b32-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="e8b32-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="e8b32-107">Renvoie des informations détaillées sur Skype pour les composants Business Server 2015 qui s’exécutent en tant que services Windows.</span><span class="sxs-lookup"><span data-stu-id="e8b32-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="e8b32-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="e8b32-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="e8b32-109">Démarre le service.</span><span class="sxs-lookup"><span data-stu-id="e8b32-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="e8b32-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="e8b32-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="e8b32-111">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="e8b32-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e8b32-112">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e8b32-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8b32-113">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="e8b32-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="e8b32-114">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="e8b32-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="e8b32-115">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e8b32-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="e8b32-116">Pour plus d’informations sur la manière d’utiliser les applets de commande, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e8b32-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

