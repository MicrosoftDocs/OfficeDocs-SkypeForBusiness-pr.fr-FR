---
title: Expanseur des paramètres SBA du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 48ba2f95cc5cae31d71727d5707120c608ffda6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104410"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="d1df5-103">Expandeur des paramètres SBA du serveur d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="d1df5-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="d1df5-104">Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1df5-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="d1df5-105">Sélectionnez **Pool de serveurs d’inscriptions de sauvegarde et service utilisateur associé** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d1df5-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="d1df5-106">Éventuellement, activez la case à cocher **Basculement et restauration automatiques pour Voice**.</span><span class="sxs-lookup"><span data-stu-id="d1df5-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="d1df5-p101">Configurez les options **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Par défaut, les intervalles sont de 120 secondes pour la détection d’échec Voice et de 240 secondes pour la restauration automatique Voice.</span><span class="sxs-lookup"><span data-stu-id="d1df5-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="d1df5-p102">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé afin de garantir le bon fonctionnement de la résilience. Si l’intervalle est trop faible (c’est-à-dire moins de 120 secondes) ou si le basculement et la restauration automatique sont définis de manière trop rapprochée, il peut en résulter un fonctionnement inattendu du basculement ou de la restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="d1df5-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="d1df5-111">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d1df5-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="d1df5-112">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d1df5-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="d1df5-113">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="d1df5-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1df5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1df5-114">See also</span></span>

[<span data-ttu-id="d1df5-115">Planification de la résilience Voix Entreprise de l’organisation</span><span class="sxs-lookup"><span data-stu-id="d1df5-115">Planning for Enterprise Voice Resiliency</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)