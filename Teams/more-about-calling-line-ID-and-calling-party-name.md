---
title: Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: En savoir plus sur l’ID de ligne d’appel et le nom de l’appelant.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308313"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="396e0-103">Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel</span><span class="sxs-lookup"><span data-stu-id="396e0-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="396e0-104">CallerID se compose de deux éléments d’information :</span><span class="sxs-lookup"><span data-stu-id="396e0-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="396e0-105">Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel).</span><span class="sxs-lookup"><span data-stu-id="396e0-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="396e0-106">Nom de l’appelant (généralement appelé CNAM).</span><span class="sxs-lookup"><span data-stu-id="396e0-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="396e0-107">Lorsqu’un appel est effectué, la CLID (numéro de téléphone) est acheminée vers l’opérateur de destination (également appelé opérateur de terminaison).</span><span class="sxs-lookup"><span data-stu-id="396e0-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="396e0-108">Les informations du CNAM de l’appel peuvent ou non être acheminées avec l’appel, car ces informations dépendent de la façon dont le pays a implémenté le nom de la famille (le caser).</span><span class="sxs-lookup"><span data-stu-id="396e0-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="396e0-109">La fiabilité de la remise du CNAM avec l’appel varie selon le pays et les opérateurs qui gèrent l’appel, soit en tant qu’intermédiaire, soit en tant qu’opérateurs terminaux.</span><span class="sxs-lookup"><span data-stu-id="396e0-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="396e0-110">CLID & transmission CNAM est de la responsabilité de l’opérateur de terminaison.</span><span class="sxs-lookup"><span data-stu-id="396e0-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="396e0-111">L’opérateur de terminaison doit prendre en charge la & CNAM et fournir des enregistrements à jour pour les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="396e0-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="396e0-112">Microsoft fournit des valeurs CLID fiables lors des appels, mais ces valeurs peuvent ne pas être conservées intactes une fois qu’elles passent par un opérateur intermédiaire ou un opérateur de terminaison.</span><span class="sxs-lookup"><span data-stu-id="396e0-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="396e0-113">Si la valeur CLID est modifiée, omis ou tronquée par l’intermédiaire ou l’opérateur de terminaison, Microsoft n’a pas recours à la correction de tels problèmes dans le réseau téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="396e0-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="396e0-114">Des incohérences dans la mise à jour CNAM peuvent être provoquées lorsque les opérateurs intermédiaires ou terminaux retardent l’actualisation des informations CNAM dans les bases de données faisant autorité, comme c’est le cas pour les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="396e0-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="396e0-115">Dans les pays où il n’existe aucune base de données faisant autorité pour CNAM, les pratiques des opérateurs individuels peuvent également entraîner des problèmes au niveau des informations CNAM qui arrivent intacts lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="396e0-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="396e0-116">Microsoft ne prend pas en charge les informations de nom de famille en provenance dans les pays autres que les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="396e0-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="396e0-117">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="396e0-117">Related topics</span></span>


