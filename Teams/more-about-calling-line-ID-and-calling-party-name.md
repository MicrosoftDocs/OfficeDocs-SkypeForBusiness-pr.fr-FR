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
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel

CallerID se compose de deux éléments d’information :

- Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel).

- Nom de l’appelant (généralement appelé CNAM). 

Lorsqu’un appel est effectué, la CLID (numéro de téléphone) est acheminée vers l’opérateur de destination (également appelé opérateur de terminaison). Les informations du CNAM de l’appel peuvent ou non être acheminées avec l’appel, car ces informations dépendent de la façon dont le pays a implémenté le nom de la famille (le caser). La fiabilité de la remise du CNAM avec l’appel varie selon le pays et les opérateurs qui gèrent l’appel, soit en tant qu’intermédiaire, soit en tant qu’opérateurs terminaux. 

CLID & transmission CNAM est de la responsabilité de l’opérateur de terminaison. L’opérateur de terminaison doit prendre en charge la & CNAM et fournir des enregistrements à jour pour les deux valeurs. Microsoft fournit des valeurs CLID fiables lors des appels, mais ces valeurs peuvent ne pas être conservées intactes une fois qu’elles passent par un opérateur intermédiaire ou un opérateur de terminaison. Si la valeur CLID est modifiée, omis ou tronquée par l’intermédiaire ou l’opérateur de terminaison, Microsoft n’a pas recours à la correction de tels problèmes dans le réseau téléphonique public.

Des incohérences dans la mise à jour CNAM peuvent être provoquées lorsque les opérateurs intermédiaires ou terminaux retardent l’actualisation des informations CNAM dans les bases de données faisant autorité, comme c’est le cas pour les États-Unis. Dans les pays où il n’existe aucune base de données faisant autorité pour CNAM, les pratiques des opérateurs individuels peuvent également entraîner des problèmes au niveau des informations CNAM qui arrivent intacts lors de l’appel. Microsoft ne prend pas en charge les informations de nom de famille en provenance dans les pays autres que les États-Unis.

## <a name="related-topics"></a>Sujets associés


