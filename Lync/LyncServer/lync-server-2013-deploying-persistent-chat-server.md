---
title: 'Lync Server 2013 : Déploiement d’un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Déploiement d’un serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-03-31_

Lync Server 2013, permanent Chat Server fait partie de l’infrastructure Lync Server 2013.

Le déploiement de Server chat permanent nécessite les éléments suivants:

  - Utilisez le générateur de topologie pour définir, importer et publier ultérieurement votre topologie et les composants que vous voulez déployer.

  - Préparez votre environnement pour le déploiement de composants serveur Chat permanent.

  - Installez et configurez les composants serveur Chat permanent pour votre déploiement.

Le serveur Chat permanent est disponible avec Lync Server 2013 Enterprise Edition en tant que pool distinct (non localisé aux serveurs frontaux Enterprise Edition). Le serveur Chat permanent nécessite un serveur principal SQL Server dans votre pool Enterprise Edition pour stocker le contenu de la salle de conversation et d’autres métadonnées pertinentes. Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié, même si le serveur principal collocating Lync Server 2013 et **PersistentChatStore** sur la même instance SQL Server est prise en charge.

Le serveur de chat permanent peut également être déployé avec Lync Server 2013 Standard Edition. Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur l’ordinateur Standard Edition, et le serveur principal **PersistentChatStore** peut être déployé dans l’instance SQL Server Express locale.

Pour plus d’informations sur les configurations de colocation prises en charge, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Nous ne prenons pas en charge la haute disponibilité pour&nbsp;le service Chat Server Standard Edition. Les performances et l’évolutivité seront limitées. Par ailleurs, nous ne prenons en charge que&nbsp;le nouveau serveur de chat permanent Server Standard Edition Server. Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Server Chat Server&nbsp;vers lync Server&nbsp;2013 permanent Chat Server Standard Edition.



</div>

Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez installer le service de compatibilité de chat serveur permanent sur le serveur frontal de chat permanent du serveur. Une base de données distincte est requise pour la conformité.

Au minimum, chaque topologie nécessite un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel sont installés les logiciels de base de données SQL Server.

Utilisez le générateur de topologie pour ajouter le serveur de chat permanent aux déploiements de Lync Server 2013. Vous avez la possibilité d’ajouter un ou plusieurs pools de serveurs de chat permanent à l’aide du générateur de topologie. Suivez les mêmes instructions de déploiement pour déployer plusieurs pools de serveurs de chat permanent que pour n’importe quel pool. Pour plus d’informations, reportez-vous à [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

Pour plus d’informations sur les topologies disponibles et la configuration logicielle requise pour l’installation d’un serveur de chat permanent, voir [planification du serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, fonctionnement du [serveur Chat permanent. dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) , dans la documentation de planification, la documentation de déploiement ou la documentation des opérations, et le [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de support.

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

Un seul serveur frontal de chat permanent peut prendre en charge des utilisateurs actifs de 20 000. Vous pouvez disposer d’un pool de serveurs de chat permanent comprenant jusqu’à 4 serveurs frontaux actifs prenant en charge un nombre total d’utilisateurs simultanés de 80 000.

Le serveur Chat permanent est également pris en charge sur un serveur virtuel. Le serveur virtuel peut prendre en charge jusqu’à 20 000 utilisateurs simultanés s’il répond aux spécifications du serveur physique.

<div>


> [!IMPORTANT]  
> Le serveur de chat permanent doit être installé sur un système de fichiers NTFS pour garantir la sécurité du système de fichiers. FAT32 n’est pas un système de fichiers pris en charge pour le serveur de chat permanent.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Fonctionnement du serveur Chat permanent dans Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Configuration requise pour le serveur de chat permanent dans Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configuration des systèmes et de l’infrastructure pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installation du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Ajout d’un administrateur de conversation permanente dans Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configuration du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Résolution des problèmes de configuration d’un serveur de conversation permanente avec les applets de commande Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Basculement et restauration d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

