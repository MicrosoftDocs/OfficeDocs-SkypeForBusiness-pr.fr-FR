---
title: 'Lync Server 2013 : Configuration des plateformes système'
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
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configuration des plateformes système dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Avant de démarrer le déploiement du serveur de chat permanent, vous devez installer le système d’exploitation requis sur le matériel qui répond à la configuration système requise sur les serveurs :

Pour plus d’informations sur le matériel pris en charge pour les serveurs exécutant Lync Server 2013, les serveurs de base de données et les serveurs de fichiers, voir [matériel compatible pour Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge. Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, voir [prise en charge des logiciels et de l’infrastructure du serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de support technique. Pour plus d’informations sur la configuration requise pour Windows Update, voir [prise en charge supplémentaire du serveur et configuration requise dans Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) dans la documentation relative à la prise en charge.

Le serveur frontal de chat permanent, **PersistentChatService**, peut être déployé sur un ou plusieurs ordinateurs autonomes dans un pool Lync Server 2013 Enterprise Edition. Elles ne peuvent pas être colocalisées sur les serveurs frontaux Lync Server Enterprise Edition. Le serveur de chat permanent peut être déployé par le programme de démarrage, comme d’autres rôles serveur Lync. Les **services Web chat permanent pour la gestion du chargement/téléchargement de fichiers**, et les **services Web chat permanent pour la gestion des salles de conversation** sont des composants Web déployés sur les serveurs Front End de Lync Server 2013.

Un seul serveur frontal de chat permanent peut prendre en charge des utilisateurs actifs de 20 000. Vous pouvez disposer d’un pool de serveurs de chat permanent comprenant jusqu’à 4 terminaisons actives prenant en charge un nombre total d’utilisateurs concurrents 80 000. Le serveur principal de chat permanent, **PersistentChatStore**, stocke les salles et les catégories de discussion. Nous vous recommandons d’installer le **PersistentChatStore** sur un serveur principal SQL Server dédié dans votre pool Enterprise Edition. Bien que nous puissions prendre en charge le serveur principal collocating Lync Server 2013 et **PersistentChatStore** sur la même instance SQL Server.

Si votre organisation nécessite une prise en charge de la conformité, vous pouvez l’installer à l’aide du générateur de topologie. Le service de compatibilité de chat permanent du serveur est installé sur le même ordinateur que le serveur frontal de Chat Server permanent. Une base de données distincte est requise pour la conformité. Pour plus d’informations sur les exigences en matière de conformité pour le serveur de chat permanent, voir [planification du serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

Au minimum, chaque topologie nécessite un serveur sur lequel Lync Server 2013 est installé et un serveur sur lequel sont installés les logiciels de base de données SQL Server. Le générateur de topologie prend en charge plusieurs pools de serveurs de chat permanent. Suivez les mêmes instructions de déploiement pour le déploiement de plusieurs pools de serveurs de chat permanent, comme vous le feriez pour n’importe quel pool de [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

Vous pouvez également déployer le serveur de chat permanent avec Lync Server 2013 Standard Edition. Dans ce cas, le serveur frontal **PersistentChatService** est colocalisé sur le serveur Standard Edition Server et vous pouvez déployer le serveur principal **PersistentChatStore** dans l’instance SQL Server Express locale.

<div>


> [!IMPORTANT]  
> Nous ne prenons pas en charge le&nbsp;service Chat Server Standard Edition pour une haute disponibilité. Les performances et l’évolutivité seront limitées. Par ailleurs, nous ne prenons en charge que&nbsp;de nouveaux déploiements de serveurs de chat permanent Server Standard Edition. Nous ne prenons pas en charge la mise à niveau de Lync Server 2010, Server Chat Server vers&nbsp;lync Server 2013&nbsp;permanent Chat Server Standard Edition.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

