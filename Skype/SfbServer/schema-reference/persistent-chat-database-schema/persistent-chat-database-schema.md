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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874049"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="597ca-103">Schéma de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="597ca-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="597ca-104">Documente le schéma de la base de données de conversation permanente dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="597ca-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="597ca-105">La base de données de conversation permanente fait référence à la base de données correspondant à la Skype pour les rôles Business Server le serveur principal **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp).</span><span class="sxs-lookup"><span data-stu-id="597ca-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="597ca-106">L’objectif de publication de ce schéma est de vous permettent de créer des requêtes et d’obtenir une vue d’ensemble de création de rapports utiles autour d’utilisation de la conversation, salles actives, affiches supérieurs et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="597ca-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="597ca-107">Nous nous réservons le droit d’évoluer ce schéma.</span><span class="sxs-lookup"><span data-stu-id="597ca-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="597ca-108">Microsoft n’effectue pas les garanties pour maintenir la compatibilité descendante avec ce schéma publié.</span><span class="sxs-lookup"><span data-stu-id="597ca-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="597ca-109">Suivez ces meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="597ca-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="597ca-110">Aucun sélectionnez\* / / est prise en charge, car la liste des colonnes peut augmenter.</span><span class="sxs-lookup"><span data-stu-id="597ca-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="597ca-111">Aucune modification de schéma générée par l’utilisateur n’est prises en charge.</span><span class="sxs-lookup"><span data-stu-id="597ca-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="597ca-112">Aucune opération d’écriture n’est prises en charge.</span><span class="sxs-lookup"><span data-stu-id="597ca-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="597ca-113">Testez les requêtes que vous créez sur des bases de données représentatives dimensionnée pour vous assurer que les requêtes peuvent effectuer un niveau pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="597ca-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="597ca-114">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="597ca-114">In this section</span></span>

- [<span data-ttu-id="597ca-115">Liste des tables de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="597ca-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="597ca-116">Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="597ca-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="597ca-117">Détails de la table des serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="597ca-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="597ca-118">Exemples de requêtes de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="597ca-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

