---
title: Expanseur des paramètres du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.
ms.openlocfilehash: cb7a5204b3b282c73f9440e61267b723b112b735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822114"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="42073-105">Expandeur des paramètres du serveur d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="42073-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="42073-p102">La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="42073-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="42073-109">Dans la section **Résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="42073-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="42073-110">**Service utilisateur associé et pool de sauvegarde du bureau d’enregistrement** Dans la liste de listes, sélectionnez le pool frontal Enterprise Edition ou le serveur frontal Standard Edition qui doit agir en tant que serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le Serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="42073-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="42073-111">**Activer le failover et la récupération** Sélectionnez ce paramètre pour permettre la détection automatique d’un échec du bureau d’enregistrement et la détermination automatique du fait que le bureau d’enregistrement principal est en cours de mise en service et prêt à reprendre le processus de bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="42073-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="42073-112">**Intervalle de détection d’échec (en secondes)** Tapez le nombre de secondes qui doivent s’écoulées avant de déterminer que le bureau d’enregistrement principal a échoué.</span><span class="sxs-lookup"><span data-stu-id="42073-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="42073-113">La valeur par défaut est 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="42073-113">The default value is 120 seconds.</span></span> <span data-ttu-id="42073-114">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="42073-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="42073-115">**Intervalle de détection de retour (s)** Tapez le nombre de secondes qui doivent s’écoulées avant qu’il soit déterminé que le bureau d’enregistrement principal est en cours de back up.</span><span class="sxs-lookup"><span data-stu-id="42073-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="42073-116">La valeur par défaut est 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="42073-116">The default value is 240 seconds.</span></span> <span data-ttu-id="42073-117">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="42073-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="42073-p105">Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment. Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="42073-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

