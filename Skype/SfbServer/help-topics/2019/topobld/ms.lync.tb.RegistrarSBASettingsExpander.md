---
title: Expandeur des paramètres SBA du serveur d’inscriptions avancé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 7eb90efde862b6326ea6f43f27937751ebff0ce9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797245"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="945a8-103">Expandeur des paramètres SBA du serveur d’inscriptions avancé</span><span class="sxs-lookup"><span data-stu-id="945a8-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="945a8-104">Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="945a8-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="945a8-105">Dans la liste **, sélectionnez service d’utilisateurs associé et pool d’inscriptions de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="945a8-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="945a8-106">Vous pouvez également activer la case à cocher **basculement et retour automatique pour la voix** .</span><span class="sxs-lookup"><span data-stu-id="945a8-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="945a8-107">Configurer l' **intervalle de détection de panne vocale (s)** et l’intervalle de restauration de la **voix (s)**.</span><span class="sxs-lookup"><span data-stu-id="945a8-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="945a8-108">Par défaut, les intervalles sont de 120 secondes pour la détection de la panne vocale et 240 secondes pour le rétablissement de la voix.</span><span class="sxs-lookup"><span data-stu-id="945a8-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="945a8-109">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé pour s’assurer que la résilience fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="945a8-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="945a8-110">Le fait de définir l’intervalle sur faible (c’est-à-dire inférieur à 120 secondes), le basculement et la restauration automatique risquent de provoquer le basculement réel et le rétablissement ne fonctionne pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="945a8-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="945a8-111">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="945a8-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="945a8-112">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="945a8-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="945a8-113">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="945a8-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="945a8-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="945a8-114">See also</span></span>

[<span data-ttu-id="945a8-115">Planification de la résilience vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="945a8-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
