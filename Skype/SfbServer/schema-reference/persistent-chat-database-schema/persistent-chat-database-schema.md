---
title: Schéma de base de données de conversation permanente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Ce dossier de documents le schéma de la base de données Chat persistant dans Skype pour Business Server.
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a>Schéma de base de données de conversation permanente
 
Ce dossier de documents le schéma de la base de données Chat persistant dans Skype pour Business Server.
  
La base de données de conversation permanent fait référence à la base de données correspondant à la Skype pour les rôles d’entreprise serveur serveur principal **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données du mgccomp). L’objectif de ce schéma de publication est pour vous permettre de créer des requêtes et d’obtenir une vue d’ensemble de création de rapports utiles autour de l’utilisation de la conversation, salles actives, affiches supérieur et ainsi de suite.
  
> [!IMPORTANT]
> Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne rend pas les garanties pour assurer la compatibilité ascendante totale avec ce schéma publié. 
  
Suivez ces recommandations :
  
- Pas de sélection\* / est pris en charge, car la liste de colonnes peut augmenter.
    
- Aucune modification de schéma de générés par l’utilisateur n’est pris en charge.
    
- Aucune opération d’écriture n’est prises en charge.
    
- Toutes les requêtes que vous générez sur dimensionné de manière représentative de bases de données pour vous assurer que les requêtes peuvent exécuter à un niveau pour répondre aux besoins de test.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Liste des tables du serveur de conversation persistant](list-of-persistent-chat-server-tables.md)
    
- [Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Détails de la table permanentes Chat Server](persistent-chat-server-table-details.md)
    
- [Exemples de requêtes de base de données Chat persistant](sample-persistent-chat-database-queries.md)
    

