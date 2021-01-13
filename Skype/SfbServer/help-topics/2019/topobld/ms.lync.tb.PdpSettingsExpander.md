---
title: Expanseur des paramètres du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.
ms.openlocfilehash: e05d4b480472289560c3d1f517e725fadf7288bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829914"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="bc673-104">Expandeur des paramètres du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="bc673-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="bc673-p102">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="bc673-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bc673-107">Vous pouvez également utiliser le panneau de contrôle ou les cmdlets de l’shell de gestion pour activer le contrôle d’accès au contrôle d’accès.</span><span class="sxs-lookup"><span data-stu-id="bc673-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="bc673-108">Dans la section **Définition du contrôle d’admission des appels** de la boîte de dialogue **Modifier les propriétés** de votre site, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bc673-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="bc673-109">**Activer le contrôle d’admission des appels** Sélectionnez ce paramètre pour activer le cac.</span><span class="sxs-lookup"><span data-stu-id="bc673-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="bc673-110">Désélectionnez ce paramètre pour désactiver le contrôle d’admission des appels pour tout votre réseau.</span><span class="sxs-lookup"><span data-stu-id="bc673-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="bc673-111">Pour activer le contrôle d’admission des appels, vous devez avoir configuré votre réseau pour le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="bc673-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="bc673-112">Pour plus d’informations, voir [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="bc673-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="bc673-113">**Pool frontal pour exécuter le contrôle d’admission des appels** Si vous avez activé le cac, vous pouvez modifier le pool qui l’exécute.</span><span class="sxs-lookup"><span data-stu-id="bc673-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="bc673-114">Sélectionnez le pool dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="bc673-114">Select the pool from the drop-down list.</span></span>
    

