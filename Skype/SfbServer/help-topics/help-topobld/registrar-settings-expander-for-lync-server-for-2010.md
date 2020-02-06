---
title: Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: adc3d3f0be42d542583cf269a7acf83d98df8dd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819336"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="367e3-103">Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="367e3-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="367e3-104">Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="367e3-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="367e3-105">Dans la liste, sélectionnez **pool d’registraire de sauvegarde associé** .</span><span class="sxs-lookup"><span data-stu-id="367e3-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="367e3-106">Vous pouvez également activer la case à cocher **basculement et retour automatique pour la voix** .</span><span class="sxs-lookup"><span data-stu-id="367e3-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="367e3-107">Configurer l' **intervalle de détection de panne vocale (s)** et l’intervalle de restauration de la **voix (s)**.</span><span class="sxs-lookup"><span data-stu-id="367e3-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="367e3-108">Par défaut, les intervalles sont de 120 secondes pour la détection de la panne vocale et 240 secondes pour le rétablissement de la voix.</span><span class="sxs-lookup"><span data-stu-id="367e3-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="367e3-109">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé pour s’assurer que la résilience fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="367e3-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="367e3-110">Le fait de définir l’intervalle sur faible (c’est-à-dire inférieur à 120 secondes), le basculement et la restauration automatique risquent de provoquer le basculement réel et le rétablissement ne fonctionne pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="367e3-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="367e3-111">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="367e3-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="367e3-112">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="367e3-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="367e3-113">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="367e3-113">**Help** Displays this help screen.</span></span>
  

