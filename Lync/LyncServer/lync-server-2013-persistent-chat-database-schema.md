---
title: 'Lync Server 2013 : schéma de la base de données de conversation permanente'
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
ms.openlocfilehash: 51ee4506a22d866a5ba0f771db47546a8fa15e6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Schéma de la base de données de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-18_

Cela décrit le schéma de la base de données de conversation permanente dans le logiciel de communication Lync Server 2013.

La base de données de conversation permanente fait référence à la base de données correspondant aux rôles de serveur principal **PersistentChatStore** de Lync Server 2013 (correspondant à la base de données MGC) et **PersistentChatComplianceStore** (correspondant à la base de données mgccomp). Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.

<div>


> [!IMPORTANT]  
> Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié.



</div>

Respectez les meilleures pratiques suivantes :

  - Non SELECT\* //est pris en charge, car la liste de colonnes peut croître.

  - Aucune modification de schéma générée par l’utilisateur n’est prise en charge.

  - Aucune opération d’écriture n’est prise en charge.

  - Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Liste des tables de serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste des tables de conformité du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Détails de la table du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

