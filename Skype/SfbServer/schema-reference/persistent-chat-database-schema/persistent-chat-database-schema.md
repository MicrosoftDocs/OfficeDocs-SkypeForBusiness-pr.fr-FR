---
title: Schéma de base de données de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Ce document décrit le schéma de la base de données de conversation permanente dans Skype entreprise Server.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814742"
---
# <a name="persistent-chat-database-schema"></a>Schéma de base de données de conversation permanente
 
Ce document décrit le schéma de la base de données de conversation permanente dans Skype entreprise Server.
  
La base de données de chat permanent fait référence à la base de données qui correspond au rôle de serveur principal de Skype entreprise Server **PersistentChatStore** (correspondant à la base de données MGC) et **PersistentChatComplianceStore** (qui correspond à la base de données mgccomp). L’objectif de la publication de ce schéma consiste à vous permettre de créer des requêtes et d’accéder à des informations sur la création de rapports utiles sur l’utilisation des discussions, des salles actives, les principaux bureaux d’information, etc.
  
> [!IMPORTANT]
> Nous nous réservons le droit d’évolutionr ce schéma. Microsoft n’apporte aucune garantie de conservation de la compatibilité descendante avec ce schéma publié. 
  
Suivez ces meilleures pratiques :
  
- Aucune sélection\* //est prise en charge, car la liste de colonnes peut grandir.
    
- Aucune modification de schéma générée par l’utilisateur n’est prise en charge.
    
- Aucune opération d’écriture n’est prise en charge.
    
- Testez toutes les requêtes que vous créez sur des bases de données de taille représentative pour vous assurer que les requêtes peuvent être effectuées à un niveau en fonction de vos besoins.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Liste des tables de serveur de conversation permanente](list-of-persistent-chat-server-tables.md)
    
- [Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Détails de la table des serveurs de conversation permanente](persistent-chat-server-table-details.md)
    
- [Exemples de requêtes de base de données de conversation permanente](sample-persistent-chat-database-queries.md)
    

