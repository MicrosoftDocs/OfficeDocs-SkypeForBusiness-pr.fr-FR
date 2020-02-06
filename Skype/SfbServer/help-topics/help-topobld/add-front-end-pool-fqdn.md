---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous avez publié la topologie contenant le pool frontal. Si vous avez besoin de renommer un pool, vous devez supprimer le pool, puis ajouter un nouveau pool avec le nouveau nom de domaine complet (FQDN).
ms.openlocfilehash: efd37f67a04c932c740b231c12d81a55ee657ecf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820846"
---
# <a name="add-front-end-pool-fqdn"></a>Ajouter le nom de domaine complet du pool frontal
 
Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous avez publié la topologie contenant le pool frontal. Si vous avez besoin de renommer un pool, vous devez supprimer le pool, puis ajouter un nouveau pool avec le nouveau nom de domaine complet (FQDN).
  
> [!TIP]
> Si vous envisagez d’implémenter un pool frontal à l’avenir, sélectionnez **pool d’ordinateurs multiples**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez exécuter de nouveau le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie et configurer le nouveau membre du pool frontal par le biais de l’Assistant Déploiement de Skype entreprise Server. Vous devez également ajouter le nouveau membre de la liste aux équilibreurs de charge appropriés pour le pool, l’équilibrage de charge DNS (Domain Name System) ou les équilibreurs de charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de charge sont en place. Assurez-vous d’ajouter le nouveau serveur membre aux deux. 
  

