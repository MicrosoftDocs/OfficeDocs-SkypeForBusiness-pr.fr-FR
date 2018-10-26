---
title: 'Lync Server 2013 : Déploiement d’un serveur de conversation permanente'
TOCTitle: Déploiement d’un serveur de conversation permanente
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205357(v=OCS.15)
ms:contentKeyID: 49299136
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement d’un serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-03-31_

Le Lync Server 2013serveur de conversations permanentes fait partie de l’infrastructure Lync Server 2013.

Le déploiement du serveur de conversations permanentes implique que vous exécutiez les opérations suivantes :

  - Utilisez le Générateur de topologie pour définir ou importer votre topologie et les composants que vous voulez déployer, puis les publier.

  - Préparez votre environnement au déploiement des composants du serveur de conversations permanentes.

  - Installez et configurez les composants du serveur de conversations permanentes pour votre déploiement.

Le serveur de conversations permanentes est disponible avec Lync Server 2013Enterprise Edition en tant que pool distinct (pas colocalisé avec les Enterprise Editionserveurs frontaux). Le serveur de conversations permanentes nécessite un SQL Serverserveur principal dans votre pool Enterprise Edition pour stocker le contenu des salles de conversation et autres métadonnées pertinentes. Nous vous recommandons d’installer le **MagasinConversationPersistante** sur un SQL Serverserveur principal dédié, même si la colocation d’un Lync Server 2013serveur principal et du **MagasinConversationPersistante** sur la même instance de SQL Server est prise en charge.

Le serveur de conversations permanentes peut aussi être déployé avec le Lync Server 2013Standard Edition. Dans ce cas, le serveur frontal du **ServiceConversationPersistante** est colocalisé sur l’ordinateur Standard Edition, et le serveur principal du **MagasinConversationPersistante** peut être déployé sur l’instance SQL Server Express locale.

Pour plus d’informations sur les configurations de colocalisation prises en charge, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md).

> [!IMPORTANT]  
> Nous ne prenons pas en charge la haute disponibilité pour le serveur de conversations permanentesStandard Edition. Les performances et l’échelle seront limitées. De plus, nous ne prenons en charge que le nouveau serveur de conversations permanentesserveur Standard Edition. Nous ne prenons pas en charge la mise à niveau du Lync Server 2010, serveur Group Chat vers un Lync Server 2013serveur de conversations permanentesStandard Edition.

Si votre entreprise nécessite une prise en charge de conformité, vous pouvez installer le service de conformité serveur de conversations permanentes sur le serveur de conversations permanentesserveur frontal. Une base de données distincte est requise pour la conformité.

Chaque topologie requiert au minimum un serveur sur lequel est installé Lync Server 2013 et un serveur sur lequel est installé le logiciel de base de données SQL Server.

Le Générateur de topologie vous permet d’ajouter le serveur de conversations permanentes à vos déploiements Lync Server 2013. Vous pouvez ajouter un ou plusieurs pools de serveurs de conversations permanentes à l’aide du Générateur de topologie. Suivez les mêmes instructions de déploiement pour déployer plusieurs pools de serveurs de conversations permanentes que pour n’importe quel pool. Pour plus d’informations, reportez-vous à [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement.

Pour plus d’informations sur les topologies disponibles et la configuration logicielle et technique requise pour l’installation du serveur de conversations permanentes, reportez-vous à [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) (contenu éventuellement en anglais) dans la documentation relative à la planification, [Fonctionnement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) (contenu éventuellement en anglais) dans la documentation relative à la planification, au déploiement ou aux opérations, et [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) (contenu éventuellement en anglais) dans la documentation relative à la capacité de prise en charge.

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, reportez-vous à [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement.

Un serveur de conversations permanentesserveur frontal unique peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez avoir un pool de serveurs de conversations permanentes avec 4 serveurs frontaux actifs au maximum, prenant en charge un total de 80 000 utilisateurs simultanés.

serveur de conversations permanentes est également pris en charge sur un serveur virtuel. Le serveur virtuel peut prendre en charge jusqu’à 20 000 utilisateurs simultanés s’il respecte les spécifications du serveur physique.

> [!IMPORTANT]  
> Le serveur de conversations permanentes doit être installé sur un système de fichiers NTFS pour permettre d’appliquer la sécurité du système de fichiers. Le système de fichiers FAT32 n’est pas pris en charge par le serveur de conversations permanentes.

## Dans cette section

  - [Fonctionnement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configuration des systèmes et de l’infrastructure pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installation du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Ajout d’un administrateur de conversation permanente dans Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configuration du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Résolution des problèmes de configuration d’un serveur de conversation permanente avec les applets de commande Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Basculement et restauration d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

