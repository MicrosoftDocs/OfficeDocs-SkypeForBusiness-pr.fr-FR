---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes:'
ms.openlocfilehash: c66d5999d6aa5bad0e9c16f8d466d82b941a630b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305920"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="9d767-103">Définir une nouvelle jonction</span><span class="sxs-lookup"><span data-stu-id="9d767-103">Define a New Trunk</span></span>

<span data-ttu-id="9d767-104">Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="9d767-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="9d767-105">**Nom du Trunk**: nom unique dans votre topologie qui identifie ce Trunk</span><span class="sxs-lookup"><span data-stu-id="9d767-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="9d767-106">**Passerelle RTC associée**: sélectionnez une passerelle PSTN déployée et configurée dans votre déploiement à partir de la liste.</span><span class="sxs-lookup"><span data-stu-id="9d767-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="9d767-107">**Port d’écoute pour la passerelle IP/PSTN**: port sur lequel le PBX IP ou la passerelle RTC écoutera.</span><span class="sxs-lookup"><span data-stu-id="9d767-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="9d767-108">Doit être unique à partir de tous les autres ports d’écoute de Trunk configurés dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="9d767-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="9d767-109">**Protocole de transport SIP**: effectuez une sélection dans la liste TCP ou TLS</span><span class="sxs-lookup"><span data-stu-id="9d767-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="9d767-110">**Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation déployé et configuré dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9d767-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="9d767-111">**Port du serveur de médiation associé**: définissez la valeur de port égale à la valeur de port TCP ou TLS du serveur de médiation que ce Trunk SIP utilisera.</span><span class="sxs-lookup"><span data-stu-id="9d767-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="9d767-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d767-112">See also</span></span>

[<span data-ttu-id="9d767-113">Jonction M:N dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9d767-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="9d767-114">Comment implémenter le trunking SIP?</span><span class="sxs-lookup"><span data-stu-id="9d767-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
