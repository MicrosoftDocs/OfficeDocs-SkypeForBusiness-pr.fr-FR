---
title: Fusion héritée
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Le Nom de domaine complet externe de conférence Web permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.
ms.openlocfilehash: 9e39d14ab59ab32e74162bdfa00447fddb68fa613fd33ccce445b11c0ae85ac6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333606"
---
# <a name="legacy-merge"></a>Fusion héritée

Le **Nom de domaine complet externe de conférence Web** permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.

La valeur **443** du **Port externe de conférence Web externe** est le port TCP SIP (Transmission Control Protocol Session Initiation Protocol) configuré par défaut pour les clients de conférences. Si la valeur par défaut n'est pas utilisée, mettez à jour la valeur du **Port externe de conférence Web externe**.

Activez la case à cocher **Ce pool de serveurs Edge est utilisé pour la fédération et la solution PIC (Public IM Connectivity)** si vous planifiez d’utiliser ce serveur Edge pour la fédération. Si vous disposez d’un déploiement de plusieurs serveurs Edge, un seul d’entre eux sera activé pour la fédération. Si vous n’activez pas cette case à cocher et que vous décidez d’activer une fédération ultérieurement, vous devez exécuter de nouveau l’Assistant Fusion du Générateur de topologie et publier votre topologie. Pour plus d’informations, voir [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).