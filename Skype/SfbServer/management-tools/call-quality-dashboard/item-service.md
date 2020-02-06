---
title: Service d’article pour le tableau de bord de qualité des appels (bord)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : en savoir plus sur le service des éléments, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816713"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Service d’article pour le tableau de bord de qualité des appels (bord)
 
**Résumé :** En savoir plus sur le service d’élément, qui fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="item-service"></a>Service d’article

L’API du référentiel propose un service de gestion de contenu simple, connu sous le nom de service des éléments, qui peut être utilisé pour stocker des contenus définis par l’application pour les utilisateurs. 
  
Le contenu du système appartient à l’utilisateur système et est partagé par tous les utilisateurs disposant d’un accès en lecture seule. Le contenu utilisateur dédié est possédé par des utilisateurs normaux et seuls les propriétaires peuvent modifier ou supprimer des éléments, mais tous les utilisateurs disposent toujours d’un accès en lecture seule.
  
> [!NOTE]
> Cette documentation sur les API décrit les opérations en lecture seule de l’API du référentiel. 
  
Le tableau de bord de qualité des appels enregistre des rapports et des requêtes en tant qu’éléments dans la base de données du référentiel. Un élément peut avoir des sous-éléments facultatifs et le tableau de bord de qualité des appels organise les rapports et les requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.
  
Le service des éléments inclut les concepts suivants :
  
- **Élément** : élément de base du référentiel. Chaque élément est possédé par un seul utilisateur.
    
- **Sous-élément** : la mécanique de base du référentiel. Un élément peut avoir zéro, un ou plusieurs éléments subordonnés.
    
- **Ancêtres d’élément** : liste d’éléments, à partir de l’élément le plus élevé, qui est l’élément par défaut de l’utilisateur, conduisant à un élément donné.
    
- **Contenu** de l’élément : contenu spécifique à l’application stocké dans les éléments. Le tableau de bord de qualité des appels enregistre les représentations JSON des rapports et des requêtes dans le contenu.
    
Les opérations REST sont comprises dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir des éléments](get-items.md) <br/> |Get renvoie tous les éléments du référentiel.  <br/> |
|[Obtenir un élément](get-item.md) <br/> |Obtenir renvoie un élément spécifique.  <br/> |
|[Obtenir des sous-éléments](get-sub-items.md) <br/> |L’option obtenir des sous-éléments renvoie les sous-éléments d’un élément spécifiques.  <br/> |
|[Obtenir les ancêtres d’élément](get-item-ancestors.md) <br/> |Obtient les ancêtres qui renvoient les ancêtres des éléments spécifiques.  <br/> |
|[Mettre à jour un élément](update-item.md) <br/> |Mettre à jour un élément spécifique du référentiel.  <br/> |
   

