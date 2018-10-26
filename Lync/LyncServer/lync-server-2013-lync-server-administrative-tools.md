---
title: 'Lync Server 2013 : Outils d’administration de Lync Server'
TOCTitle: Outils d’administration de Lync Server
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg195756(v=OCS.15)
ms:contentKeyID: 49298296
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Outils d’administration de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique décrit les outils d’administration pour Lync Server 2013.

Les outils d’administration sont installés par défaut sur chaque serveur Lync Server. Par ailleurs, vous pouvez installer ces outils sur d’autres ordinateurs, notamment sur des consoles d’administration dédiées. Pour obtenir les procédures d’installation des outils d’administration, reportez-vous à [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md). Pour savoir comment ouvrir les outils afin d’effectuer des tâches d’administration, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

Veillez à prendre connaissance des spécifications concernant l’infrastructure, le système d’exploitation, les logiciels et les droits d’administrateur avant d’installer ou d’utiliser les outils d’administration Lync Server. Pour plus d’informations sur les spécifications de l’infrastructure, reportez-vous à [Configuration requise de l’infrastructure pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Pour plus d’informations sur la configuration requise concernant le système d’exploitation et les logiciels pour installer les outils d’administration Lync Server, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) et [Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Les droits et les autorisations d’utilisateur requises pour installer et utiliser les outils sont décrits dans [Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Les outils d’administration se composent des éléments suivants :

  - **Assistant Déploiement de Lync Server**   Permet de déployer Lync Server et d’installer tous les outils d’administration.

  - **Lync ServerGénérateur de topologie**   Permet de définir les composants inclus dans votre déploiement.

  - **Panneau de configuration Lync Server**   Permet une gestion continue de votre déploiement via une interface web.

  - **Lync Server Management Shell**   Permet une gestion courante de votre déploiement via la ligne de commande.

  - **Lync Server Logging tool**   Use to troubleshoot problems in your deployment.

  - **service de journalisation centralisée**   Recueille les journaux et fichiers de suivi d’un ordinateur, d’un pool, d’un site ou globalement. Sélectionnez et définissez des scénarios qui contiennent des fournisseurs, des indicateurs et des niveaux de suivi. La journalisation est recueillie, agrégée et affichée à l’aide d’outils tels que Snooper.exe ou tout autre outil textuel.

Vous pouvez gérer votre déploiement en utilisant essentiellement le Générateur de topologie et le Panneau de configuration Lync Server.

## Assistant Déploiement

Vous devez utiliser l’Assistant Déploiement de Lync Server, inclus dans le support d’installation, pour installer tous les outils d’administration sur un ordinateur sur lequel vous n’avez pas encore installé Lync Server. Au cours du processus d’installation des outils d’administration, l’Assistant Déploiement de Lync Server est installé localement avec les autres outils. Vous pouvez donc l’utiliser par la suite pour installer les fichiers de composants supplémentaires ou pour supprimer les fichiers de composants que vous ne voulez plus sur votre ordinateur.

Pour plus d’informations sur l’exécution initiale de l’Assistant Déploiement de Lync Server à partir du support d’installation Lync Server, reportez-vous à [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

## Générateur de topologie

Pour plus d’informations sur les tâches de déploiement que vous pouvez effectuer à l’aide de le Générateur de topologie, reportez-vous à la documentation de déploiement pour chaque rôle serveur.

## Panneau de configuration Lync Server

Vous pouvez utiliser le Panneau de configuration Lync Server 2013 pour effectuer la plupart des tâches d’administration requises pour gérer et assurer la maintenance de Lync Server 2013. Le Panneau de configuration Lync Server offre une interface graphique utilisateur pour gérer la configuration des serveurs Lync Server, en plus des utilisateurs, clients et périphériques de votre organisation. Lync Server Management Shell utilise le Panneau de configuration Lync Server comme mécanisme sous-jacent pour effectuer la configuration de Lync Server.

Le Panneau de configuration Lync Server est installé automatiquement sur chaque serveur frontal ou serveur Lync Server Standard Edition. Dans cette version, l’administration des serveurs Edge s’effectue à distance. Vous pouvez également installer le Panneau de configuration Lync Server sur un autre ordinateur, tel qu’une console de gestion à partir de laquelle vous gérez Lync Server de manière centralisée. Pour plus d’informations, reportez-vous à [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

> [!IMPORTANT]  
> <ul>
> <li><p>Pour configurer les paramètres à l’aide du Panneau de configuration Lync Server, vous devez être connecté avec un compte affecté au rôle CsAdministrator. Pour plus de détails sur les rôles d’administrateur prédéfinis disponibles dans Lync Server 2013, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a>.</p></li>
> <li><p>Pour configurer les paramètres à l’aide du Panneau de configuration Lync Server, vous devez aussi utiliser un ordinateur avec une résolution d’écran minimale de 1024 x 768.</p></li></ul>


## Lync Server Management Shell

Dans Lync Server, Lync Server Management Shell offre une nouvelle méthode d’administration et de gestion. Lync Server Management Shell est une puissante interface de gestion reposant sur interface de ligne de commande Windows PowerShell, qui inclut un jeu complet d’applets de commande spécifiques à Lync Server. Avec Lync Server Management Shell, vous disposez d’un ensemble complet de commandes de configuration et d’automatisation. Le Générateur de topologie et le Panneau de configuration Lync Server mettent tous deux en œuvre des sous-ensembles de ces applets de commande pour permettre la gestion de Lync Server. Lync Server Management Shell inclut des applets de commande pour toutes les tâches d’administration de Lync Server et vous pouvez les utiliser individuellement pour gérer votre déploiement. Pour plus d’informations, reportez-vous à la documentation [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md) ou l’aide de la ligne de commande pour chaque applet de commande.

## Outil de journalisation

L’outil de journalisation Lync Server facilite la résolution des problèmes en capturant des informations de journalisation et de suivi auprès du produit pendant son exécution. Vous pouvez utiliser cet outil pour exécuter des sessions de débogage sur n’importe quel rôle serveur Lync Server. Pour plus d’informations sur l’outil de journalisation, reportez-vous à la documentation sur l’outil de journalisation Lync Server 2010 dans la bibliothèque TechNet à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).

> [!IMPORTANT]  
> Le service de journalisation centralisée est recommandé pour toute la collecte de journalisation dans toutes les circonstances, plutôt que l’Outil de journalisation de Lync Server. L’Outil de journalisation Lync Server fonctionnera quand même, mais il sera rendu inefficace ou interfèrera avec le service de journalisation centralisée si celui est déjà en cours d’exécution. Vous devez utiliser uniquement le service de journalisation centralisée ou uniquement l’Outil de journalisation Lync Server, mais jamais les deux simultanément. Pour plus d’informations sur le service de journalisation centralisée et sur les raisons pour lesquelles vous devez l’utiliser de manière exclusive, reportez-vous à <a href="lync-server-2013-using-the-centralized-logging-service.md">Utilisation du service de journalisation centralisée dans Lync Server 2013</a>.

## Dans cette section

  - [Configuration requise de l’infrastructure pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Conditions requises pour publier une topologie dans Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Dépannage du Panneau de configuration Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Utilisation du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

## Voir aussi

#### Autres ressources

[Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md)

