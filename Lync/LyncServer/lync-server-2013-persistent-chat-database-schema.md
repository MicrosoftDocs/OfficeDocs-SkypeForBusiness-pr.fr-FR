---
title: 'Lync Server 2013 : schéma de la base de données de conversation permanente'
description: 'Lync Server 2013 : schéma de la base de données de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545150"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="3c327-103">Schéma de la base de données de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c327-103">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c327-104">_**Dernière modification de la rubrique :** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="3c327-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="3c327-105">Cela décrit le schéma de la base de données de conversation permanente dans le logiciel de communication Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c327-105">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="3c327-106">La base de données de conversation permanente fait référence à la base de données correspondant aux rôles de serveur principal **PersistentChatStore** de Lync Server 2013 (correspondant à la base de données MGC) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp).</span><span class="sxs-lookup"><span data-stu-id="3c327-106">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="3c327-107">Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.</span><span class="sxs-lookup"><span data-stu-id="3c327-107">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3c327-p102">Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié.</span><span class="sxs-lookup"><span data-stu-id="3c327-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="3c327-110">Respectez les meilleures pratiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3c327-110">Follow these best practices:</span></span>

  - <span data-ttu-id="3c327-111">Non SELECT \* //est pris en charge, car la liste de colonnes peut croître.</span><span class="sxs-lookup"><span data-stu-id="3c327-111">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="3c327-112">Aucune modification de schéma générée par l’utilisateur n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3c327-112">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="3c327-113">Aucune opération d’écriture n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3c327-113">No write operations are supported.</span></span>

  - <span data-ttu-id="3c327-114">Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="3c327-114">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c327-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3c327-115">In This Section</span></span>

  - [<span data-ttu-id="3c327-116">Liste des tables de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c327-116">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="3c327-117">Liste des tables de conformité du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c327-117">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="3c327-118">Détails de la table du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c327-118">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="3c327-119">Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c327-119">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

