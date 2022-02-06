---
title: Schéma de base de données de conversation permanente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Cela documente le schéma de la base de données de conversation permanente dans Skype Entreprise Server.
---

# <a name="persistent-chat-database-schema"></a>Schéma de base de données de conversation permanente
 
Cela documente le schéma de la base de données de conversation permanente dans Skype Entreprise Server.
  
La base de données de conversation permanente fait référence à la base de données correspondant aux rôles serveur principal Skype Entreprise Server **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp). Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.
  
> [!IMPORTANT]
> Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié. 
  
Respectez les meilleures pratiques suivantes :
  
- Aucun select\* // n’est pris en charge, car la liste des colonnes peut croître.
    
- Aucune modification de schéma générée par l’utilisateur n’est prise en charge.
    
- Aucune opération d’écriture n’est prise en charge.
    
- Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.
    
## <a name="in-this-section"></a>Dans cette section

- [Liste des tables de serveur de conversation permanente](list-of-persistent-chat-server-tables.md)
    
- [Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Détails de la table des serveurs de conversation permanente](persistent-chat-server-table-details.md)
    
- [Exemples de requêtes de base de données de conversation permanente](sample-persistent-chat-database-queries.md)
    

