---
title: Service d’élément de tableau de bord qualité appel (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : En savoir plus sur le Service de l’élément, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 5e5198afd95d6c9e1de517054053b724a54b1105
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035623"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Service d’élément de tableau de bord qualité appel (CQD)
 
**Résumé :** Obtenir des informations sur le Service de l’élément, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="item-service"></a>Service d’article

API de référentiel offre un service de gestion de contenu simple, appelé service d’élément, qui peut être utilisé pour le stockage de contenu défini par l’application pour les utilisateurs. 
  
Le contenu du système est détenus par l’utilisateur du système et partagé par tous les utilisateurs avec accès en lecture seule. Contenu utilisateur dédié appartiennent par les utilisateurs standard et seuls les propriétaires peuvent modifier ou supprimer les, mais tous les utilisateurs ont toujours accès en lecture seule pour les.
  
> [!NOTE]
> Cette documentation de l’API traite des opérations en lecture seule de l’API de référentiel. 
  
Tableau de bord qualité appel enregistre des rapports et des requêtes en tant qu’éléments dans la base de données de référentiel. Un élément peut avoir les sous-éléments facultatifs, et appelez le tableau de bord qualité organise des rapports et des requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.
  
Élément comprend les concepts suivants :
  
- **Élément** - l’élément de base du référentiel. Chaque élément appartient à un seul utilisateur.
    
- **Sous-élément** - les mécanismes d’organisation de base du référentiel. Élément peut avoir zéro, une ou plusieurs des éléments subordonnés.
    
- **Élément ancêtres** - la liste des éléments, en commençant à partir de l’élément de niveau supérieur, qui est la valeur par défaut de l’élément de l’utilisateur, conduisant à un élément donné.
    
- **Contenu de l’élément** - le contenu spécifique à l’application stocké dans les éléments. Tableau de bord qualité appel enregistre représentations JSON de rapports et de requêtes de contenu.
    
Les opérations REST sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Extraire des éléments](get-items.md) <br/> |Obtenir les éléments renvoie tous les éléments dans le référentiel.  <br/> |
|[Obtenir l’élément](get-item.md) <br/> |Obtenir élément renvoie un élément spécifique.  <br/> |
|[Obtenir les sous-éléments](get-sub-items.md) <br/> |Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.  <br/> |
|[Obtenir l’élément ancêtres](get-item-ancestors.md) <br/> |Get élément ancêtres renvoie ancêtres d’un élément spécifique.  <br/> |
|[Élément de la mise à jour](update-item.md) <br/> |Mettre à jour un élément spécifique dans le référentiel.  <br/> |
   

