---
title: Fusion héritée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Le nom de domaine complet externe conférence Web permet aux utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence web du serveur Edge hérité.
ms.openlocfilehash: 3e426af0b08660eaef619d4fd9cec9da2ca11b32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919751"
---
# <a name="legacy-merge"></a>Fusion héritée

Le **nom de domaine complet externe conférence Web** permet aux utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence web du serveur Edge hérité.

La valeur du **port externe de conférence Web externe** **443** est le port du protocole TCP (Transmission Control) protocole SIP (Session Initiation) par défaut configuré pour les clients de conférence. Si la valeur par défaut n’est pas utilisée, mettre à jour la valeur du **port externe de conférence Web externe** .

Activez la case à cocher **Edge ce pool est utilisé pour la fédération et la connectivité PIC** si vous prévoyez d’utiliser ce serveur Edge pour la fédération. Si vous avez plusieurs serveurs de périphérie déployés, une seule d'entre elles sera activée pour la fédération. Si vous désactivez cette case et que vous décidez ultérieurement d’activer la fédération, vous devez réexécuter l’Assistant Fusion du Générateur de topologie, ainsi que publier votre topologie. Pour plus d’informations, voir [Phase 4 : fusionner les Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


