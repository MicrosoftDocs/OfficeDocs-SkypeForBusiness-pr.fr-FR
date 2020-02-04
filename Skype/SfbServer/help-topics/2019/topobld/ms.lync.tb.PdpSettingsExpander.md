---
title: Expanseur des paramètres du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.
ms.openlocfilehash: 62d77de88a6bf0f0195e1c54eef4e5cac6d2a409
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701769"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="cb8d3-104">Expanseur des paramètres du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="cb8d3-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="cb8d3-p102">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau pour le contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb8d3-107">Vous pouvez utiliser le panneau de configuration ou les applets de commande de Management Shell pour activer le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="cb8d3-108">Dans la section **Définition du contrôle d’admission des appels** de la boîte de dialogue **Modifier les propriétés** de votre site, vous pouvez modifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="cb8d3-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="cb8d3-109">**Activer le contrôle d’admission des appels** Sélectionnez ce paramètre pour activer le CAC.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="cb8d3-110">Effacez ce paramètre pour désactiver le CAC pour l’ensemble de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="cb8d3-111">Pour activer le CAC, vous devez avoir configuré votre réseau pour le CAC.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="cb8d3-112">Pour plus d’informations, reportez-vous à la section [déploiement du contrôle d’admission des appels dans Skype entreprise Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="cb8d3-113">**Pool frontal pour exécuter le contrôle d’admission des appels** Si vous avez activé le CAC, vous pouvez modifier le pool qui s’exécute.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="cb8d3-114">Sélectionnez la liste déroulante dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cb8d3-114">Select the pool from the drop-down list.</span></span>
    

