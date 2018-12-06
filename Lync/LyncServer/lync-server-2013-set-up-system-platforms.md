---
title: 'Lync Server 2013 : Configuration des plateformes système'
TOCTitle: Configuration des plateformes système
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204783(v=OCS.15)
ms:contentKeyID: 49296742
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plateformes système dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Avant de commencer le déploiement du serveur de conversations permanentes, vous devez installer le système d’exploitation requis sur du matériel conforme à la configuration requise sur les serveurs :

Pour plus d’informations sur le matériel pris en charge pour les serveurs exécutant Lync Server 2013, les serveurs de base de données et les serveurs de fichiers, reportez-vous à [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge. Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, reportez-vous à [Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge. Pour plus d’informations sur les mises à jour requises de Windows, reportez-vous à [Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) dans la documentation de prise en charge.

Le serveur de conversations permanentesserveur frontal, **PersistentChatService** peut être déployé sur un ou plusieurs ordinateurs autonomes dans un pool Lync Server 2013Enterprise Edition. Il est impossible de les colocaliser sur le Lync ServerEnterprise Editionserveurs frontaux. Le programme d’amorçage peut déployer serveur de conversations permanentes, à l’instar des autres rôles Lync Server. Les services web **conversation permanente pour File Upload/Download** et **conversation permanente pour Gestion des salles de conversation** sont des composants web déployés sur le Lync Server 2013serveurs frontaux.

Le serveur frontal du serveur de conversations permanentes peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez disposer d’un pool de serveurs de conversations permanentes comprenant jusqu’à 4 serveurs frontaux prenant en charge un total de 80 000 utilisateurs simultanés. Le serveur principal de conversation permanente, **PersistentChatStore**, stocke les salles de conversation et les catégories. Nous vous conseillons d’installer le **PersistentChatStore** sur un serveur principalSQL Server dédié dans votre pool Enterprise Edition, même si nous prenons en charge la colocalisation du serveur principalLync Server 2013 et de **PersistentChatStore** sur la même instance SQL Server.

Si votre organisation requiert la prise en charge de la conformité, vous pouvez l’installer à l’aide du Générateur de topologie. Le service de conformité du serveur de conversations permanentes est installé sur le même ordinateur que le serveur frontal du serveur de conversations permanentes. Une base de données distincte est requise pour la conformité. Pour plus d’informations sur la conformité requise pour le serveur de conversations permanentes, reportez-vous à [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

Chaque topologie requiert au moins un serveur équipé de Lync Server 2013 et un serveur équipé d’un logiciel de base de données SQL Server. Le Générateur de topologie prend en charge plusieurs pools de serveurs de conversations permanentes. Suivez les mêmes instructions de déploiement pour plusieurs pools de serveurs de conversations permanentes que pour n’importe quel pool indiquées dans [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) de la documentation de déploiement.

Vous pouvez aussi déployer un serveur de conversations permanentes avec Lync Server 2013Standard Edition. Dans ce cas, le serveur frontal**PersistentChatService** est colocalisé sur le serveur Standard Edition et vous pouvez déployer le serveur principal**PersistentChatStore** sur l’instance SQL Server Express locale.

> [!IMPORTANT]  
> Nous ne prenons pas en charge le serveur de conversations permanentesStandard Edition pour la haute disponibilité. Les performances et l’évolutivité seraient limitées. De plus, nous ne prenons en charge que les nouveaux déploiements du serveur Standard Edition du serveur de conversations permanentes. Nous ne prenons pas en charge la mise à jour de Lync Server 2010, serveur Group Chat vers un serveur de conversations permanentesLync Server 2013Standard Edition.

## Voir aussi

#### Concepts

[Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  

#### Autres ressources

[Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)

