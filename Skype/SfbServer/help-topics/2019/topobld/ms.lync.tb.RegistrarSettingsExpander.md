---
title: Expandeur des paramètres du serveur d’inscriptions avancé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La résilience fournit une haute disponibilité et une reprise après sinistre pour le pool d’inscriptions. En fournissant un bureau d’enregistrement de sauvegarde en cas d’échec du Bureau d’enregistrement principal, le Bureau d’enregistrement de sauvegarde peut prendre le contrôle du Bureau d’enregistrement en panne, ce qui permet aux utilisateurs de se connecter et de communiquer. Les utilisateurs peuvent bénéficier de fonctionnalités réduites, en fonction des systèmes ayant échoué avec le Bureau d’enregistrement principal.
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277838"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="b8062-105">Expandeur des paramètres du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="b8062-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="b8062-106">La résilience fournit une haute disponibilité et une reprise après sinistre pour le pool d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="b8062-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="b8062-107">En fournissant un bureau d’enregistrement de sauvegarde en cas d’échec du Bureau d’enregistrement principal, le Bureau d’enregistrement de sauvegarde peut prendre le contrôle du Bureau d’enregistrement en panne, ce qui permet aux utilisateurs de se connecter et de communiquer.</span><span class="sxs-lookup"><span data-stu-id="b8062-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="b8062-108">Les utilisateurs peuvent bénéficier de fonctionnalités réduites, en fonction des systèmes ayant échoué avec le Bureau d’enregistrement principal.</span><span class="sxs-lookup"><span data-stu-id="b8062-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="b8062-109">Dans la \*\*\*\* section résilience de la boîte de dialogue **modifier les propriétés** pour votre appareil de branche Survivable ou votre serveur de succursales survivant, vous pouvez modifier les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="b8062-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="b8062-110">**Service utilisateur associé et pool d’inscriptions de sauvegarde** Dans la liste déroulante, sélectionnez le serveur frontal Enterprise Edition ou le serveur frontal Standard Edition principal qui doit agir en tant que bureau d’enregistrement de sauvegarde de l’appareil de succursale survivant ou du serveur de succursales survivant.</span><span class="sxs-lookup"><span data-stu-id="b8062-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="b8062-111">**Activer le basculement et la restauration automatique** Sélectionnez ce paramètre pour activer la détection automatique d’un bureau d’enregistrement en échec et la détermination automatique du registre principal du Bureau d’enregistrement et la reprise du processus d’inscription.</span><span class="sxs-lookup"><span data-stu-id="b8062-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="b8062-112">**Intervalle de détection des échecs (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il ne soit déterminé que le Bureau d’enregistrement principal a échoué.</span><span class="sxs-lookup"><span data-stu-id="b8062-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="b8062-113">La valeur par défaut est 120 secondes.</span><span class="sxs-lookup"><span data-stu-id="b8062-113">The default value is 120 seconds.</span></span> <span data-ttu-id="b8062-114">Ce champ est obligatoire si vous sélectionnez **activer le basculement et la restauration automatique**.</span><span class="sxs-lookup"><span data-stu-id="b8062-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="b8062-115">**Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le Bureau d’enregistrement principal est sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="b8062-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="b8062-116">La valeur par défaut est 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="b8062-116">The default value is 240 seconds.</span></span> <span data-ttu-id="b8062-117">Ce champ est obligatoire si vous sélectionnez **activer le basculement et**la reprise.</span><span class="sxs-lookup"><span data-stu-id="b8062-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b8062-118">Lorsque vous définissez l’intervalle de détection d’échec et l’intervalle de détection de secours, veillez à ne pas entrer un intervalle qui entraînera le basculement et le basculement sur le point d’échec de réponse pour le Bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b8062-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="b8062-119">Il est possible que le Bureau d’enregistrement principal ne réponde pas pendant des périodes courtes en fonction du chargement du ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="b8062-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

