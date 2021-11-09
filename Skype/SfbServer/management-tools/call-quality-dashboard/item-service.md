---
title: Service d’élément pour le tableau de bord de qualité des appels (CQD)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : Découvrez le service d’élément, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 58d141930d98704eac101feb5d0fe8994284b587
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848437"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Service d’élément pour le tableau de bord de qualité des appels (CQD)
 
**Résumé :** Découvrez le service d’élément, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.
  
## <a name="item-service"></a>Service d’article

L’API de référentiel offre un service de gestion de contenu simple, appelé service d’élément, qui peut être utilisé pour stocker tout contenu défini par l’application pour les utilisateurs. 
  
Le contenu du système appartient à l’utilisateur système et est partagé par tous les utilisateurs avec un accès en lecture seule. Le contenu des utilisateurs dédiés appartient à des utilisateurs réguliers et seuls les propriétaires peuvent les modifier ou les supprimer, mais tous les utilisateurs y ont toujours accès en lecture seule.
  
> [!NOTE]
> Cette documentation de l’API couvre les opérations en lecture seule de l’API référentiel. 
  
Le Tableau de bord de qualité des appels enregistre les rapports et les requêtes en tant qu’éléments dans la base de données du référentiel. Un élément peut avoir des sous-éléments facultatifs, et le Tableau de bord de qualité des appels organise les rapports et les requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.
  
Le service d’élément comprend les concepts suivants :
  
- **Item** - élément de base du référentiel. Chaque élément appartient exactement à un utilisateur.
    
- **Sous-élément :** mécanismes d’organisation de base du référentiel. L’élément peut avoir zéro, un ou plusieurs éléments subordonnés.
    
- **Ancêtres** d’élément : liste des éléments, en commençant par l’élément le plus haut, qui est l’élément par défaut de l’utilisateur, menant à un élément donné.
    
- **Contenu d’élément** : contenu propre à l’application stocké dans les éléments. Le Tableau de bord de qualité des appels enregistre les représentations JSON des rapports et des requêtes dans le contenu.
    
Les opérations REST sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir des éléments](get-items.md) <br/> |Get Items renvoie tous les éléments du référentiel.  <br/> |
|[Obtenir un élément](get-item.md) <br/> |Obtenir l’élément renvoie un élément spécifique.  <br/> |
|[Obtenir des sous-éléments](get-sub-items.md) <br/> |Obtenir Sub-Items renvoie les sous-éléments d’un élément spécifique.  <br/> |
|[Obtenir les ancêtres d’élément](get-item-ancestors.md) <br/> |Obtenir des ancêtres d’élément renvoie les ancêtres d’un élément spécifique.  <br/> |
|[Mettre à jour un élément](update-item.md) <br/> |Mettez à jour un élément spécifique dans le référentiel.  <br/> |
   

