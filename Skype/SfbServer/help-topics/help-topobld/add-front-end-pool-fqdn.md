---
title: Ajouter un Pool frontal nom de domaine complet
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Spécifiez le nom de domaine complet (FQDN) du pool Front-End que vous créez. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez supprimer le pool et puis ajouter un nouveau pool avec le nouveau nom de domaine complet.
ms.openlocfilehash: 73fce35786cdce2a39ebf2981b59a500991112f0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-pool-fqdn"></a>Ajouter un Pool frontal nom de domaine complet
 
Spécifiez le nom de domaine complet (FQDN) du pool Front-End que vous créez. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez supprimer le pool et puis ajouter un nouveau pool avec le nouveau nom de domaine complet.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool frontal à l’avenir, sélectionnez **plusieurs pool d’ordinateur**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologies pour définir le nouveau membre du pool, publiez la nouvelle topologie, puis configurer le nouveau membre du pool frontal via le Skype pour l’Assistant de déploiement de Business Server. Vous devez également ajouter le nouveau membre du pool pour les équilibreurs de charge approprié pour le pool, l’équilibrage de la charge système de nom de domaine (DNS) ou les équilibreurs de charge matériels. Dans de nombreux cas, vous aurez les deux systèmes d’équilibrage de la charge. Assurez-vous que vous ajoutez le nouveau serveur membre pour les deux. 
  

