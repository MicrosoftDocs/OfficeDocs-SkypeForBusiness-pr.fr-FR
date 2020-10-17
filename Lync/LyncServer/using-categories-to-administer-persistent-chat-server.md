---
title: Utilisation de catégories pour administrer le serveur de conversation permanente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d008e77df49dcfb2875923575c5d0c2acb1d1dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526411"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a>Utilisation de catégories pour administrer le serveur de conversation permanente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-01_

Votre déploiement de serveur de conversation permanente peut héberger de nombreuses salles de conversation permanentes simultanées. Les salles de conversation peuvent être organisées en un ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure utile pour l’identification des conversations en fonction de leur objectif professionnel et simplifie la délégation de l’administration ainsi que la gestion.

<div>


> [!NOTE]  
> Bien que de nombreuses fonctionnalités de gestion des salles de conversation soient disponibles sur les ordinateurs qui exécutent une conversation permanente (client Lync) pour l’utilisateur, les administrateurs de conversation permanente (dans le rôle <STRONG>cspersistentchatadministrator</STRONG> ) doivent utiliser le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer ou gérer des catégories.



</div>

Les administrateurs de conversation permanente utilisent le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer des catégories, ainsi que pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.

Les gestionnaires de salles de conversation permanente, qui peuvent gérer une ou plusieurs salles de conversation, peuvent utiliser le client Lync pour lancer une application Web de gestion de salle afin de créer et gérer des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler). Les administrateurs de conversation permanente peuvent également utiliser le panneau de configuration Lync Server ou les applets de commande Windows PowerShell pour créer et gérer des salles.

<div>


> [!NOTE]  
> Une salle de conversation permanente ne peut pas avoir le même nom qu’une catégorie de conversation permanente.



</div>

Les responsables de salles de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, à l’exception de la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :

  - Désactivation d’une salle de conversation

  - Modification du nom d’une salle de conversation

  - Modification de la description d’une salle de conversation

  - Modification du type d’une salle de conversation (Auditorium ou Normal)

  - modification de la confidentialité d’une salle (ouverte/fermée/secrète) ;

  - Ajout ou suppression de membres

  - Ajout ou suppression de gestionnaires de salle de conversation

  - Ajout ou suppression d’un complément

  - Modification de paramètres tels que les invitations (en fonction de ce qui est autorisé par la catégorie)

<div>

## <a name="delegated-administration"></a>Administration déléguée

La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir **AllowedMembers** et des **créateurs** pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de configuration Lync Server ou des applets de commande Windows PowerShell.

Les utilisateurs, les unités d’organisation (UO) et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, les utilisateurs, les unités d’organisation et les groupes d’utilisateurs de la liste **AllowedMembers** de la catégorie peuvent choisir comme responsables et membres de la salle de conversation pour gérer et participer à la salle.

Les salles de conversation créées dans une catégorie adhèrent aux stratégies et paramètres appliqués par la catégorie (par exemple, qui peuvent être dans l’appartenance de la salle, qui peut gérer la salle, si les téléchargements de fichiers sont autorisés, si les invitations sont envoyées, etc.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

