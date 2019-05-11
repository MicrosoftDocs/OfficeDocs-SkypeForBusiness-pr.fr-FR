---
title: Schéma de base de données de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documente le schéma de la base de données de conversation permanente dans Skype pour Business Server.
ms.openlocfilehash: 5e10f47a7eeb04de08766bae2957773db35d88f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930007"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="fa2a7-103">Schéma de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fa2a7-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="fa2a7-104">Documente le schéma de la base de données de conversation permanente dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="fa2a7-105">La base de données de conversation permanente fait référence à la base de données correspondant à la Skype pour les rôles Business Server le serveur principal **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp).</span><span class="sxs-lookup"><span data-stu-id="fa2a7-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="fa2a7-106">L’objectif de publication de ce schéma est de vous permettent de créer des requêtes et d’obtenir une vue d’ensemble de création de rapports utiles autour d’utilisation de la conversation, salles actives, affiches supérieurs et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa2a7-107">Nous nous réservons le droit d’évoluer ce schéma.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="fa2a7-108">Microsoft n’effectue pas les garanties pour maintenir la compatibilité descendante avec ce schéma publié.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="fa2a7-109">Suivez ces meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="fa2a7-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="fa2a7-110">Aucun sélectionnez\* / / est prise en charge, car la liste des colonnes peut augmenter.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="fa2a7-111">Aucune modification de schéma générée par l’utilisateur n’est prises en charge.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="fa2a7-112">Aucune opération d’écriture n’est prises en charge.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="fa2a7-113">Testez les requêtes que vous créez sur des bases de données représentatives dimensionnée pour vous assurer que les requêtes peuvent effectuer un niveau pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fa2a7-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="fa2a7-114">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="fa2a7-114">In this section</span></span>

- [<span data-ttu-id="fa2a7-115">Liste des tables de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fa2a7-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="fa2a7-116">Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fa2a7-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="fa2a7-117">Détails de la table des serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fa2a7-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="fa2a7-118">Exemples de requêtes de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fa2a7-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

