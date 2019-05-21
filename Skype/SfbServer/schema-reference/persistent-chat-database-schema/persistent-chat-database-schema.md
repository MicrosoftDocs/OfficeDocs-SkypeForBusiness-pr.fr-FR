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
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Ce document décrit le schéma de la base de données de conversation permanente dans Skype entreprise Server.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295614"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="3dc9b-103">Schéma de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3dc9b-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="3dc9b-104">Ce document décrit le schéma de la base de données de conversation permanente dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="3dc9b-105">La base de données de chat permanent fait référence à la base de données qui correspond au rôle de serveur principal de Skype entreprise Server **PersistentChatStore** (correspondant à la base de données MGC) et **PersistentChatComplianceStore** (correspondant au mgccomp de base de données).</span><span class="sxs-lookup"><span data-stu-id="3dc9b-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="3dc9b-106">L’objectif de la publication de ce schéma consiste à vous permettre de créer des requêtes et d’accéder à des informations sur la création de rapports utiles sur l’utilisation des discussions, des salles actives, les principaux bureaux d’information, etc.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3dc9b-107">Nous nous réservons le droit d’évolutionr ce schéma.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="3dc9b-108">Microsoft n’apporte aucune garantie de conservation de la compatibilité descendante avec ce schéma publié.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="3dc9b-109">Suivez ces meilleures pratiques:</span><span class="sxs-lookup"><span data-stu-id="3dc9b-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="3dc9b-110">Aucune sélection\* //est prise en charge, car la liste de colonnes peut grandir.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="3dc9b-111">Aucune modification de schéma générée par l’utilisateur n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="3dc9b-112">Aucune opération d’écriture n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="3dc9b-113">Testez toutes les requêtes que vous créez sur des bases de données de taille représentative pour vous assurer que les requêtes peuvent être effectuées à un niveau en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="3dc9b-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="3dc9b-114">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="3dc9b-114">In this section</span></span>

- [<span data-ttu-id="3dc9b-115">Liste des tables de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3dc9b-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="3dc9b-116">Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3dc9b-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="3dc9b-117">Détails de la table des serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3dc9b-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="3dc9b-118">Exemples de requêtes de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3dc9b-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

