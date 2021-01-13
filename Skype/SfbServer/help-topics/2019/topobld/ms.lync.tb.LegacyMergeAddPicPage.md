---
title: Fusion héritée
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Le Nom de domaine complet externe de conférence Web permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805704"
---
# <a name="legacy-merge"></a>Fusion héritée

Le **Nom de domaine complet externe de conférence Web** permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.

La valeur **443** du **Port externe de conférence Web externe** est le port TCP SIP (Transmission Control Protocol Session Initiation Protocol) configuré par défaut pour les clients de conférences. Si la valeur par défaut n'est pas utilisée, mettez à jour la valeur du **Port externe de conférence Web externe**.

Activez la case à cocher **Ce serveur Edge d’accès est utilisé pour la fédération et la solution PIC** si vous planifiez d’utiliser ce serveur Edge pour la fédération. Si vous disposez d’un déploiement de plusieurs serveurs Edge, un seul d’entre eux sera activé pour la fédération. Si vous n’activez pas cette case à cocher et que vous décidez d’activer une fédération ultérieurement, vous devez exécuter de nouveau l’Assistant Fusion du Générateur de topologies et publier votre topologie. Pour plus d’informations, voir [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


