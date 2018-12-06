---
title: 'Lync Server 2013 : Schéma de base de données de conversation permanente'
TOCTitle: Schéma de base de données de conversation permanente
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558653(v=OCS.15)
ms:contentKeyID: 49297255
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schéma de base de données de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-18_

Cela documente le schéma de la base de données de conversation permanente dans les logiciels de communicationLync Server 2013.

La base de données de conversation permanente fait référence à la base de données correspondant aux rôles serveur principaux Lync Server 2013**PersistentChatStore** (correspond à la base de données mgc) et **PersistentChatComplianceStore** (correspond à la base de données mgccomp). Le but de la publication de ce schéma est de vous permettre de créer des requêtes et d’obtenir des informations sur la création de rapports pertinents en matière de conversation instantanée, de salles actives, de contributeurs les plus productifs, etc.

> [!IMPORTANT]  
> Nous nous réservons le droit de faire évoluer ce schéma. Microsoft ne donne aucune garantie en matière de conservation de la rétrocompatibilité avec le schéma publié.

Respectez les meilleures pratiques suivantes :

  - Aucune instruction SELECT\* // n’est prise en charge, car la liste des colonnes peut augmenter.

  - Aucune modification de schéma générée par l’utilisateur n’est prise en charge.

  - Aucune opération d’écriture n’est prise en charge.

  - Testez les requêtes que vous créez sur des bases de données représentatives en matière de taille afin d’avoir la garantie que ces requêtes peuvent répondre à vos besoins.

## Dans cette section

  - [Liste des tables de serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Liste des tables de conformité avec le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Détails de la table des serveurs de conversation permanente dans Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Exemples de requêtes de base de données de conversation permanente pour Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

