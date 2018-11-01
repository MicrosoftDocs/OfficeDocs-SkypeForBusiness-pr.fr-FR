---
title: "Lync Server 2013 : Déf. de la conf. requise pour le serveur de conv. Perm."
TOCTitle: Définition de la configuration requise pour l’organisation du serveur de conversation permanente
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398372(v=OCS.15)
ms:contentKeyID: 49297231
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour l’organisation du serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-01-15_

Avant de déployer un serveur de conversations permanentes pour votre organisation, il est essentiel de réfléchir aux questions clés suivantes afin d’optimiser votre déploiement :

  - Qui (profil utilisateur) doit avoir accès au serveur de conversations permanentes ? Le serveur de conversations permanentes est activé par une stratégie qui peut être définie au niveau global, au niveau du site, au niveau du pool ou au niveau de l’utilisateur.

  - Combien d’utilisateurs (échelle) peuvent avoir accès au serveur de conversations permanentes ? Le serveur de conversations permanentes prend en charge 150 000 utilisateurs disposant de privilèges d’accès (via une stratégie) et un nombre maximal de 80 000 utilisateurs simultanés via le serveur de conversations permanentes. Un seul serveur de conversations permanentes peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveurs de conversations permanentes peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.

  - Est-ce que vous effectuez une migration à partir d’une version antérieure d’un serveur Group Chat ou est-ce que vous déployez le serveur de conversations permanentes pour la première fois ?

  - Existe-t-il des exigences de conformité ? Le serveur de conversations permanentes prend en charge la conformité. Le service de conformité s’exécute de manière colocalisée sur le serveur frontal du serveur de conversations permanentes, contrairement aux déploiements antérieurs du serveur Group Chat, où il était nécessaire de disposer d’un ordinateur distinct. La conformité est une fonctionnalité facultative. Si elle est utilisée, elle nécessite une base de données de conformité qui doit être configurée pour stocker les données et événements de conformité. Vous pouvez également configurer un adaptateur pour récupérer les données de la base de données de conformité et les convertir vers un autre format (des fichiers XML ou des archives hébergées sur Exchange, par exemple).

  - Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des **catégories** afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.

  - Comment contrôler les personnes autorisées à créer des salles ? Vous pouvez configurer des **créateurs** en fonction de vos catégories pour créer des salles. Les créateurs peuvent affecter d’autres membres (tels que les **gestionnaires de salles de conversation**) pour la gestion permanente des salles (par ajout ou suppression de membres), en fonction de l’étendue de **AllowedMembers/DeniedMembers** configurée par la catégorie.

  - Comment créer des salles ? Le serveur de conversations permanentes fournit une fonctionnalité web pour la création et la gestion des salles. Cette fonctionnalité peut être exécutée à partir du client Lync 2013. Vous pouvez définir une solution personnalisée (à l’aide du Kit de développement logiciel (SDK) du serveur de conversations permanentes) qui implémente vos besoins et flux de travail professionnels et configure le serveur de conversations permanentes afin de diriger les utilisateurs vers votre solution personnalisée.

  - Quel genre de compléments voulez-vous approvisionner ? Les **compléments** améliorent l’expérience utilisateur en tirant parti du volet d’extensibilité du client Lync 2013 afin de fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant.

  - Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ? Le serveur de conversations permanentes prend en charge la mise en miroir de SQL Server et la mise en cluster de SQL Server à des fins de haute disponibilité. Il prend également en charge jusqu’à 8 serveurs (4 actifs et 4 de secours) dans un pool étendu avec la fonctionnalité de copie des journaux de transaction de SQL Server pour la récupération d’urgence.

  - Existe-t-il des exigences réglementaires ? Si votre société est basée dans un pays/région où les données doivent être conservées à l’échelle nationale, vous devrez déployer plusieurs pools de serveurs de conversations permanentes, chacun étant propre à une zone géographique particulière. Une salle, une catégorie ou un complément ne couvre pas les pools. Il n’appartient qu‘à un seul pool de serveurs de conversations permanentes. Vous pouvez gérer l’ennsemble de catégories, de salles et de compléments pour chaque pool de serveurs de conversations permanentes. Il est possible de configurer des utilisateurs pour accéder aux salles dans un ou plusieurs pools via l’étendue AllowedMembers de la catégorie ou l’adhésion de la salle, selon la manière dont vous concevez vos catégories.
    
    > [!IMPORTANT]  
    > Même si vous disposez de plusieurs pools de serveurs de conversations permanentes, cela n’a pas d’impact au niveau de l’échelle (vous ne pouvez avoir que 80 000 utilisateurs connectés simultanément sur l’ensemble de vos pools de serveurs de conversations permanentes). La raison principale pour la prise en charge de plusieurs pools de serveurs de conversations permanentes est de satisfaire aux exigences réglementaires.
