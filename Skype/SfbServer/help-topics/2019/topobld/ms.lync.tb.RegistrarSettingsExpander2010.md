---
title: Expanseur des paramètres du serveur d’inscriptions pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Modifier les paramètres de résilience et de configurer les propriétés suivantes :'
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="9b6b0-103">Expanseur des paramètres du serveur d’inscriptions pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9b6b0-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="9b6b0-104">Modifier les paramètres de **résilience** et de configurer les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b6b0-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="9b6b0-105">Sélectionnez le **pool de serveurs d’inscriptions de sauvegarde associé** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="9b6b0-106">Facultativement, activez la case à cocher **basculement automatique et restauration pour la voix** .</span><span class="sxs-lookup"><span data-stu-id="9b6b0-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="9b6b0-107">Configurer l' **intervalle de détection de panne voix (s)** et l' **intervalle de la restauration de voix (s)**.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="9b6b0-108">Par défaut, les intervalles sont 120 pour détecter une défaillance voix et 240 secondes pour la restauration automatique de la voix.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9b6b0-109">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration doit être testé avec soin pour vous assurer que la résilience fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="9b6b0-110">Définir l’intervalle à faible (autrement dit, moins de 120 secondes) ou le basculement et la restauration définir trop près peuvent entraîner le basculement réel et la restauration automatique ne fonctionne ne pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="9b6b0-111">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="9b6b0-112">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="9b6b0-113">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="9b6b0-113">**Help** Displays this help screen.</span></span>
  

