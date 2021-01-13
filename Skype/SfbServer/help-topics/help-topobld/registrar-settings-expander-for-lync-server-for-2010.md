---
title: Expanseur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
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
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Vous modifiez les paramètres de résilience et configurez les propriétés suivantes :'
ms.openlocfilehash: 92df9deeba1287dab4dc7d84b089fa81ca2e51ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818324"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="321ec-103">Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="321ec-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="321ec-104">Vous modifiez les paramètres de **résilience** et configurez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="321ec-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="321ec-105">Sélectionnez **Pool de serveurs d’inscriptions de sauvegarde associé** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="321ec-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="321ec-106">Éventuellement, activez la case à cocher **Basculement et restauration automatiques pour Voice**.</span><span class="sxs-lookup"><span data-stu-id="321ec-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="321ec-p101">Configurez les options **Intervalle de détection d’échec Voice (en secondes)** et **Intervalle de restauration automatique Voice (en secondes)**. Par défaut, les intervalles sont de 120 secondes pour la détection d’échec Voice et de 240 secondes pour la restauration automatique Voice.</span><span class="sxs-lookup"><span data-stu-id="321ec-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="321ec-p102">Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration automatique doit être soigneusement testé afin de garantir le bon fonctionnement de la résilience. Si l’intervalle est trop faible (c’est-à-dire moins de 120 secondes) ou si le basculement et la restauration automatique sont définis de manière trop rapprochée, il peut en résulter un fonctionnement inattendu du basculement ou de la restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="321ec-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="321ec-111">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="321ec-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="321ec-112">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="321ec-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="321ec-113">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="321ec-113">**Help** Displays this help screen.</span></span>
  

