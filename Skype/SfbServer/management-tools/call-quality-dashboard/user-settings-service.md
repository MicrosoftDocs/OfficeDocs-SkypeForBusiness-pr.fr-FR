---
title: Service des paramètres utilisateur pour le tableau de bord de qualité des appels (bord)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé : en savoir plus sur le service des paramètres d’utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816643"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Service des paramètres utilisateur pour le tableau de bord de qualité des appels (bord)
 
**Résumé :** En savoir plus sur le service des paramètres d’utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="user-settings-service"></a>Service de paramètres utilisateur

Les paramètres utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker des métadonnées pour différentes raisons, notamment la personnalisation des comportements d’application par utilisateur. Chaque utilisateur reçoit un espace de stockage pour les paramètres utilisateur. Seuls les propriétaires peuvent ajouter, modifier et supprimer des paramètres utilisateur.
  
 **Paramètres globaux**
  
Les paramètres globaux sont les paramètres utilisateur appartenant à l’utilisateur système, et tous les utilisateurs y ont accès en lecture seule. Les paramètres globaux sont des constantes : elles sont créées lors de la création du référentiel et ne changent jamais.
  
Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés. Lorsque l’application demande les paramètres d’utilisateur efficaces, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, et chaque paramètre utilisateur remplace le paramètre global correspondant si les clés sont identiques. L’API peut également renvoyer uniquement les paramètres utilisateur de sorte que les applications puissent savoir quels paramètres sont remplacés. 
  
Les opérations REST sont comprises dans le tableau suivant.

|**Opération**|**Description**|
|:-----|:-----|
|[Obtention des paramètres utilisateur](get-user-settings.md) <br/> |Obtenir les paramètres d’utilisateur renvoie une liste de paramètres pour un utilisateur spécifié.  <br/> |
|[Obtention d’un paramètre utilisateur](get-user-setting.md) <br/> |Le paramètre Get est un paramètre utilisateur unique.  <br/> |
   

