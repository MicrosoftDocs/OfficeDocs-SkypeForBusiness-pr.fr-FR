---
title: 'Lync Server 2013 : Schéma de base de données de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Schéma de base de données de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-18_

Ce document décrit le schéma de la base de données de chat persistante dans le logiciel de communication de Lync Server 2013.

La base de données de chat permanent fait référence à la base de données qui correspond à l' **PersistentChatStore** de rôles de serveur principal Lync Server 2013 (qui correspond à la base de données MGC) et **PersistentChatComplianceStore** (qui correspond au mgccomp base de données). L’objectif de la publication de ce schéma consiste à vous permettre de créer des requêtes et d’accéder à des informations sur la création de rapports utiles sur l’utilisation des discussions, des salles actives, les principaux bureaux d’information, etc.

<div>


> [!IMPORTANT]  
> Nous nous réservons le droit d’évolutionr ce schéma. Microsoft n’apporte aucune garantie de conservation de la compatibilité descendante avec ce schéma publié.



</div>

Suivez ces meilleures pratiques:

  - Aucune sélection\* //est prise en charge, car la liste de colonnes peut grandir.

  - Aucune modification de schéma générée par l’utilisateur n’est prise en charge.

  - Aucune opération d’écriture n’est prise en charge.

  - Testez toutes les requêtes que vous créez sur des bases de données de taille représentative pour vous assurer que les requêtes peuvent être effectuées à un niveau en fonction de vos besoins.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Liste des tables de serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Détails de la table des serveurs de conversation permanente dans Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

