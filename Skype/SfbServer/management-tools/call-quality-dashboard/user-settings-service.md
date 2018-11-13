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
description: 'Résumé : En savoir plus sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 9e72d051699269b404d72e77ca00923b8ca240a3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293762"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Service de paramètres utilisateur pour le tableau de bord qualité appel (CQD)
 
**Résumé :** Obtenir des informations sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="user-settings-service"></a>Service de paramètres utilisateur

Paramètres de l’utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker les métadonnées à des fins diverses, notamment la personnalisation de l’application à la fois par utilisateur comportements. Chaque utilisateur reçoit un stockage pour les paramètres utilisateur. Seuls les propriétaires peuvent ajouter, modifier et supprimer les paramètres utilisateur.
  
 **Paramètres globaux**
  
Les paramètres globaux sont les paramètres utilisateur appartenant à l’utilisateur du système et tous les utilisateurs ont accès en lecture seule pour les. Les paramètres globaux sont des constantes : ils sont créés pendant la création du référentiel, et ils ne changent jamais.
  
Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés. Lorsque l’application demande les paramètres utilisateur effectif, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, avec chaque paramètre de l’utilisateur remplaçant la respectifs paramètre global si les clés sont les mêmes. L’API peut aussi renvoyer uniquement les paramètres utilisateur, afin que les applications peuvent savoir quels paramètres sont remplacés. 
  
Les opérations REST sont incluses dans le tableau suivant.

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les paramètres utilisateur](get-user-settings.md) <br/> |Obtenir les paramètres utilisateur renvoie une liste des paramètres pour un utilisateur spécifié.  <br/> |
|[Obtenir les paramètres utilisateur](get-user-setting.md) <br/> |Obtenir le paramètre utilisateur renvoie un paramètre d’utilisateur unique.  <br/> |
   

