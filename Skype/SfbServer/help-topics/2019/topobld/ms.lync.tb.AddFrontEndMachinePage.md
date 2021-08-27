---
title: Ajouter un ordinateur frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool. Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie. Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir Définir et configurer un pool frontal dans la documentation de déploiement.
ms.openlocfilehash: f1624a2e8abbba455abf0982c33730d95235e1f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625406"
---
# <a name="add-front-end-machine"></a>Ajouter un ordinateur frontal

Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool. Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie. Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [Définir et configurer un pool frontal](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) dans la documentation de déploiement.

> [!IMPORTANT]
> Notez que le Générateur de topologie indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool. Le nombre maximal de serveurs pris en charge est de 12. Vous pouvez avoir jusqu’à 20 serveurs avec état définis dans la structure, dont 12 peuvent être actifs et en ligne à tout moment.