---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093272"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="3fcf6-103">Définir une nouvelle jonction</span><span class="sxs-lookup"><span data-stu-id="3fcf6-103">Define a New Trunk</span></span>

<span data-ttu-id="3fcf6-104">Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3fcf6-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="3fcf6-105">**Nom de la jonction** : nom unique dans votre topologie qui identifiera cette jonction</span><span class="sxs-lookup"><span data-stu-id="3fcf6-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="3fcf6-106">**Passerelle PSTN associée** : sélectionnez dans la liste une passerelle PSTN déployée et configurée dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="3fcf6-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="3fcf6-p101">**Port d’écoute pour la passerelle IP/PSTN** : port que le système IP-PBX ou la passerelle PSTN écoutera. Doit être différent de tous les autres ports d’écoute de jonction configurés dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="3fcf6-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="3fcf6-109">**Protocole de transport SIP** : sélectionnez dans la liste soit TCP, soit TLS</span><span class="sxs-lookup"><span data-stu-id="3fcf6-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="3fcf6-110">**Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation qui est déployé et configuré dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="3fcf6-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="3fcf6-111">**Port du serveur** de médiation associé : définissez la valeur de port sur la valeur du port TCP ou TLS du serveur de médiation que cette trunk SIP utilisera</span><span class="sxs-lookup"><span data-stu-id="3fcf6-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="3fcf6-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fcf6-112">See also</span></span>

[<span data-ttu-id="3fcf6-113">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3fcf6-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="3fcf6-114">Comment implémenter une trunking SIP ?</span><span class="sxs-lookup"><span data-stu-id="3fcf6-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)