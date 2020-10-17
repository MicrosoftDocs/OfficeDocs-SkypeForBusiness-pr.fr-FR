---
title: 'Lync Server 2013 : configuration des plateformes système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509781"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configuration des plateformes système dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Avant de commencer le déploiement du serveur de conversation permanente, vous devez installer le système d’exploitation requis sur le matériel qui répond à la configuration système requise sur les serveurs :

Pour plus d’informations sur le matériel pris en charge pour les serveurs exécutant Lync Server 2013, les serveurs de bases de données et les serveurs de fichiers, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge. Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, voir [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge. Pour plus d’informations sur la configuration requise pour Windows Update, voir [prise en charge et configuration requise des serveurs supplémentaires dans Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) dans la documentation de prise en charge.

Le serveur frontal de serveur de conversation permanente **PersistentChatService**peut être déployé sur un ou plusieurs ordinateurs autonomes dans un pool Lync Server 2013 Enterprise Edition. Elles ne peuvent pas être colocalisées sur les serveurs frontaux Lync Server Enterprise Edition. Le serveur de conversation permanente peut être déployé par le programme d’amorçage, comme d’autres rôles Lync Server. Les **services Web de conversation permanente pour le chargement/téléchargement de fichiers**et les **services Web de conversation permanente pour la gestion des salles de conversation** sont des composants Web déployés sur les serveurs frontaux Lync Server 2013.

Un seul serveur frontal de serveur de conversation permanente peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez disposer d’un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs prenant en charge un total de 80 000 utilisateurs simultanés. Le serveur principal de conversation permanente **PersistentChatStore**, stocke les salles de conversation et les catégories. Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié dans votre pool Enterprise Edition ; Bien que nous prenons en charge colocaliser serveur principal et **PersistentChatStore** Lync Server 2013 sur la même instance SQL Server.

Si votre organisation a besoin d’une prise en charge de la conformité, vous pouvez l’installer à l’aide du générateur de topologie. Le service de conformité du serveur de conversation permanente est installé sur le même ordinateur que le serveur frontal de serveur de conversation permanente. Une base de données séparée est requise pour la conformité. Pour plus d’informations sur les exigences de conformité pour le serveur de conversation permanente, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

Chaque topologie requiert au minimum un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel le logiciel de base de données SQL Server est installé. Le générateur de topologie prend en charge plusieurs pools de serveurs de conversation permanente. Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de conversation permanente comme vous le feriez pour n’importe quel pool du [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

Vous pouvez également déployer le serveur de conversation permanente avec Lync Server 2013 Standard Edition. Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur le serveur Standard Edition, et vous pouvez déployer le serveur principal **PersistentChatStore** sur l’instance SQL Server Express locale.

<div>


> [!IMPORTANT]  
> Nous ne prenons pas en charge le serveur de conversation permanente &nbsp; pour la haute disponibilité. Les performances et l’évolutivité seraient limitées. En outre, nous ne prenons en charge que les nouveaux déploiements de serveur de conversation permanente Server &nbsp; Standard Edition. Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Group Chat Server vers un serveur Lync Server 2013 &nbsp; persistent Chat Server &nbsp; Standard Edition.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge supplémentaire des serveurs et configuration requise dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Déploiement de Microsoft Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

