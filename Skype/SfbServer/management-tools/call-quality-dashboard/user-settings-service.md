---
title: User Paramètres Service for Call Quality Dashboard (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé : Découvrez le service d’Paramètres utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: c037024c8fe336c3614dd9daf6ee02370337ad5c6c44b45c783044cc421f626f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315560"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>User Paramètres Service for Call Quality Dashboard (CQD)
 
**Résumé :** Découvrez le service d’Paramètres utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
Le service Paramètres utilisateur fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.
  
## <a name="user-settings-service"></a>Service de paramètres utilisateur

Les paramètres utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker des métadonnées à diverses fins, y compris la personnalisation des comportements d’application par utilisateur. Chaque utilisateur reçoit un stockage pour les paramètres utilisateur. Seuls les propriétaires peuvent ajouter, modifier et supprimer des paramètres utilisateur.
  
 **Paramètres globaux**
  
Les paramètres globaux sont les paramètres utilisateur de l’utilisateur système, et tous les utilisateurs y ont accès en lecture seule. Les paramètres globaux sont des constantes : ils sont créés lors de la création du référentiel et ne changent jamais.
  
Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés. Lorsque l’application demande les paramètres utilisateur effectifs, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, chaque paramètre utilisateur ayant pour effet de se supercaler au paramètre global respectif si les clés sont identiques. L’API peut également renvoyer uniquement les paramètres utilisateur afin que les applications trouvent les paramètres qui sont à la place. 
  
Les opérations REST sont incluses dans le tableau suivant.

|**Opération**|**Description**|
|:-----|:-----|
|[Obtention des paramètres utilisateur](get-user-settings.md) <br/> |Get User Paramètres renvoie la liste des paramètres d’un utilisateur spécifié.  <br/> |
|[Obtention d’un paramètre utilisateur](get-user-setting.md) <br/> |Obtenir le paramètre utilisateur renvoie un paramètre utilisateur unique.  <br/> |
   

