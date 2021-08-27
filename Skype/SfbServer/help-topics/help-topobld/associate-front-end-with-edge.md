---
title: Associer un pool frontal à un serveur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: Chaque pool frontal ne peut être associé qu’à un seul serveur Edge ou pool edge. Lorsque vous activez l’accès des utilisateurs externes pour un site, vous pouvez prendre en charge les utilisateurs distants. Vous pouvez également activer la prise en charge des utilisateurs fédérés, qui peut inclure la prise en charge des utilisateurs de fournisseurs de connectivité de messagerie instantanée publique spécifiques (tels que Windows Live) et la prise en charge des utilisateurs anonymes.
ms.openlocfilehash: 34b0cfe5fdfa7b98d37ff3a7458f3a4f4a59c534
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581408"
---
# <a name="associate-front-end-with-edge"></a>Associer un pool frontal à un serveur Edge

Chaque pool frontal ne peut être associé qu’à un seul serveur Edge ou pool edge. Lorsque vous activez l’accès des utilisateurs externes pour un site, vous pouvez prendre en charge les utilisateurs distants. Vous pouvez également activer la prise en charge des utilisateurs fédérés, qui peut inclure la prise en charge des utilisateurs de fournisseurs de connectivité de messagerie instantanée publique spécifiques (tels que Windows Live) et la prise en charge des utilisateurs anonymes.

Tous les pools d’un site et les pools de plusieurs sites centraux peuvent utiliser le même serveur Edge si l’utilisation ne dépasse pas la capacité du serveur Edge. Pour plus d’informations sur la surveillance, y compris la mise à l'échelle, voir [Planification de l’accès des utilisateurs externes](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) dans la documentation de planification. Pour plus d’informations sur la conception d’une topologie en vue de prendre en charge l’accès des utilisateurs externes, voir [Définir la topologie Edge](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) dans la documentation de déploiement.