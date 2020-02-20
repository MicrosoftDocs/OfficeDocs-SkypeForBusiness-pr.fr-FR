---
title: 'Lync Server 2013 : définition de la configuration requise pour le serveur de conversation permanente'
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
ms.openlocfilehash: 15beb7728525fa3e4bb6b75dfc46fb46335d1063
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Définition des besoins de votre organisation pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-15_

Avant de déployer le serveur de conversation permanente pour votre organisation, il est essentiel de prendre en compte les principales questions suivantes pour optimiser votre déploiement :

  - Qui (profil utilisateur) doit être activé pour le serveur de conversation permanente ? Le serveur de conversation permanente est activé par une stratégie qui peut être définie au niveau global, de site, de pool ou d’utilisateur.

  - Combien d’utilisateurs (mise à l’ampleur) doivent être activés pour le serveur de conversation permanente ? Le serveur de conversation permanente prend en charge 150 000 utilisateurs configurés (activés par stratégie) et un maximum de 80 000 utilisateurs simultanés utilisant le serveur de conversation permanente. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés et un seul pool de serveurs de conversation permanente peut avoir jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.

  - Effectuez-vous une migration à partir d’une version précédente du serveur de conversation de groupe ou déployez-vous le serveur de conversation permanente pour la première fois ?

  - Existe-t-il des exigences de conformité ? Le serveur de conversation permanente prend en charge la conformité. Le service de conformité s’exécute sous colocalisé sur le serveur frontal de serveur de conversation permanente, par opposition à la nécessité d’un autre ordinateur dans les déploiements de serveurs de conversation de groupe précédents. La conformité est facultative et, si elle est choisie, elle nécessite une base de données de conformité qui doit être configurée pour stocker les données de conformité et les événements. Vous pouvez également configurer un adaptateur pour qu’il prenne les données de la base de données de conformité et les convertit dans un autre format (par exemple, des fichiers XML ou des archives hébergées par Exchange).

  - Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des **catégories** afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.

  - Comment contrôler les personnes autorisées à créer des salles ? Vous pouvez configurer des **créateurs** en fonction de vos catégories pour créer des salles. Les créateurs peuvent affecter d’autres membres (tels que les **gestionnaires de salles de conversation**) pour la gestion permanente des salles (par ajout ou suppression de membres), en fonction de l’étendue de **AllowedMembers/DeniedMembers** configurée par la catégorie.

  - Comment créer des salles ? Le serveur de conversation permanente fournit une fonctionnalité Web pour la création et la gestion de salle. Elle peut être lancée à partir du client Lync 2013. Vous pouvez choisir de définir une solution personnalisée (en utilisant le kit de développement logiciel (SDK) du serveur de conversation permanente) qui implémente les flux de travail et les besoins de votre entreprise, et configure le serveur de conversation permanente pour qu’il dirige les utilisateurs vers votre solution personnalisée.

  - Quel genre de compléments voulez-vous approvisionner ? Les **compléments** améliorent l’expérience dans la salle en tirant parti du volet d’extensibilité du client Lync 2013 pour fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant.

  - Quels sont les types d’exigences en matière de haute disponibilité et de récupération d’urgence ? Le serveur de conversation permanente prend en charge la mise en miroir SQL Server et le clustering SQL Server pour une haute disponibilité et prend en charge jusqu’à 8 serveurs (4 active et 4 Standby) dans un pool étiré avec la copie des journaux de transaction SQL Server pour la récupération d’urgence.

  - Existe-t-il des exigences en matière de réglementation ? Si votre société se trouve dans un pays/une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de conversation permanente, chacun d’eux étant local à une géographie spécifique. Une salle, une catégorie ou un complément ne couvre pas les pools ; il n’appartient qu’à un seul pool de serveurs de conversation permanente. Vous pouvez gérer l’ensemble des catégories, des compléments et des salles pour chaque pool de serveurs de conversation permanente. Les utilisateurs peuvent être configurés pour accéder aux salles d’un ou de plusieurs pools à l’aide de la catégorie AllowedMembers ou de l’étendue d’appartenance de la salle, en fonction de la conception de vos catégories.
    
    <div>
    

    > [!IMPORTANT]  
    > Le fait de disposer de plusieurs pools de serveurs de conversation permanente ne vous offre pas une plus grande échelle (vous pouvez toujours avoir seulement 80 000 utilisateurs connectés simultanément sur tous vos pools de serveurs de conversation permanente). La principale raison de la prise en charge de plusieurs pools de serveurs de conversation permanente est de prendre en charge les préoccupations réglementaires.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

