---
title: Ajouter des associations au pool frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous pouvez activer la prise en charge pour des fonctionnalités spécifiques qui nécessitent le déploiement d’autres serveurs en associant maintenant les rôles serveur et les pools frontaux. Vous pouvez également associer les rôles serveur et le pool frontal ultérieurement. Les rôles serveur pouvant être associés à un pool frontal sont notamment les suivants :'
ms.openlocfilehash: 1a528fbeeabc4ca9a4c676a9f064b651c37298c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122655"
---
# <a name="add-front-end-associations"></a>Ajouter des associations au pool frontal

Vous pouvez activer la prise en charge pour des fonctionnalités spécifiques qui nécessitent le déploiement d’autres serveurs en associant maintenant les rôles serveur et les pools frontaux. Vous pouvez également associer les rôles serveur et le pool frontal ultérieurement. Les rôles serveur pouvant être associés à un pool frontal sont notamment les suivants :

- Serveur Edge A/V. Pour plus d’informations sur l’implémentation d’un serveur Edge A/V, voir [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) dans la documentation de planification.

> [!IMPORTANT]
> Si vous activez la prise en charge de l’une de ces fonctionnalités maintenant, la conception de la topologie que vous publiez comprendra les composants de serveur requis pour implémenter chaque fonctionnalité sélectionnée. Pour que la publication d’une topologie réussisse, les ordinateurs physiques doivent être joints au domaine. Par exemple, si vous activez la prise en charge de l’archivage maintenant, vous devez ensuite déployer un serveur d’archivage et configurer les options d’archivage appropriées avant de commencer l’archivage des communications pour votre organisation.