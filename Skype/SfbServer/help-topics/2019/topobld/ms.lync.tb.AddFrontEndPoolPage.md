---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.
ms.openlocfilehash: ee85c9223b780359ec86e927b93c591bdeaac944ca227b45969875fb19c63d22
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298524"
---
# <a name="add-front-end-pool-fqdn"></a>Ajouter le nom de domaine complet du pool frontal
 
Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool frontal par la suite, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau exécuter le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool frontal via l’Assistant Déploiement de Skype Entreprise Server. Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place. Veillez à ajouter le nouveau membre aux deux systèmes. 
  

