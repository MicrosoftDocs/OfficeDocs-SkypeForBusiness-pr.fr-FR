---
title: 'Lync Server 2013 : Conditions requises pour publier une topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Conditions requises pour publier une topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette rubrique décrit l’infrastructure et les configurations logicielles requises qui sont spécifiques à la publication d’une topologie, que ce soit à l’aide du générateur de topologie ou de l’interface de ligne de commande de Lync Server 2013 Management Shell. Ces exigences s’ajoutent aux exigences générales du système d’exploitation, des logiciels et des autorisations applicables à tous les outils d’administration de Lync Server 2013. Assurez-vous que vous respectez toutes les conditions d’outils d’administration avant de publier une topologie.

  - Vous devez exécuter le générateur de topologie sur un ordinateur qui est joint à un domaine ou une forêt du déploiement de Lync Server 2013 que vous créez, afin que les étapes de préparation des services de domaine Active Directory soient déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur de publier correctement votre topologie.

  - Les ordinateurs définis dans la topologie doivent être joints au domaine, à l’exception des serveurs de périphérie et dans AD DS. Toutefois, les ordinateurs n’ont pas besoin d’être en ligne lorsque vous publiez la topologie.

  - Le partage de fichiers du pool doit être créé et disponible pour les utilisateurs distants.

  - Pour publier un pool frontal Enterprise Edition, le serveur principal SQL Server doit être joint au domaine dans lequel vous déployez les serveurs, en ligne et configuré avec les règles de pare-feu appropriées pour le mettre à la disposition des utilisateurs distants. Pour plus d’informations sur la spécification des exceptions de pare-feu, voir [Présentation de la configuration requise pour le pare-feu pour SQL Server avec Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Pour plus d’informations sur la configuration de SQL Server, voir [configurer SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Le serveur Standard Edition dispose d’une base de données colocalisée qui acceptera la configuration publiée. Vous devez commencer par exécuter la tâche de configuration <STRONG>préparer la première édition Standard Server</STRONG> dans l’Assistant Déploiement de Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Voir aussi


[Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

