---
title: 'Lync Server 2013 : Définition de la configuration requise pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Définition de la configuration requise pour l’organisation du serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-15_

Avant de déployer le serveur de chat permanent pour votre organisation, il est essentiel de tenir compte des principales questions suivantes pour optimiser votre déploiement :

  - Qui (profil utilisateur) doit être activé pour le serveur Chat permanent ? Le serveur Chat permanent est activé par une stratégie qui peut être définie au niveau global, de site, de pool ou d’utilisateur.

  - Combien d’utilisateurs (échelle) doivent être activés pour le serveur de chat permanent ? Le serveur Chat permanent prend en charge les utilisateurs approvisionnés 150 000 (activés par stratégie) et un maximum d' 80 000 utilisateurs simultanés utilisant le serveur de chat permanent. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveur de conversation permanente peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.

  - Vous effectuez une migration à partir d’une version précédente du serveur de discussion de groupe ou vous déployez le serveur de chat permanent pour la première fois ?

  - Est-il impératif de conformité ? Le serveur Chat permanent prend en charge la conformité. Le service de conformité s’exécute sur le serveur frontal de chat permanent du serveur et non sur la configuration requise pour un autre ordinateur dans les déploiements de serveurs de discussion de groupe précédents. La conformité est facultative, et si elle est activée, une base de données de conformité doit être configurée pour stocker les données et événements de conformité. Il est possible que vous souhaitiez également configurer un adaptateur pour utiliser les données de la base de données de conformité et convertir dans un autre format (par exemple, des fichiers XML ou des archives hébergées sur Exchange).

  - Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des **catégories** pour dissocier ces frontières, et choisir qui est autorisé à se trouver dans des salles créées dans chacune de ces catégories.

  - Comment voulez-vous déterminer qui peut créer des salles ? Vous pouvez configurer des **créateurs**en fonction de vos catégories, qui peuvent créer des salles. Les créateurs peuvent affecter d’autres membres comme **gestionnaires de salle de conversation** pour la gestion en continu des salles (en ajoutant ou en supprimant des membres supplémentaires), en fonction de l’étendue de **AllowedMembers/DeniedMembers** configurées par la catégorie.

  - Comment créer des salles ? Le serveur Chat permanent fournit une fonctionnalité basée sur le Web pour la création et la gestion d’une salle. Ce problème peut être lancé à partir du client 2013 Lync. Vous pouvez choisir de définir une solution personnalisée (à l’aide du kit de développement logiciel (SDK) serveur Chat permanent qui implémente les exigences et flux de travail de votre entreprise, et configure le serveur de chat permanent pour diriger les utilisateurs vers votre solution personnalisée.

  - Quel genre de compléments voulez-vous approvisionner ? Les **compléments** améliorent l’environnement dans la salle en tirant parti du volet Extensibility dans le client 2013 de Lync afin de fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant.

  - Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ? Le serveur Chat permanent prend en charge la mise en miroir SQL Server et SQL Server clustering pour une haute disponibilité et prend en charge jusqu’à 8 serveurs (4 en veille d’un niveau actif et 4) dans un pool étendu avec l’envoi du journal SQL Server

  - Existe-t-il des exigences réglementaires ? Si votre société se trouve dans un pays ou une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de chat permanent, chacun d’eux étant local. Une salle, une catégorie ou un complément n’étend pas de pools, ce qui n’est qu’une seule liste de serveurs de chat permanent. Vous pouvez gérer l’ensemble des catégories, des compléments et des salles pour chaque pool de serveurs de chat permanent. Les utilisateurs peuvent être configurés de manière à avoir accès à des salles dans un ou plusieurs pools en utilisant l’étendue de la catégorie AllowedMembers ou l’étendue de l’appartenance de la salle, selon la façon dont vous concevez vos catégories.
    
    <div>
    

    > [!IMPORTANT]  
    > L’utilisation de plusieurs pools de serveurs de chat permanent ne vous offre pas de nouvelles mises à l’échelle (vous pouvez toujours avoir uniquement 80 000 connecté aux utilisateurs de tous vos pools de serveurs de chat permanent). La principale raison de la prise en charge de plusieurs pools de serveurs de chat permanent est de prendre en charge les préoccupations réglementaires.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

