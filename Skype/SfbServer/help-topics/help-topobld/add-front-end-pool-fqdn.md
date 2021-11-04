---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.
ms.openlocfilehash: f65b0903f8c64498ce8bd4eddad630e19a46a462
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776234"
---
# <a name="add-front-end-pool-fqdn"></a>Ajouter le nom de domaine complet du pool frontal
 
Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool frontal par la suite, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau exécuter le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool frontal via l’Assistant Déploiement de Skype Entreprise Server. Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place. Veillez à ajouter le nouveau membre aux deux systèmes. 
  

