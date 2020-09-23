---
title: Expanseur des paramètres du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217155"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="391c4-105">Expanseur des paramètres du serveur d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="391c4-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="391c4-p102">La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="391c4-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="391c4-109">Dans la section **Résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="391c4-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="391c4-110">**Service utilisateur associé et pool de serveurs d’inscriptions de sauvegarde** Dans la liste déroulante, sélectionnez le pool frontal Enterprise Edition ou le serveur frontal Standard Edition qui doit agir comme serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="391c4-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="391c4-111">**Activer le basculement et la restauration automatique** Sélectionnez ce paramètre pour autoriser la détection automatique d’un serveur d’inscriptions défaillant et la détermination automatique du fait que le serveur d’inscriptions principal est sauvegardé et prêt à reprendre le processus de serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="391c4-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="391c4-112">**Intervalle de détection des échecs (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le serveur d’inscriptions principal a échoué.</span><span class="sxs-lookup"><span data-stu-id="391c4-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="391c4-113">La valeur par défaut est 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="391c4-113">The default value is 120 seconds.</span></span> <span data-ttu-id="391c4-114">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="391c4-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="391c4-115">**Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le serveur d’inscriptions principal est sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="391c4-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="391c4-116">La valeur par défaut est 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="391c4-116">The default value is 240 seconds.</span></span> <span data-ttu-id="391c4-117">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="391c4-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="391c4-p105">Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment. Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="391c4-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

