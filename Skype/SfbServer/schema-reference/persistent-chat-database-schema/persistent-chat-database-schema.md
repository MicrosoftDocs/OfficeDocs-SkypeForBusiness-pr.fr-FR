---
title: Schéma de base de données de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Cela documente le schéma de la base de données de conversation permanente dans Skype Entreprise Server.
ms.openlocfilehash: bc314413d2bb7a3d5916396f1e8f281d2217e9058d087dcec8bcc486ee7f172f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280927"
---
# <a name="persistent-chat-database-schema"></a>Schéma de base de données de conversation permanente
 
Cela documente le schéma de la base de données de conversation permanente dans Skype Entreprise Server.
  
La base de données de conversation permanente fait référence à la base de données correspondant aux rôles serveur principal Skype Entreprise Server **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp). Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.
  
> [!IMPORTANT]
> Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié. 
  
Respectez les meilleures pratiques suivantes :
  
- Aucun select \* // n’est pris en charge, car la liste des colonnes peut croître.
    
- Aucune modification de schéma générée par l’utilisateur n’est prise en charge.
    
- Aucune opération d’écriture n’est prise en charge.
    
- Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.
    
## <a name="in-this-section"></a>Contenu de cette section

- [Liste des tables de serveur de conversation permanente](list-of-persistent-chat-server-tables.md)
    
- [Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Détails de la table des serveurs de conversation permanente](persistent-chat-server-table-details.md)
    
- [Exemples de requêtes de base de données de conversation permanente](sample-persistent-chat-database-queries.md)
    

