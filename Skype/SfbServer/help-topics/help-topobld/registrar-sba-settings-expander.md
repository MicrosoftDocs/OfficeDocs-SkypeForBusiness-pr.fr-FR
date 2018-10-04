---
title: Expanseur des paramètres du serveur d’inscriptions SBA
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Modifier les paramètres de résilience et de configurer les propriétés suivantes :'
ms.openlocfilehash: f4237972f271ed65e323d67637d9428631c9a899
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375877"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="1bcf8-103">Expanseur des paramètres du serveur d’inscriptions SBA</span><span class="sxs-lookup"><span data-stu-id="1bcf8-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="1bcf8-104">Modifier les paramètres de **résilience** et de configurer les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="1bcf8-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="1bcf8-105">Sélectionnez le **pool de serveurs d’inscriptions de sauvegarde et de service utilisateur associé** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="1bcf8-106">Facultativement, activez la case à cocher **basculement automatique et restauration pour la voix** .</span><span class="sxs-lookup"><span data-stu-id="1bcf8-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="1bcf8-107">Configurer l' **intervalle de détection de panne voix (s)** et l' **intervalle de la restauration de voix (s)**.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="1bcf8-108">Par défaut, les intervalles sont 120 pour détecter une défaillance voix et 240 secondes pour la restauration automatique de la voix.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="1bcf8-109">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration doit être testé avec soin pour vous assurer que la résilience fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="1bcf8-110">Définir l’intervalle à faible (autrement dit, moins de 120 secondes) ou le basculement et la restauration définir trop près peuvent entraîner le basculement réel et la restauration automatique ne fonctionne ne pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="1bcf8-111">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="1bcf8-112">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="1bcf8-113">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="1bcf8-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bcf8-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bcf8-114">See also</span></span>

[<span data-ttu-id="1bcf8-115">Planification de voix Entrerprise</span><span class="sxs-lookup"><span data-stu-id="1bcf8-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)