---
title: Ajouter une Machine de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant qu’un serveur frontal de ce pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Une fois que vous publiez la topologie, la modification de nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis en ajoutant un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir définir et configurer un Pool fin avant dans la documentation de déploiement.
ms.openlocfilehash: f4d8b197592a68cd3d19ba1bc2741b9f4743d19c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-machine"></a>Ajouter une Machine de Front-End
 
Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant qu’un serveur frontal de ce pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Une fois que vous publiez la topologie, la modification de nom de domaine complet nécessite la suppression du serveur dans le Générateur de topologies, puis en ajoutant un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [définir et configurer un Pool fin avant](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.
  
> [!IMPORTANT]
> Notez que le Générateur de topologies indique que vous pouvez avoir jusqu'à 20 serveurs frontaux dans un pool. Le nombre maximal de serveurs est 12. Vous pouvez avoir jusqu'à 20 serveurs menés définis dans le fabric, dont 12 peut être active et en ligne à tout moment. 
  

