---
title: Fusion héritée
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: 'NOINDEX, NOFOLLOW'
description: Le Nom de domaine complet externe de conférence Web permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.
---

# <a name="legacy-merge"></a>Fusion héritée

Le **Nom de domaine complet externe de conférence Web** permet à des utilisateurs externes de participer à des réunions sur site. Entrez le nom de domaine complet (FQDN) de l'interface de conférence Web externe du serveur Edge hérité.

La valeur **443** du **Port externe de conférence Web externe** est le port TCP SIP (Transmission Control Protocol Session Initiation Protocol) configuré par défaut pour les clients de conférences. Si la valeur par défaut n'est pas utilisée, mettez à jour la valeur du **Port externe de conférence Web externe**.

Activez la case à cocher **Ce pool de serveurs Edge est utilisé pour la fédération et la solution PIC (Public IM Connectivity)** si vous planifiez d’utiliser ce serveur Edge pour la fédération. Si vous disposez d’un déploiement de plusieurs serveurs Edge, un seul d’entre eux sera activé pour la fédération. Si vous n’activez pas cette case à cocher et que vous décidez d’activer une fédération ultérieurement, vous devez exécuter de nouveau l’Assistant Fusion du Générateur de topologie et publier votre topologie. Pour plus d’informations, voir [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).