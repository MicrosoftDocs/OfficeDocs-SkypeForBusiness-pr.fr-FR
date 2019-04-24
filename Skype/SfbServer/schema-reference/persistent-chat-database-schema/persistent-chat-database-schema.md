---
title: Schéma de base de données de conversation permanente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documente le schéma de la base de données de conversation permanente dans Skype pour Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212690"
---
# <a name="persistent-chat-database-schema"></a>Schéma de base de données de conversation permanente
 
Documente le schéma de la base de données de conversation permanente dans Skype pour Business Server.
  
La base de données de conversation permanente fait référence à la base de données correspondant à la Skype pour les rôles Business Server le serveur principal **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp). L’objectif de publication de ce schéma est de vous permettent de créer des requêtes et d’obtenir une vue d’ensemble de création de rapports utiles autour d’utilisation de la conversation, salles actives, affiches supérieurs et ainsi de suite.
  
> [!IMPORTANT]
> Nous nous réservons le droit d’évoluer ce schéma. Microsoft n’effectue pas les garanties pour maintenir la compatibilité descendante avec ce schéma publié. 
  
Suivez ces meilleures pratiques :
  
- Aucun sélectionnez\* / / est prise en charge, car la liste des colonnes peut augmenter.
    
- Aucune modification de schéma générée par l’utilisateur n’est prises en charge.
    
- Aucune opération d’écriture n’est prises en charge.
    
- Testez les requêtes que vous créez sur des bases de données représentatives dimensionnée pour vous assurer que les requêtes peuvent effectuer un niveau pour répondre à vos besoins.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Liste des tables de serveur de conversation permanente](list-of-persistent-chat-server-tables.md)
    
- [Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Détails de la table des serveurs de conversation permanente](persistent-chat-server-table-details.md)
    
- [Exemples de requêtes de base de données de conversation permanente](sample-persistent-chat-database-queries.md)
    

