---
title: Ajouter un ordinateur frontal
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant qu’un serveur frontal de ce pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Une fois que vous publiez la topologie, modification du nom complet nécessite la suppression du serveur dans le Générateur de topologie, puis en ajoutant un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir Define and Configure a Front End Pool dans la documentation de déploiement.
ms.openlocfilehash: ff12350f2c8ce7527fa619145fd03956191df936
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974888"
---
# <a name="add-front-end-machine"></a>Ajouter un ordinateur frontal
 
Spécifiez le nom de domaine complet (FQDN) de chaque ordinateur que vous souhaitez ajouter en tant qu’un serveur frontal de ce pool. Après avoir ajouté un ordinateur à la liste, vous pouvez mettre à jour le nom de domaine complet de l’ordinateur ou le supprimer du pool à tout moment avant la publication de la topologie. Une fois que vous publiez la topologie, modification du nom complet nécessite la suppression du serveur dans le Générateur de topologie, puis en ajoutant un nouveau serveur au pool avec le nouveau nom de domaine complet. Pour plus d’informations sur l’ajout d’un pool frontal à la topologie, voir [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.
  
> [!IMPORTANT]
> Notez que le Générateur de topologie indique que vous pouvez avoir jusqu'à 20 serveurs frontaux dans un pool. Le nombre maximal pris en charge de serveurs est 12. Vous pouvez avoir jusqu'à 20 serveurs menés définis dans le fabric, dont 12 peut être active et en ligne à tout moment. 
  

