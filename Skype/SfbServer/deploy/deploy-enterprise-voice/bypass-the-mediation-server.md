---
title: Configurer l’exclusion de médias dans Skype entreprise Server pour ignorer toujours le serveur de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Activez le contournement multimédia pour ignorer toujours le serveur de médiation dans Skype entreprise Server Voice.
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275877"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5c950-103">Configurer l’exclusion de médias dans Skype entreprise Server pour ignorer toujours le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="5c950-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="5c950-104">Activez le contournement multimédia pour ignorer toujours le serveur de médiation dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="5c950-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="5c950-105">Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour le contournement du média multimédia, il est supposé que vous disposez d’une bonne connectivité entre les points de terminaison Skype entreprise et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.</span><span class="sxs-lookup"><span data-stu-id="5c950-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="5c950-106">Si vous n’avez pas de bonne connectivité entre les points de terminaison Skype entreprise et tous les homologues sur le serveur de médiation pour lesquels une connexion de ligne respective a été activée pour la dérivation de média, vous devez configurer des paramètres globaux de contournement de médias pour utiliser les informations relatives au site et à la région. lors de l’utilisation d’une dérivation de média.</span><span class="sxs-lookup"><span data-stu-id="5c950-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="5c950-107">Cela permet d’augmenter le contrôle lors du contournement du serveur de médiation par le média.</span><span class="sxs-lookup"><span data-stu-id="5c950-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="5c950-108">Pour cela, suivez les étapes décrites dans l’article [configurer les paramètres globaux de contournement de médias dans Skype entreprise Server pour utiliser les informations sur les sites et les régions](use-site-and-region-information.md) et [associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="5c950-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5c950-109">Pour activer la déviation du trafic multimédia au niveau global pour qu’il contourne toujours le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="5c950-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="5c950-110">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5c950-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5c950-111">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="5c950-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="5c950-112">Double-cliquez sur la configuration **Globale** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5c950-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="5c950-113">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.</span><span class="sxs-lookup"><span data-stu-id="5c950-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="5c950-114">Cliquez sur **Toujours ignorer**.</span><span class="sxs-lookup"><span data-stu-id="5c950-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="5c950-115">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5c950-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5c950-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c950-116">See also</span></span>

[<span data-ttu-id="5c950-117">Plan de contournement de médias dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="5c950-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="5c950-118">Déploiement du contournement multimédia dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5c950-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

