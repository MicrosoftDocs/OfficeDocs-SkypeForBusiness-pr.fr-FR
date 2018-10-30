---
title: "Util. des catégories pour administrer le serveur de conversation permanente"
TOCtitle: "Util. des catégories pour administrer le serveur de conversation permanente"
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398988(v=OCS.15)
ms:contentKeyID: 49299076
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation des catégories pour administrer le serveur de conversation permanente

 

_**Dernière rubrique modifiée :** 2013-10-01_

Votre déploiement de serveur de conversations permanentes peut héberger plusieurs salles de conversation permanente en même temps. Les salles de conversation peuvent être organisées en un ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie, et hérite certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations sur la base de leur objectif métier et facilite une administration déléguée et une gestion simplifiée.

> [!NOTE]  
> Même si de nombreuses fonctionnalités de gestion des salles de conversation sont disponibles sur les ordinateurs exécutant la conversation permanente (client Lync) pour l’utilisateur, les administrateurs de conversation permanente (dans le rôle <strong>cspersistentchatadministrator</strong>) doivent utiliser le Panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer ou gérer les catégories.

Les administrateurs de conversation permanente utilisent le Panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer les catégories, et pour concevoir l’accès aux salles de conversation pour les utilisateurs dans leur organisation.

Les gestionnaires de salle de conversation permanente, qui peuvent gérer une ou plusieurs salles de conversation, peuvent utiliser le client Lync pour lancer une application web de gestion de salles pour créer et gérer les salles (ou les clients peuvent créer des solutions et flux de travail personnalisés à appeler). Les administrateurs de conversation permanente peuvent également utiliser le Panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer les salles.

> [!NOTE]  
> Une salle conversation permanente ne peut pas avoir le même nom qu’une catégorie conversation permanente.

Les responsables de salle de conversation peuvent apporter des modifications aux propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :

  - Désactivation d’une salle de conversation

  - Modification du nom d’une salle de conversation

  - Modification de la description d’une salle de conversation

  - Modification du type de salle d’une conversation (Auditorium ou Normal)

  - Modification de la confidentialité d’une salle (ouverte par rapport à fermée par rapport à secrète)

  - Ajout ou suppression de membres

  - Ajout ou suppression de gestionnaires de salle de conversation

  - Ajout ou suppression d’un complément

  - Modification des paramètres tels que les invitations (selon ce qui est autorisé par la catégorie)

## Administration déléguée

La création et la gestion des salles de conversation permanente est beaucoup plus facile avec l’utilisation appropriée des catégories. Un administrateur de conversation permanente peut définir les **AllowedMembers** et **Creators** de chaque catégorie, ainsi que les paramètres et comportements par défaut à appliquer à chaque salle de conversation créée dans la catégorie. Les administrateurs de conversation permanente créent et gèrent les catégories à l’aide du Panneau de configuration Lync Server ou d’applets de commande Windows PowerShell.

Les utilisateurs, unités d’organisation et groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent définir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste **AllowedMembers** de la catégorie comme responsables et membres de salle de conversation pour gérer et participer à la salle.

Les salles de conversation créées dans une catégorie respectent les stratégies et paramètres appliqués par la catégorie (tels que les personnes pouvant être membres de la salle, celles pouvant gérer la salle, si les téléchargements de fichiers sont autorisés, si des invitations sont envoyées, etc.).

