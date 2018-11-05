---
title: 'Lync Server 2013 : Configuration système requise pour SQL Server'
TOCTitle: Configuration système requise pour SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205112(v=OCS.15)
ms:contentKeyID: 49298309
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration système requise pour SQL Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-25_

Avant de déployer le serveur Enterprise Edition, installez Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 sur un ordinateur dédié qui dispose de la configuration matérielle requise. Pour plus d’informations sur la configuration matérielle requise, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge. Pour plus d’informations sur la configuration logicielle requise, reportez-vous à [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md) dans la documentation de prise en charge. Pour plus d’informations sur les autorisations nécessaires au déploiement, reportez-vous à [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

Avant de créer le pool frontal, vous devez également configurer le Pare-feu Windows de façon à autoriser Lync Server 2013 à accéder à SQL Server via des ports spécifiques. Pour cela, vous devez définir les ports dédiés au serveur à l’aide du Gestionnaire de configuration SQL Server, puis ouvrir les ports dans le Pare-feu Windows avec fonctions avancées de sécurité.

