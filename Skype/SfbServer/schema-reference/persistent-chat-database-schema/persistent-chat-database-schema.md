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
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809874"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="acfdc-103">Schéma de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="acfdc-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="acfdc-104">Cela documente le schéma de la base de données de conversation permanente dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="acfdc-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="acfdc-105">La base de données de conversation permanente fait référence à la base de données correspondant aux rôles serveur principal Skype Entreprise Server **PersistentChatStore** (correspondant à la base de données mgc) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp).</span><span class="sxs-lookup"><span data-stu-id="acfdc-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="acfdc-106">Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.</span><span class="sxs-lookup"><span data-stu-id="acfdc-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="acfdc-p102">Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié.</span><span class="sxs-lookup"><span data-stu-id="acfdc-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="acfdc-109">Respectez les meilleures pratiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="acfdc-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="acfdc-110">Aucun select \* // n’est pris en charge, car la liste des colonnes peut croître.</span><span class="sxs-lookup"><span data-stu-id="acfdc-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="acfdc-111">Aucune modification de schéma générée par l’utilisateur n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="acfdc-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="acfdc-112">Aucune opération d’écriture n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="acfdc-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="acfdc-113">Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="acfdc-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="acfdc-114">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="acfdc-114">In this section</span></span>

- [<span data-ttu-id="acfdc-115">Liste des tables de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="acfdc-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="acfdc-116">Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="acfdc-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="acfdc-117">Détails de la table des serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="acfdc-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="acfdc-118">Exemples de requêtes de base de données de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="acfdc-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

