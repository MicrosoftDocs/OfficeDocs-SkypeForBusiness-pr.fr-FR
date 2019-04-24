---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous créez. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous publiez la topologie contenant le pool frontal. Si vous avez besoin renommer un pool, vous devez supprimer le pool et puis ajoutez un nouveau pool avec le nouveau nom de domaine complet.
ms.openlocfilehash: 28e831df0cdf86620eefc1a22ced199507026c46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202060"
---
# <a name="add-front-end-pool-fqdn"></a>Ajouter le nom de domaine complet du pool frontal
 
Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous créez. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous publiez la topologie contenant le pool frontal. Si vous avez besoin renommer un pool, vous devez supprimer le pool et puis ajoutez un nouveau pool avec le nouveau nom de domaine complet.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool frontal à l’avenir, sélectionnez **pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre de pool frontal via le Skype pour l’Assistant de déploiement Business Server. Vous devez également ajouter le nouveau membre du pool les programmes d’équilibrage de charge approprié pour le pool, le nom de domaine DNS (Domain Name System) de l’équilibrage de charge ou les équilibreurs de charge matérielle. Dans la plupart des cas, vous auriez les deux systèmes en place d’équilibrage de charge. N’oubliez pas que vous ajoutez le nouveau serveur membre pour les deux. 
  

