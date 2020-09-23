---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218555"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="70d03-103">Définir une nouvelle jonction</span><span class="sxs-lookup"><span data-stu-id="70d03-103">Define a New Trunk</span></span>

<span data-ttu-id="70d03-104">Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="70d03-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="70d03-105">**Nom de la jonction** : nom unique dans votre topologie qui identifiera cette jonction</span><span class="sxs-lookup"><span data-stu-id="70d03-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="70d03-106">**Passerelle PSTN associée** : sélectionnez dans la liste une passerelle PSTN déployée et configurée dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="70d03-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="70d03-p101">**Port d’écoute pour la passerelle IP/PSTN** : port que le système IP-PBX ou la passerelle PSTN écoutera. Doit être différent de tous les autres ports d’écoute de jonction configurés dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="70d03-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="70d03-109">**Protocole de transport SIP** : sélectionnez dans la liste soit TCP, soit TLS</span><span class="sxs-lookup"><span data-stu-id="70d03-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="70d03-110">**Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation déployé et configuré dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="70d03-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="70d03-111">**Port du serveur de médiation associé**: définissez la valeur de port sur la valeur de port TCP ou TLS du serveur de médiation que cette jonction SIP doit utiliser.</span><span class="sxs-lookup"><span data-stu-id="70d03-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="70d03-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70d03-112">See also</span></span>

[<span data-ttu-id="70d03-113">Jonction M :N dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="70d03-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="70d03-114">Comment implémenter la jonction SIP ?</span><span class="sxs-lookup"><span data-stu-id="70d03-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
