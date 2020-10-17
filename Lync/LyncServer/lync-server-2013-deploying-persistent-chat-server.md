---
title: 'Lync Server 2013 : déploiement d’un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76f3bb2a3ccc182f16e2e1416bdec00aefe3e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506091"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Déploiement du serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-31_

Lync Server 2013, le serveur de conversation permanente fait partie de l’infrastructure Lync Server 2013.

Le déploiement du serveur de conversation permanente nécessite les opérations suivantes :

  - Utilisez le générateur de topologies pour définir ou importer et publier ultérieurement votre topologie et les composants que vous souhaitez déployer.

  - Préparez votre environnement pour le déploiement de composants de serveur de conversation permanente.

  - Installez et configurez les composants de serveur de conversation permanente pour votre déploiement.

Le serveur de conversation permanente est disponible avec Lync Server 2013 Enterprise Edition en tant que pool distinct (non colocalisé avec les serveurs frontaux Enterprise Edition). Le serveur de conversation permanente nécessite un serveur principal SQL Server dans votre pool Enterprise Edition pour stocker le contenu de la salle de conversation et d’autres métadonnées pertinentes. Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié, bien que colocaliser serveur principal et **PersistentChatStore** Lync Server 2013 sur la même instance SQL Server soient pris en charge.

Le serveur de conversation permanente peut également être déployé avec Lync Server 2013 Standard Edition. Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur l’ordinateur Standard Edition et le serveur principal **PersistentChatStore** peut être déployé sur l’instance SQL Server Express locale.

Pour plus d’informations sur les configurations de géolocalisation prises en charge, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Nous ne prenons pas en charge la haute disponibilité pour le serveur de conversation permanente &nbsp; Standard Edition. Les performances et l’évolutivité seraient limitées. Par ailleurs, nous prenons en charge uniquement le nouveau serveur de conversation permanente Server &nbsp; Standard Edition. Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, du serveur de conversation de groupe vers un serveur Lync Server 2013 &nbsp; persistent Chat Server &nbsp; Standard Edition.



</div>

Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez installer le service de conformité du serveur de conversation permanente sur le serveur frontal du serveur de conversation permanente. Une base de données séparée est requise pour la conformité.

Chaque topologie requiert au minimum un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel le logiciel de base de données SQL Server est installé.

Utilisez le générateur de topologie pour ajouter un serveur de conversation permanente à vos déploiements Lync Server 2013. Vous pouvez choisir d’ajouter un ou plusieurs pools de serveurs de conversation permanente à l’aide du générateur de topologie. Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de conversation permanente comme vous le feriez pour n’importe quel pool. Pour plus d’informations, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement.

Pour plus d’informations sur les topologies disponibles et les configurations techniques et logicielles requises pour l’installation du serveur de conversation permanente, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, [How the persistent Chat Server in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations, ainsi que le [matériel pris en charge pour Lync 2013 Server](lync-server-2013-supported-hardware.md)

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

Un seul serveur frontal de serveur de conversation permanente peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez disposer d’un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs prenant en charge un total de 80 000 utilisateurs simultanés.

Le serveur de conversation permanente est également pris en charge sur un serveur virtuel. Le serveur virtuel peut prendre en charge jusqu’à 20 000 utilisateurs simultanés s’il respecte les spécifications du serveur physique.

<div>


> [!IMPORTANT]  
> Le serveur de conversation permanente doit être installé sur un système de fichiers NTFS pour renforcer la sécurité du système de fichiers. FAT32 n’est pas un système de fichiers pris en charge pour le serveur de conversation permanente.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Fonctionnement du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configuration des systèmes et de l’infrastructure pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installation du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Ajout d’un administrateur de conversation permanente dans Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configuration du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Résolution des problèmes de configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Basculement et restauration d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

