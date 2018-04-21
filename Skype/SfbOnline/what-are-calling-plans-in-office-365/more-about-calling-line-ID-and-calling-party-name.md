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
ms.openlocfilehash: deb4320617d1840f2a237776ed0c4dc584fc2964
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Plus sur ID de la ligne appelante et le nom de partie de l’appel

CallerID, comme il est généralement désigné, se compose de deux éléments identifiables rencontrées par les utilisateurs d’informations :
    - Un numéro de téléphone (généralement appelé comme CLID ou en appelant les ID de ligne) 
    - Appel de nom du tiers (généralement appelé CNAM) qui peut être de longueur jusqu'à 15 caractères. 

Lorsqu’un appel est effectué, le CLID (numéro de téléphone) est acheminé vers le support de destination (également connu sous le nom de terminaison transporteur). Les informations de CNAM de l’appel peuvent ou ne peuvent pas être routée avec l’appel que cela dépend de comment le pays a mis en œuvre CNAM (si). La fiabilité de la livraison CNAM avec l’appel varie selon le pays et les transporteurs qui gèrent l’appel sous la forme d’un intermédiaire ou un transporteur de fin. 

Transmission par CLID & CNAM est la responsabilité du transporteur fin, pour autant que le transporteur de fin doit prendre en charge les fonctionnalités CLID & CNAM ainsi que fournir les enregistrements à jour des valeurs. Microsoft fournit les valeurs CLID de façon fiable lorsque les appels d’origine, mais que ces valeurs ne peuvent pas rester intactes une fois qu’ils traversent un transporteur intermédiaire ou de la fin du support. Malheureusement, dans le cas du CLID, omise ou la valeur tronquée par le transporteur intermédiaire ou final, Microsoft n’a peu à aucun recours dans la correction de ces problèmes sur le réseau téléphonique public.

Des incohérences dans les CNAM peuvent être dû à des retards dans les supports intermédiaires ou fin l’actualisation des informations CNAM dans des bases de données faisant autorités comme les États-Unis. Dans les pays où il n’existe aucune base de données faisant autorité pour CNAM, pratiques du transporteur concerné peuvent également entraîner des problèmes avec les informations CNAM arrivant toucher avec l’appel. Microsoft n’autorise pas actuellement d’informations CNAM origine dans des pays autres que les États-Unis. »

## <a name="related-topics"></a>Rubriques connexes


