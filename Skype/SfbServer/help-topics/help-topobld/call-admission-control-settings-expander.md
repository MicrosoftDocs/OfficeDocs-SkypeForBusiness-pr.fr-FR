---
title: Expanseur des paramètres du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218785"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="57671-104">Expanseur des paramètres du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="57671-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="57671-p102">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="57671-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57671-107">Vous pouvez également utiliser le panneau de configuration ou les applets de commande Management Shell pour activer le contrôle d’admission des appel.</span><span class="sxs-lookup"><span data-stu-id="57671-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="57671-108">Dans la section **Définition du contrôle d’admission des appels** de la boîte de dialogue **Modifier les propriétés** de votre site, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="57671-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="57671-109">**Activer le contrôle d’admission des appels** Sélectionnez ce paramètre pour activer la fonctionnalité CAC.</span><span class="sxs-lookup"><span data-stu-id="57671-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="57671-110">Désélectionnez ce paramètre pour désactiver le contrôle d’admission des appels pour tout votre réseau.</span><span class="sxs-lookup"><span data-stu-id="57671-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="57671-111">Pour activer le contrôle d’admission des appels, vous devez avoir configuré votre réseau pour le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="57671-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="57671-112">Pour plus d’informations, reportez-vous à la rubrique [Deploy Call Admission Control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="57671-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="57671-113">**Pool frontal pour exécuter le contrôle d’admission des appels** Si vous avez activé le contrôle d’admission des connexions, vous pouvez modifier le pool qui l’exécute.</span><span class="sxs-lookup"><span data-stu-id="57671-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="57671-114">Sélectionnez le pool dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="57671-114">Select the pool from the drop-down list.</span></span>
    

