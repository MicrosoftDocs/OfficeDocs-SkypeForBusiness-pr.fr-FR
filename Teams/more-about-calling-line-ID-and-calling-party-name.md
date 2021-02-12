---
title: Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez pourquoi vous devez ajouter une personne autorisée qui peut apporter des modifications au compte lorsque vous utilisez l’Assistant Demande de nouveaux ports de numéro local.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255397"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="751d8-103">Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel</span><span class="sxs-lookup"><span data-stu-id="751d8-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="751d8-104">L’ID de l’appelant, tel qu’il est généralement appelé, se compose en réalité de deux éléments d’information identifiables face à l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="751d8-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="751d8-105">Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel)</span><span class="sxs-lookup"><span data-stu-id="751d8-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="751d8-106">Nom de l’appelant (généralement appelé CNAM) d’une longueur maximale de 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="751d8-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="751d8-107">Lorsqu’un appel est effectué, la CLID (numéro de téléphone) est acheminée vers l’opérateur de destination (également appelé opérateur de terminaison).</span><span class="sxs-lookup"><span data-stu-id="751d8-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="751d8-108">Les informations du CNAM de l’appel peuvent ou non être acheminées avec l’appel, car cela dépend de la façon dont le pays a implémenté le nom CNAM (le caser).</span><span class="sxs-lookup"><span data-stu-id="751d8-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="751d8-109">La fiabilité de la remise du CNAM avec l’appel varie selon le pays et les opérateurs qui gèrent l’appel en tant qu’intermédiaire et/ou en tant qu’opérateurs terminaux.</span><span class="sxs-lookup"><span data-stu-id="751d8-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="751d8-110">CLID & Transmission CNAM est de la responsabilité de l’opérateur de terminaison, car celui-ci doit prendre en charge la fonctionnalité CLID & CNAM et fournir des enregistrements à jour pour les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="751d8-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="751d8-111">Microsoft fournit des valeurs CLID fiables lors des appels, mais ces valeurs peuvent ne pas être conservées intactes une fois qu’elles passent par un opérateur intermédiaire ou un opérateur de terminaison.</span><span class="sxs-lookup"><span data-stu-id="751d8-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="751d8-112">Malheureusement, en cas de changement, d’omis ou de tronquée de la valeur CLID par l’intermédiaire ou l’opérateur de terminaison, Microsoft n’a pas recours à la correction de tels problèmes sur le réseau téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="751d8-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="751d8-113">Les incohérences dans la mise à jour CNAM peuvent être provoquées par des retards de mise à jour des opérateurs intermédiaires ou terminaux dans les bases de données faisant autorité, comme c’est le cas aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="751d8-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="751d8-114">Dans les pays où il n’existe pas de base de données faisant autorité pour CNAM, les pratiques des opérateurs individuels peuvent également poser des problèmes avec les informations CNAM qui arrivent intacts lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="751d8-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="751d8-115">Microsoft ne prend actuellement pas en charge les informations de nom de famille en provenance de pays autres que les États-Unis ».</span><span class="sxs-lookup"><span data-stu-id="751d8-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="751d8-116">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="751d8-116">Related topics</span></span>


