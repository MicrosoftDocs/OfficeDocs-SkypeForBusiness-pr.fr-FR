---
title: Ajouter un ordinateur frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool. Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie. Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir Définir et configurer un pool frontal dans la documentation de déploiement.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218315"
---
# <a name="add-front-end-machine"></a>Ajouter un ordinateur frontal

Indiquez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant que serveur frontal dans ce pool. Une fois l’ordinateur ajouté à cette liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant de publier la topologie. Une fois la topologie publiée, la modification du nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis l’ajout d’un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [Définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.

> [!IMPORTANT]
> Notez que le générateur de topologies indique que vous pouvez avoir jusqu’à 20 serveurs frontaux dans un pool. Le nombre maximal de serveurs pris en charge est de 12. Vous pouvez avoir jusqu’à 20 serveurs statefull définis dans le fabric, dont 12 peuvent être actifs et en ligne à tout moment.


