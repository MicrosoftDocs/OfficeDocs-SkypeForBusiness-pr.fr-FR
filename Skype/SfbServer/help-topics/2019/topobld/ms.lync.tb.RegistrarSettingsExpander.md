---
title: Expandeur des paramètres du serveur d’inscriptions avancé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Résistance fournit une haute disponibilité et récupération d’urgence pour le pool de serveurs d’inscriptions. En fournissant une serveur d’inscriptions de sauvegarde en cas de défaillance d’inscriptions principale, la sauvegarde de serveurs d’inscriptions peut prendre en charge pour le serveur d’inscriptions ayant échoué, permettant aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent bénéficier potentiellement avec fonctionnalités réduites, selon lequel les systèmes ont échoué avec le serveur d’inscriptions principal.
ms.openlocfilehash: 0902c8490d650208c072ed7d2856738b9bd7f2c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906731"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="b856b-105">Expandeur des paramètres du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="b856b-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="b856b-106">Résistance fournit une haute disponibilité et récupération d’urgence pour le pool de serveurs d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="b856b-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="b856b-107">En fournissant une serveur d’inscriptions de sauvegarde en cas de défaillance d’inscriptions principale, la sauvegarde de serveurs d’inscriptions peut prendre en charge pour le serveur d’inscriptions ayant échoué, permettant aux utilisateurs de se connecter et communiquer.</span><span class="sxs-lookup"><span data-stu-id="b856b-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="b856b-108">Les utilisateurs peuvent bénéficier potentiellement avec fonctionnalités réduites, selon lequel les systèmes ont échoué avec le serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="b856b-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="b856b-109">Dans la section **résistance** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou un serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="b856b-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="b856b-110">**Pool de serveurs d’inscriptions de sauvegarde et de service utilisateur associé** Dans la liste déroulante, sélectionnez le pool frontal Enterprise Edition ou Standard Edition serveur frontal qui doit agir en tant que la sauvegarde du serveur d’inscriptions pour le Survivable Branch Appliance ou serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="b856b-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="b856b-111">**Activer le basculement et la restauration automatique** Sélectionnez cette option pour permettre la détection automatique Échec d’un serveur d’inscriptions et le calcul automatique du serveur d’inscriptions principal est sauvegardée et prêt à reprendre le processus de serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="b856b-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="b856b-112">**Intervalle de détection de panne (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il est déterminé que le serveur principal serveur d’inscriptions a échoué.</span><span class="sxs-lookup"><span data-stu-id="b856b-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="b856b-113">La valeur par défaut est 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="b856b-113">The default value is 120 seconds.</span></span> <span data-ttu-id="b856b-114">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="b856b-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="b856b-115">**Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il est déterminé que le serveur d’inscriptions principal est sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="b856b-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="b856b-116">La valeur par défaut est 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="b856b-116">The default value is 240 seconds.</span></span> <span data-ttu-id="b856b-117">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et secours**.</span><span class="sxs-lookup"><span data-stu-id="b856b-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b856b-118">Lorsque vous définissez l’intervalle de détection de panne et l’intervalle de détection de secours, être veiller à ne pas saisir un intervalle qui provoquera le basculement et de secours se produire si le serveur d’inscriptions ne répond pas pour un certain laps de temps.</span><span class="sxs-lookup"><span data-stu-id="b856b-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="b856b-119">Il est possible que le serveur d’inscriptions principal peut ne pas répond de courtes périodes de temps, basées sur le chargement du pool ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="b856b-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

