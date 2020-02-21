---
title: 'Lync Server 2013 : conditions requises pour publier une topologie'
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
ms.openlocfilehash: bf8c36fee84880e5236c5048da35dca38a476eab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Conditions requises pour publier une topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette rubrique décrit l’infrastructure et les logiciels requis pour publier une topologie, qu’il s’agisse du générateur de topologies ou de l’interface de ligne de commande de l’environnement de ligne de commande Lync Server 2013 Management Shell. Ces exigences sont en plus du système d’exploitation, des logiciels et des autorisations requis pour tous les outils d’administration Lync Server 2013. Assurez-vous que vous répondez à tous les outils d’administration requis avant de publier une topologie.

  - Vous devez exécuter le générateur de topologie sur un ordinateur qui est joint au même domaine ou à la même forêt que le déploiement Lync Server 2013 que vous créez afin que les étapes de préparation des services de domaine Active Directory soient déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur pour publier correctement votre topologie.

  - Les ordinateurs définis dans la topologie doivent être ajoutés au domaine, à l’exception des serveurs Edge, et aux services de domaine Active Directory (AD DS). En revanche, ils n’ont pas besoin d’être en ligne au moment où vous publiez la topologie.

  - Vous devez créer le partage de fichiers du pool et le mettre à la disposition des utilisateurs distants.

  - Pour publier un pool frontal Enterprise Edition, le serveur principal basé sur SQL Server doit être joint au domaine dans lequel vous déployez les serveurs, en ligne et configuré avec les règles de pare-feu appropriées pour le mettre à la disposition des utilisateurs distants. Pour plus d’informations sur la spécification des exceptions de pare-feu, voir [Understanding Firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Pour plus d’informations sur la configuration de SQL Server, voir [configurer SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Le serveur Standard Edition dispose d’une base de données colocalisée qui acceptera la configuration publiée. Vous devez d’abord exécuter la tâche <STRONG>préparer le premier serveur Standard Edition Server</STRONG> dans l’Assistant Déploiement de Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Voir aussi


[Publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Déléguer les autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

