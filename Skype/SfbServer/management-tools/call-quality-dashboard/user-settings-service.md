---
title: Service de paramètres utilisateur pour le tableau de bord qualité appel (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé : En savoir plus sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: fe51c96546903e09f28ffadf06451efc8c1a88b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Service de paramètres utilisateur pour le tableau de bord qualité appel (CQD)
 
**Résumé :** Obtenir des informations sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="user-settings-service"></a>Service de paramètres utilisateur

Paramètres de l’utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker les métadonnées à diverses fins, notamment la personnalisation de chaque utilisateur de comportements application. Chaque utilisateur reçoit un stockage pour les paramètres utilisateur. Seuls les propriétaires peuvent ajouter, modifier et supprimer des paramètres de l’utilisateur.
  
 **Paramètres globaux**
  
Les paramètres globaux sont les paramètres de l’utilisateur appartenant à l’utilisateur du système et tous les utilisateurs ont accès en lecture seule. Les paramètres globaux sont des constantes : ils sont créés lors de la création du référentiel, et ils ne changent jamais.
  
Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés. Lorsque l’application demande les paramètres utilisateur efficace, l’API retourne un ensemble de paramètres globaux fusionnés avec les paramètres de l’utilisateur, avec chaque paramètre de l’utilisateur remplaçant le respectifs paramètre global si les clés sont les mêmes. L’API peut également retourner uniquement les paramètres de l’utilisateur afin que les applications peuvent déterminer quels paramètres sont substituées. 
  
Les opérations de repos sont incluses dans le tableau suivant.

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les paramètres de l’utilisateur](get-user-settings.md) <br/> |Paramètres d’utilisateur get retourne une liste de paramètres pour un utilisateur spécifié.  <br/> |
|[Obtenir les paramètres de l’utilisateur](get-user-setting.md) <br/> |Obtenir le paramètre utilisateur retourne un paramètre d’utilisateur unique.  <br/> |
   

