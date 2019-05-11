---
title: Configurer le contournement de média dans Skype pour le serveur d’entreprise pour toujours contourner le serveur de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activer le contournement de média pour toujours contourner le serveur de médiation dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: ffefeb9850915f4ac8e4677f1bcf0202c4f29405
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893139"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="12fcd-103">Configurer le contournement de média dans Skype pour le serveur d’entreprise pour toujours contourner le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="12fcd-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="12fcd-104">Activer le contournement de média pour toujours contourner le serveur de médiation dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="12fcd-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="12fcd-105">Si vous utilisez les étapes décrites dans cette rubrique pour configurer les paramètres globaux pour le média de contournement, il est supposé que vous avez vérifié la connectivité entre Skype pour systèmes d’extrémité Business et un homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.</span><span class="sxs-lookup"><span data-stu-id="12fcd-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="12fcd-106">Si vous n’avez pas vérifié la connectivité entre Skype pour systèmes d’extrémité Business et tous les homologues au serveur de médiation dont connexions de jonction respectifs ont été activées pour le contournement de média, vous devez configurer les paramètres de déviation du trafic multimédia globale pour utiliser les informations de site et de région Lorsque utilisant le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="12fcd-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="12fcd-107">Ainsi, pour plus de déterminer quand média contourne le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="12fcd-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="12fcd-108">Pour ce faire, utilisez les étapes décrites dans [les paramètres globaux dans Skype pour Business Server utilise des informations de site et de la région du contournement de média de configurer](use-site-and-region-information.md) et [d’associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="12fcd-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="12fcd-109">Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="12fcd-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="12fcd-110">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="12fcd-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="12fcd-111">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="12fcd-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="12fcd-112">Double-cliquez sur la configuration **Globale** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="12fcd-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="12fcd-113">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.</span><span class="sxs-lookup"><span data-stu-id="12fcd-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="12fcd-114">Cliquez sur **Toujours ignorer**.</span><span class="sxs-lookup"><span data-stu-id="12fcd-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="12fcd-115">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="12fcd-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12fcd-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12fcd-116">See also</span></span>

[<span data-ttu-id="12fcd-117">Planification du contournement de média dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="12fcd-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="12fcd-118">Déployer le contournement de média dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="12fcd-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

