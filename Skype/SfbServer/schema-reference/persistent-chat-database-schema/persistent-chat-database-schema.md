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
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="1e55d-103">Schéma de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="1e55d-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="1e55d-104">Ce dossier de documents le schéma de la base de données Chat persistant dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e55d-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="1e55d-105">La base de données de conversation permanent fait référence à la base de données correspondant à la Skype pour les rôles d’entreprise serveur serveur principal **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données du mgccomp).</span><span class="sxs-lookup"><span data-stu-id="1e55d-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="1e55d-106">L’objectif de ce schéma de publication est pour vous permettre de créer des requêtes et d’obtenir une vue d’ensemble de création de rapports utiles autour de l’utilisation de la conversation, salles actives, affiches supérieur et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="1e55d-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e55d-107">Nous nous réservons le droit de faire évoluer ce schéma.</span><span class="sxs-lookup"><span data-stu-id="1e55d-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="1e55d-108">Microsoft ne rend pas les garanties pour assurer la compatibilité ascendante totale avec ce schéma publié.</span><span class="sxs-lookup"><span data-stu-id="1e55d-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="1e55d-109">Suivez ces recommandations :</span><span class="sxs-lookup"><span data-stu-id="1e55d-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="1e55d-110">Pas de sélection\* / est pris en charge, car la liste de colonnes peut augmenter.</span><span class="sxs-lookup"><span data-stu-id="1e55d-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="1e55d-111">Aucune modification de schéma de générés par l’utilisateur n’est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1e55d-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="1e55d-112">Aucune opération d’écriture n’est prises en charge.</span><span class="sxs-lookup"><span data-stu-id="1e55d-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="1e55d-113">Toutes les requêtes que vous générez sur dimensionné de manière représentative de bases de données pour vous assurer que les requêtes peuvent exécuter à un niveau pour répondre aux besoins de test.</span><span class="sxs-lookup"><span data-stu-id="1e55d-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="1e55d-114">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="1e55d-114">In this section</span></span>

- [<span data-ttu-id="1e55d-115">Liste des tables du serveur de conversation persistant</span><span class="sxs-lookup"><span data-stu-id="1e55d-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="1e55d-116">Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1e55d-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="1e55d-117">Détails de la table permanentes Chat Server</span><span class="sxs-lookup"><span data-stu-id="1e55d-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="1e55d-118">Exemples de requêtes de base de données Chat persistant</span><span class="sxs-lookup"><span data-stu-id="1e55d-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

