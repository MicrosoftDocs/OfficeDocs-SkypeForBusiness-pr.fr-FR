---
title: Service d’élément de tableau de bord qualité appel (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : En savoir plus sur le Service de l’article, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Service d’élément de tableau de bord qualité appel (CQD)
 
**Résumé :** Obtenir des informations sur le Service de l’article, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="item-service"></a>Service d’article

API de référentiel offre un service de gestion de contenu simple, connu en tant que service d’élément, qui peut être utilisé pour le stockage de contenu défini par l’application pour les utilisateurs. 
  
Le contenu du système est appartenant à l’utilisateur du système et partagé par tous les utilisateurs disposant d’un accès en lecture seule. Utilisateur dédié contenu appartiennent à des utilisateurs réguliers et seuls les propriétaires peuvent modifier ou les supprimer, mais tous les utilisateurs ont toujours accès en lecture seule.
  
> [!NOTE]
> Cette documentation de l’API traite des opérations en lecture seule de l’API de référentiel. 
  
Tableau de bord qualité appel enregistre des rapports et des requêtes en tant qu’éléments dans la base de données de référentiel. Un élément peut avoir des sous-éléments facultatifs, et appelez le tableau de bord qualité organise des rapports et des requêtes dans une structure hiérarchique à l’aide de la fonctionnalité de sous-éléments.
  
Service d’article comprend les concepts suivants :
  
- **Article** - l’élément de base du référentiel. Chaque élément est détenu par un seul utilisateur.
    
- **Sous-élément** - les mécanismes d’organisation de base du référentiel. Article peut y avoir zéro, un ou plusieurs des éléments subordonnés.
    
- **Ancêtres de l’élément** - la liste des éléments, en commençant à partir de l’élément au premier plan, qui est la valeur par défaut de l’élément de l’utilisateur, conduisant à un élément donné.
    
- **Contenu de l’élément** - le contenu spécifique à l’application stocké dans les éléments. Appel de tableau de bord qualité enregistre la représentation JSON des rapports et des requêtes dans le contenu.
    
Les opérations de repos sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir des éléments](get-items.md) <br/> |Obtenir les éléments retourne tous les éléments dans le référentiel.  <br/> |
|[Obtenir l’élément](get-item.md) <br/> |Obtenir élément renvoie un élément spécifique.  <br/> |
|[Obtenir des éléments de sous-menu](get-sub-items.md) <br/> |Obtenir les sous-éléments retourne les sous-éléments d’un élément spécifique.  <br/> |
|[Obtenir les ancêtres de l’élément](get-item-ancestors.md) <br/> |Ancêtres d’élément Get retourne les ancêtres d’un élément spécifique.  <br/> |
|[Élément de mise à jour](update-item.md) <br/> |Mettre à jour un élément spécifique dans le référentiel.  <br/> |
   

