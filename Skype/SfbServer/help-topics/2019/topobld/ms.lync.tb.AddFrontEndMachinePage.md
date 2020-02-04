---
title: Ajouter un ordinateur frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous voulez ajouter en tant que serveur frontal du pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Après la publication de la topologie, la modification du nom de domaine complet nécessite la suppression du serveur dans le générateur de topologie et l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir définir et configurer un pool frontal dans la documentation de déploiement.
ms.openlocfilehash: a11042c8d91089e74ab1bacfc5206eb7d2fa3f67
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689304"
---
# <a name="add-front-end-machine"></a>Ajouter un ordinateur frontal

Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous voulez ajouter en tant que serveur frontal du pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Après la publication de la topologie, la modification du nom de domaine complet nécessite la suppression du serveur dans le générateur de topologie et l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.

> [!IMPORTANT]
> Notez que le générateur de topologie indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool. Le nombre maximal de serveurs pris en charge est 12. Vous pouvez avoir jusqu’à 20 serveurs statefull définis dans le fabric, dont 12 peuvent être actifs et en ligne à un moment donné.


