---
title: Définir une nouvelle jonction
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous définissez une configuration de jonction nouvelle session initiation protocol (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: 9b237903239786737e194755ec69025a5f6a0478
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059041"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="32204-103">Définir une nouvelle jonction</span><span class="sxs-lookup"><span data-stu-id="32204-103">Define a New Trunk</span></span>
 
<span data-ttu-id="32204-104">Vous définissez une configuration de jonction nouvelle session initiation protocol (SIP) en fournissant les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32204-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>
  
- <span data-ttu-id="32204-105">**Nom de la jonction**: nom unique dans votre topologie qui identifiera cette jonction</span><span class="sxs-lookup"><span data-stu-id="32204-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>
    
- <span data-ttu-id="32204-106">**Passerelle de PSTN associée**: sélectionnez une passerelle PSTN déployée et configurée dans votre déploiement à partir de la liste</span><span class="sxs-lookup"><span data-stu-id="32204-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>
    
- <span data-ttu-id="32204-107">**Port d’écoute pour la passerelle IP/PSTN**: port d’écoute sur la passerelle IP-PBX ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="32204-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="32204-108">Doit être unique à partir de tous les autres ports d’écoute jonction configurés dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="32204-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>
    
- <span data-ttu-id="32204-109">**Protocole de Transport SIP**: sélectionnez dans la liste TCP ou TLS</span><span class="sxs-lookup"><span data-stu-id="32204-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>
    
- <span data-ttu-id="32204-110">**Serveur de médiation associé**: sélectionnez dans la liste d’un serveur de médiation qui est déployé et configuré dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="32204-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>
    
- <span data-ttu-id="32204-111">**Port du serveur de médiation associé**: définissez la valeur de port égale à la valeur du port TCP ou TLS du serveur de médiation cette jonction SIP utilisera</span><span class="sxs-lookup"><span data-stu-id="32204-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="32204-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32204-112">See also</span></span>

[<span data-ttu-id="32204-113">Jonction m : n dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="32204-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="32204-114">Implémentation d’une une jonction SIP</span><span class="sxs-lookup"><span data-stu-id="32204-114">How do I implement SIP trunking?</span></span>](http://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)