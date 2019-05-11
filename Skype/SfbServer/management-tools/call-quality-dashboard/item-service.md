---
title: Service d’élément de tableau de bord qualité appel (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : En savoir plus sur le Service de l’élément, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897498"
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
|[Obtenir des éléments](get-items.md) <br/> |Obtenir les éléments renvoie tous les éléments dans le référentiel.  <br/> |
|[Obtenir un élément](get-item.md) <br/> |Obtenir élément renvoie un élément spécifique.  <br/> |
|[Obtenir des sous-éléments](get-sub-items.md) <br/> |Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.  <br/> |
|[Obtenir les ancêtres d’élément](get-item-ancestors.md) <br/> |Get élément ancêtres renvoie ancêtres d’un élément spécifique.  <br/> |
|[Mettre à jour un élément](update-item.md) <br/> |Mettre à jour un élément spécifique dans le référentiel.  <br/> |
   

