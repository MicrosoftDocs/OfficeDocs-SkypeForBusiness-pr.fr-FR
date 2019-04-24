---
title: Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez pourquoi vous devez ajouter une personne qui peut modifier le compte lorsque vous utilisez l’Assistant Nouvel ordre de Port numéro Local.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229866"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="b9af7-103">Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel</span><span class="sxs-lookup"><span data-stu-id="b9af7-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="b9af7-104">CallerID, comme il est généralement appelée, se compose de deux éléments identifiables perçues par les utilisateurs des informations :</span><span class="sxs-lookup"><span data-stu-id="b9af7-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="b9af7-105">Un numéro de téléphone (généralement appelé comme CLID ou en appelant des ID de ligne)</span><span class="sxs-lookup"><span data-stu-id="b9af7-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="b9af7-106">L’appel de nom (généralement appelé CNAM) qui peut être jusqu'à 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="b9af7-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="b9af7-107">Lorsqu’un appel est effectué, le CLID (numéro de téléphone) est dirigé vers l’opérateur de destination (également appelé l’opérateur fin).</span><span class="sxs-lookup"><span data-stu-id="b9af7-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="b9af7-108">Les informations de CNAM pour l’appel peuvent ou peuvent être acheminées pas avec l’appel comme cela dépend comment le pays a implémenté CNAM (si).</span><span class="sxs-lookup"><span data-stu-id="b9af7-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="b9af7-109">La fiabilité de livraison CNAM avec l’appel varie selon le pays et les opérateurs qui gère l’appel soit comme un intermédiaire et/ou un opérateur rencontrée.</span><span class="sxs-lookup"><span data-stu-id="b9af7-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="b9af7-110">Transmission de CNAM & CLID est la responsabilité de l’opérateur de fin dans la mesure où l’opérateur rencontrée doit prendre en charge CLID & CNAM fonctionnalité ainsi que fournir des enregistrements à jour pour les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="b9af7-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="b9af7-111">Microsoft fournit fiable valeurs CLID lorsque les appels d’origine, mais ces valeurs ne peuvent pas être conservées intactes une fois qu’ils transitent par un opérateur intermédiaire ou l’opérateur de fin.</span><span class="sxs-lookup"><span data-stu-id="b9af7-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="b9af7-112">Malheureusement, la valeur CLID est modifiée, omise ou tronquée par l’opérateur intermédiaire ou de fin, Microsoft n’a peu recours à aucune Pour corriger ces problèmes dans le réseau téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="b9af7-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="b9af7-113">Incohérences de CNAM peuvent être dû retards dans les opérateurs intermédiaires ou rencontrées l’actualisation des informations CNAM dans les bases de données faisant autorités comme dans le cas des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="b9af7-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="b9af7-114">Dans les pays où il n’y a aucune base de données faisant autorité pour CNAM, pratiques opérateur individuel peuvent également entraîner des problèmes avec les informations CNAM arrivant intacts avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="b9af7-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="b9af7-115">Microsoft n’autorise pas actuellement d’informations CNAM origine dans des pays autres que les États-Unis. »</span><span class="sxs-lookup"><span data-stu-id="b9af7-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9af7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9af7-116">Related topics</span></span>


