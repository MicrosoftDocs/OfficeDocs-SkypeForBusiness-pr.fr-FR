---
title: Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant
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
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865276"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant

CallerID, comme il est généralement appelée, se compose de deux éléments identifiables perçues par les utilisateurs des informations :
    - Un numéro de téléphone (généralement appelé comme CLID ou en appelant des ID de ligne) 
    - L’appel de nom (généralement appelé CNAM) qui peut être jusqu'à 15 caractères. 

Lorsqu’un appel est effectué, le CLID (numéro de téléphone) est dirigé vers l’opérateur de destination (également appelé l’opérateur fin). Les informations de CNAM pour l’appel peuvent ou peuvent être acheminées pas avec l’appel comme cela dépend comment le pays a implémenté CNAM (si). La fiabilité de livraison CNAM avec l’appel varie selon le pays et les opérateurs qui gère l’appel soit comme un intermédiaire et/ou un opérateur rencontrée. 

Transmission CLID & CNAM est la responsabilité de l’opérateur de fin dans la mesure où l’opérateur rencontrée doit prendre en charge les fonctionnalités CLID & CNAM ainsi que fournir des enregistrements à jour pour les deux valeurs. Microsoft fournit fiable valeurs CLID lorsque les appels d’origine, mais ces valeurs ne peuvent pas être conservées intactes une fois qu’ils transitent par un opérateur intermédiaire ou l’opérateur de fin. Malheureusement, la valeur CLID est modifiée, omise ou tronquée par l’opérateur intermédiaire ou de fin, Microsoft n’a peu recours à aucune Pour corriger ces problèmes dans le réseau téléphonique public.

Incohérences de CNAM peuvent être dû retards dans les opérateurs intermédiaires ou rencontrées l’actualisation des informations CNAM dans les bases de données faisant autorités comme dans le cas des États-Unis. Dans les pays où il n’y a aucune base de données faisant autorité pour CNAM, pratiques opérateur individuel peuvent également entraîner des problèmes avec les informations CNAM arrivant intacts avec l’appel. Microsoft n’autorise pas actuellement d’informations CNAM origine dans des pays autres que les États-Unis. »

## <a name="related-topics"></a>Rubriques connexes


