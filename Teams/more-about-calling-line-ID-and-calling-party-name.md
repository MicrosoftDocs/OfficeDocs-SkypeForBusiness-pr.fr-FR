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
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel

L’ID de l’appelant, tel qu’il est généralement appelé, se compose en réalité de deux éléments d’information identifiables face à l’utilisateur :
    - Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel) 
    - Nom de l’appelant (généralement appelé CNAM) d’une longueur maximale de 15 caractères. 

Lorsqu’un appel est effectué, la CLID (numéro de téléphone) est acheminée vers l’opérateur de destination (également appelé opérateur de terminaison). Les informations du CNAM de l’appel peuvent ou non être acheminées avec l’appel, car cela dépend de la façon dont le pays a implémenté le nom CNAM (le caser). La fiabilité de la remise du CNAM avec l’appel varie selon le pays et les opérateurs qui gèrent l’appel en tant qu’intermédiaire et/ou en tant qu’opérateurs terminaux. 

CLID & Transmission CNAM est de la responsabilité de l’opérateur de terminaison, car celui-ci doit prendre en charge la fonctionnalité CLID & CNAM et fournir des enregistrements à jour pour les deux valeurs. Microsoft fournit des valeurs CLID fiables lors des appels, mais ces valeurs peuvent ne pas être conservées intactes une fois qu’elles passent par un opérateur intermédiaire ou un opérateur de terminaison. Malheureusement, en cas de changement, d’omis ou de tronquée de la valeur CLID par l’intermédiaire ou l’opérateur de terminaison, Microsoft n’a pas recours à la correction de tels problèmes sur le réseau téléphonique public.

Les incohérences dans la mise à jour CNAM peuvent être provoquées par des retards de mise à jour des opérateurs intermédiaires ou terminaux dans les bases de données faisant autorité, comme c’est le cas aux États-Unis. Dans les pays où il n’existe pas de base de données faisant autorité pour CNAM, les pratiques des opérateurs individuels peuvent également poser des problèmes avec les informations CNAM qui arrivent intacts lors de l’appel. Microsoft ne prend actuellement pas en charge les informations de nom de famille en provenance de pays autres que les États-Unis ».

## <a name="related-topics"></a>Sujets associés


