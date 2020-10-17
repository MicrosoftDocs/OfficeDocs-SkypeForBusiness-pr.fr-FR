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
ms.openlocfilehash: 0b393f9281c1bb1fc1072a541b33bbab2656dafb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524251"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Schéma de la base de données de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

  - Non SELECT \* //est pris en charge, car la liste de colonnes peut croître.

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

