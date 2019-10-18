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
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez pourquoi vous devez ajouter une personne autorisée pouvant apporter des modifications au compte lorsque vous utilisez l’Assistant Nouvelle demande de transfert de numéros locaux.
ms.openlocfilehash: 833bb27aa34b16601485437be9e25e2e41c2bf4e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573378"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="f52b7-103">Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel</span><span class="sxs-lookup"><span data-stu-id="f52b7-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="f52b7-104">Appelant, car elle est généralement désignée, consiste en fait de deux éléments d’information identifiables par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="f52b7-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="f52b7-105">Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel);</span><span class="sxs-lookup"><span data-stu-id="f52b7-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="f52b7-106">Nom de l’appelant (généralement appelé CNAMe) qui peut comporter jusqu’à 15 caractères.</span><span class="sxs-lookup"><span data-stu-id="f52b7-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="f52b7-107">Lors d’un appel, le CLID (numéro de téléphone) est routé vers l’opérateur de destination (également appelé opérateur de terminaison).</span><span class="sxs-lookup"><span data-stu-id="f52b7-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="f52b7-108">Les informations CNAMe de l’appel sont susceptibles de ne pas être acheminées en fonction de l’appel, car le pays a implémenté CNAMe (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="f52b7-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="f52b7-109">La fiabilité de la fourniture de CNAMe avec l’appel varie en fonction du pays et du transporteur qui gèrent l’appel en tant qu’intermédiaire et/ou opérateur de résiliation.</span><span class="sxs-lookup"><span data-stu-id="f52b7-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="f52b7-110">Le CLID & transmission CNAMe incombe à l’opérateur de résiliation, dans la mesure où l’opérateur de résiliation doit prendre en charge le CLID & la fonctionnalité CNAMe et fournir des enregistrements à jour pour les deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="f52b7-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="f52b7-111">Microsoft fournit des valeurs de CLID lors des appels d’origine, mais ces valeurs ne peuvent pas être conservées intactes une fois transmises par le biais d’un transporteur intermédiaire ou du transporteur de terminaison.</span><span class="sxs-lookup"><span data-stu-id="f52b7-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="f52b7-112">Malheureusement, en cas de modification de la valeur de l’élément CLID, qu’il ait été omis ou tronqué par l’intermédiaire du transporteur ou de l’arrêt du son, Microsoft ne peut pas être modifié dans le cadre de la résolution de ces problèmes sur le réseau téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="f52b7-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="f52b7-113">Les incohérences dans CNAMe peuvent être provoquées par des retards dans les opérateurs intermédiaires ou de terminaison qui actualisent les informations CNAMe dans les bases de données faisant autorité, comme dans le cas des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="f52b7-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="f52b7-114">Dans les pays dans lesquels il n’existe aucune base de données faisant autorité pour CNAMe, des pratiques de transporteur individuelles peuvent également poser des problèmes avec les informations CNAMe qui arrivent de façon insuffisante lors de l’appel.</span><span class="sxs-lookup"><span data-stu-id="f52b7-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="f52b7-115">Microsoft ne prend actuellement pas en charge les informations CNAMe d’origine dans les pays autres que les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="f52b7-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="f52b7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f52b7-116">Related topics</span></span>


