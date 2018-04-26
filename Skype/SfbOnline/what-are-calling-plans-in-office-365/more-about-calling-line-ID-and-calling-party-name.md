---
title: Plus sur ID de la ligne appelante et le nom de partie de l’appel
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez pourquoi vous devez ajouter une personne qui peut apporter des modifications au compte lorsque vous utilisez l’Assistant Nouvelle commande de Port numéro Local.
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="75f03-103">Plus sur ID de la ligne appelante et le nom de partie de l’appel</span><span class="sxs-lookup"><span data-stu-id="75f03-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="75f03-104">CallerID, comme il est généralement désigné, se compose de deux éléments identifiables rencontrées par les utilisateurs d’informations :</span><span class="sxs-lookup"><span data-stu-id="75f03-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="75f03-105">Un numéro de téléphone (généralement appelé comme CLID ou en appelant les ID de ligne)</span><span class="sxs-lookup"><span data-stu-id="75f03-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="75f03-106">Appel de nom du tiers (généralement appelé CNAM) qui peut être de longueur jusqu'à 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="75f03-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="75f03-107">Lorsqu’un appel est effectué, le CLID (numéro de téléphone) est acheminé vers le support de destination (également connu sous le nom du transporteur de fin).</span><span class="sxs-lookup"><span data-stu-id="75f03-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="75f03-108">Les informations de CNAM de l’appel peuvent ou ne peuvent pas être routée avec l’appel que cela dépend de comment le pays a mis en œuvre CNAM (si).</span><span class="sxs-lookup"><span data-stu-id="75f03-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="75f03-109">La fiabilité de la livraison CNAM avec l’appel varie selon le pays et les transporteurs qui gèrent l’appel sous la forme d’un intermédiaire ou un transporteur de fin.</span><span class="sxs-lookup"><span data-stu-id="75f03-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="75f03-110">Transmission par CLID & CNAM est la responsabilité du transporteur fin, pour autant que le transporteur de fin doit prendre en charge les fonctionnalités CLID & CNAM ainsi que fournir des enregistrements à jour pour les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="75f03-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="75f03-111">Microsoft fournit les valeurs CLID de façon fiable lorsque les appels d’origine, mais que ces valeurs ne peuvent pas rester intactes une fois qu’ils traversent un transporteur intermédiaire ou de la fin du support.</span><span class="sxs-lookup"><span data-stu-id="75f03-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="75f03-112">Malheureusement, dans le cas du CLID, omise ou la valeur tronquée par le transporteur intermédiaire ou final, Microsoft n’a peu à aucun recours dans la correction de ces problèmes sur le réseau téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="75f03-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="75f03-113">Des incohérences dans les CNAM peuvent être dû à des retards dans les supports intermédiaires ou fin l’actualisation des informations CNAM dans des bases de données faisant autorités comme dans le cas des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="75f03-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="75f03-114">Dans les pays où il n’existe aucune base de données faisant autorité pour CNAM, pratiques du transporteur concerné peuvent également entraîner des problèmes avec les informations CNAM arrivant toucher avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="75f03-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="75f03-115">Microsoft n’autorise pas actuellement d’informations CNAM origine dans des pays autres que les États-Unis. »</span><span class="sxs-lookup"><span data-stu-id="75f03-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="75f03-116">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="75f03-116">Related topics</span></span>


