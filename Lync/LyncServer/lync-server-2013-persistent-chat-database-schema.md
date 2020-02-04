---
title: 'Lync Server 2013 : Schéma de base de données de conversation permanente'
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
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="ed3ac-102">Schéma de base de données de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed3ac-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed3ac-103">_**Dernière modification de la rubrique :** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="ed3ac-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="ed3ac-104">Ce document décrit le schéma de la base de données de chat persistante dans le logiciel de communication de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="ed3ac-105">La base de données de chat permanent fait référence à la base de données qui correspond à l' **PersistentChatStore** de rôles de serveur principal Lync Server 2013 (qui correspond à la base de données MGC) et **PersistentChatComplianceStore** (qui correspond à la base de données mgccomp).</span><span class="sxs-lookup"><span data-stu-id="ed3ac-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="ed3ac-106">L’objectif de la publication de ce schéma consiste à vous permettre de créer des requêtes et d’accéder à des informations sur la création de rapports utiles sur l’utilisation des discussions, des salles actives, les principaux bureaux d’information, etc.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed3ac-107">Nous nous réservons le droit d’évolutionr ce schéma.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="ed3ac-108">Microsoft n’apporte aucune garantie de conservation de la compatibilité descendante avec ce schéma publié.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="ed3ac-109">Suivez ces meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="ed3ac-109">Follow these best practices:</span></span>

  - <span data-ttu-id="ed3ac-110">Aucune sélection\* //est prise en charge, car la liste de colonnes peut grandir.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="ed3ac-111">Aucune modification de schéma générée par l’utilisateur n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="ed3ac-112">Aucune opération d’écriture n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-112">No write operations are supported.</span></span>

  - <span data-ttu-id="ed3ac-113">Testez toutes les requêtes que vous créez sur des bases de données de taille représentative pour vous assurer que les requêtes peuvent être effectuées à un niveau en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ed3ac-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed3ac-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ed3ac-114">In This Section</span></span>

  - [<span data-ttu-id="ed3ac-115">Liste des tables de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed3ac-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="ed3ac-116">Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed3ac-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="ed3ac-117">Détails de la table des serveurs de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed3ac-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="ed3ac-118">Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed3ac-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

