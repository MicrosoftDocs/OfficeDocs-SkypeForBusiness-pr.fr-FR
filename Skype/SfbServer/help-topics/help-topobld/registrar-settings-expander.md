---
title: Expander des paramètres de Registre
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Résilience fournit une haute disponibilité et reprise après sinistre pour le pool de Registrar. En fournissant une Registre de sauvegarde en cas de défaillance de l’agent d’enregistrement principal, la sauvegarde Registre peut prendre en charge pour le Registre a échoué, ce qui permet aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent potentiellement bénéficier des fonctionnalités réduites, selon les systèmes ont échoué dans le Registre principal.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="beb09-105">Expander des paramètres de Registre</span><span class="sxs-lookup"><span data-stu-id="beb09-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="beb09-106">Résilience fournit une haute disponibilité et reprise après sinistre pour le pool de Registrar.</span><span class="sxs-lookup"><span data-stu-id="beb09-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="beb09-107">En fournissant une Registre de sauvegarde en cas de défaillance de l’agent d’enregistrement principal, la sauvegarde Registre peut prendre en charge pour le Registre a échoué, ce qui permet aux utilisateurs de se connecter et communiquer.</span><span class="sxs-lookup"><span data-stu-id="beb09-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="beb09-108">Les utilisateurs peuvent potentiellement bénéficier des fonctionnalités réduites, selon les systèmes ont échoué dans le Registre principal.</span><span class="sxs-lookup"><span data-stu-id="beb09-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="beb09-109">Dans la section de la **résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou le serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="beb09-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="beb09-110">**Pool de sauvegarde Registre et de service associé à l’utilisateur** Dans la liste déroulante, sélectionnez le pool frontal de Enterprise Edition ou Standard Edition serveur frontal qui est d’agir en tant que la sauvegarde du Registre pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="beb09-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="beb09-111">**Activer le basculement et restauration automatique** Sélectionnez ce paramètre pour permettre la détection automatique d’un échec greffier et la détermination automatique qui le greffier principal est sauvegardée et prêt à reprendre le processus d’inscription.</span><span class="sxs-lookup"><span data-stu-id="beb09-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="beb09-112">**Intervalle de détection de défaillance (s)** Tapez le nombre de secondes qui doit s’écouler avant qu’il est déterminé que le principal Registre a échoué.</span><span class="sxs-lookup"><span data-stu-id="beb09-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="beb09-113">La valeur par défaut est de 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="beb09-113">The default value is 120 seconds.</span></span> <span data-ttu-id="beb09-114">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="beb09-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="beb09-115">**Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doit s’écouler avant qu’il est déterminé que le Registre principal est sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="beb09-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="beb09-116">La valeur par défaut est 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="beb09-116">The default value is 240 seconds.</span></span> <span data-ttu-id="beb09-117">Ce champ est obligatoire si vous sélectionnez **Activer le basculement et secours**.</span><span class="sxs-lookup"><span data-stu-id="beb09-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="beb09-118">Lorsque vous définissez l’intervalle de détection de panne et l’intervalle de détection de secours, être faites attention à ne pas entrer un intervalle qui entraîne le basculement et de secours pour se produire si le Registre ne répond pas pendant une courte période de temps.</span><span class="sxs-lookup"><span data-stu-id="beb09-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="beb09-119">Il est possible que le Registre principal peut ne pas répond pour courtes périodes de temps basée sur le chargement du pool ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="beb09-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

