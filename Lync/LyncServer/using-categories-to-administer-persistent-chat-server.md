---
title: Utilisation des catégories pour administrer le serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Utilisation des catégories pour administrer le serveur de conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-01_

Le déploiement de votre serveur Chat permanent peut accueillir de nombreux salles de conversation permanentes concomitantes. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.

<div>


> [!NOTE]  
> Même si de nombreuses fonctionnalités de gestion des salles de conversation sont disponibles sur des ordinateurs exécutant une conversation permanente (client Lync) pour l’utilisateur, les administrateurs de chat permanent (dans le rôle <STRONG>cspersistentchatadministrator</STRONG> ) doivent utiliser le panneau de configuration de Lync Server ou Cmdlets Windows PowerShell pour créer ou gérer des catégories.



</div>

Les administrateurs de chat permanent utilisent le panneau de configuration de Lync Server ou des applets de commande Windows PowerShell pour créer et gérer des catégories, et pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.

Les gestionnaires de salle de conversation permanents, qui peuvent gérer une ou plusieurs salles de conversation, peuvent utiliser le client Lync pour lancer une application Web de gestion de salle de création et de gestion des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler). Les administrateurs de chat permanent peuvent également utiliser les applets de commande du panneau de configuration de Lync Server ou de Windows PowerShell pour créer et gérer des salles.

<div>


> [!NOTE]  
> Une salle de conversation permanente ne peut pas avoir le même nom qu’une catégorie de conversation permanente.



</div>

Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :

  - Désactivation d’une salle de conversation

  - Modification du nom d’une salle de conversation

  - Modification de la description d’une salle de conversation

  - Modification du type de salle d’une conversation (Auditorium ou Normal)

  - Modification de la confidentialité d’une salle (ouverte, fermée ou secrète)

  - Ajout ou suppression de membres

  - Ajout ou suppression de gestionnaires de salle de conversation

  - Ajout ou suppression d’un complément

  - Modification des paramètres, comme les invitations (selon ce qu’autorise la catégorie)

<div>

## <a name="delegated-administration"></a>Administration déléguée

La création et la gestion des salles de conversation permanentes sont beaucoup plus simples grâce à l’utilisation correcte des catégories. Un administrateur de chat permanent peut définir des **AllowedMembers** et des **créateurs** pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à l’ensemble des salles de conversation créées dans la catégorie. Les administrateurs de chat permanent créent et gèrent des catégories à l’aide du panneau de configuration de Lync Server ou des applets de commande Windows PowerShell.

Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent définir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste **AllowedMembers** de la catégorie comme responsables et membres de salle de conversation pour gérer et participer à la salle.

Les salles de conversation créées dans une catégorie respectent les stratégies et les paramètres appliqués par la catégorie (par exemple, qui peut se trouver dans l’appartenance de la salle, qui peut gérer la salle, si les téléchargements de fichiers sont autorisés, si les invitations sont envoyées, etc.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

