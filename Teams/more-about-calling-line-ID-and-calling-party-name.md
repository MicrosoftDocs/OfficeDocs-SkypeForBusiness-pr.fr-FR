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
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Découvrez pourquoi vous devez ajouter une personne autorisée pouvant apporter des modifications au compte lorsque vous utilisez l’Assistant Nouvelle demande de transfert de numéros locaux.
ms.openlocfilehash: a687bc1aca8a47b349415d4a0cc2dc9f61f81884
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708800"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Plus d’informations sur le nom de l’appelant et l’ID de ligne d’appel

Appelant, car elle est généralement désignée, consiste en fait de deux éléments d’information identifiables par l’utilisateur :
    - Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel); 
    - Nom de l’appelant (généralement appelé CNAMe) qui peut comporter jusqu’à 15 caractères. 

Lors d’un appel, le CLID (numéro de téléphone) est routé vers l’opérateur de destination (également appelé opérateur de terminaison). Les informations CNAMe de l’appel sont susceptibles de ne pas être acheminées en fonction de l’appel, car le pays a implémenté CNAMe (le cas échéant). La fiabilité de la fourniture de CNAMe avec l’appel varie en fonction du pays et du transporteur qui gèrent l’appel en tant qu’intermédiaire et/ou opérateur de résiliation. 

Le CLID & transmission CNAMe incombe à l’opérateur de résiliation, dans la mesure où l’opérateur de résiliation doit prendre en charge le CLID & la fonctionnalité CNAMe et fournir des enregistrements à jour pour les deux valeurs. Microsoft fournit des valeurs de CLID lors des appels d’origine, mais ces valeurs ne peuvent pas être conservées intactes une fois transmises par le biais d’un transporteur intermédiaire ou du transporteur de terminaison. Malheureusement, en cas de modification de la valeur de l’élément CLID, qu’il ait été omis ou tronqué par l’intermédiaire du transporteur ou de l’arrêt du son, Microsoft ne peut pas être modifié dans le cadre de la résolution de ces problèmes sur le réseau téléphonique public.

Les incohérences dans CNAMe peuvent être provoquées par des retards dans les opérateurs intermédiaires ou de terminaison qui actualisent les informations CNAMe dans les bases de données faisant autorité, comme dans le cas des États-Unis. Dans les pays dans lesquels il n’existe aucune base de données faisant autorité pour CNAMe, des pratiques de transporteur individuelles peuvent également poser des problèmes avec les informations CNAMe qui arrivent de façon insuffisante lors de l’appel. Microsoft ne prend actuellement pas en charge les informations CNAMe d’origine dans les pays autres que les États-Unis.

## <a name="related-topics"></a>Rubriques connexes


