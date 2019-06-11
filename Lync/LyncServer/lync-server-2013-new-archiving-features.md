---
title: 'Lync Server 2013 : Nouvelles fonctionnalités d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nouvelles fonctionnalités d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

L’archivage dans Lync Server 2013 permet d’archiver les types de contenu suivants:

  - Messages instantanés P2P

  - Conférences (réunions) qui sont des messages instantanés à plusieurs participants

  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)

De plus, l’archivage dans Lync Server 2013 fournit de nouvelles fonctionnalités qui améliorent l’efficacité du déploiement et des opérations. Ces nouvelles fonctionnalités sont les suivantes:

  - **Colocalisation de l’archivage sur des serveurs frontaux.**    Lync Server 2013 ne possède pas de rôle serveur d’archivage distinct. L’archivage est une fonctionnalité facultative disponible sur tous les serveurs frontaux d’un déploiement Enterprise Edition et sur les serveurs Standard Edition Server qui peuvent être implémentés pour un pool ou un site.

  - **Intégration de Microsoft Exchange.**    Lorsque vous déployez l’archivage, vous pouvez intégrer le stockage des données pour l’archivage avec votre espace de stockage 2013 Exchange pour tous les utilisateurs hébergés sur Exchange 2013 et disposer de leurs boîtes aux lettres sur place, de sorte que vous n’avez pas besoin de déployer SQL Server distinct les bases de données d’archiver les données Lync. Si vous n’avez pas de déploiement Exchange 2013 ou si vous préférez ne pas l’intégrer, ou si vous avez des utilisateurs de Lync 2013 qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées sur place, vous pouvez déployer des bases de données d’archivage distinctes en utilisant SQL Server to Stor. e données archivées provenant des communications Lync. Vous pouvez utiliser les bases de données d’archivage Microsoft Exchange et Lync Server 2013 si vous souhaitez utiliser l’intégration de Microsoft Exchange pour certains utilisateurs, mais pas pour tous les utilisateurs de votre déploiement. Pour plus d’informations sur la conservation inaltérable, voir la section «conservation inaltérable» [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)à l’adresse.

  - **Mise en miroir du SQL Store.**    Lorsque vous déployez l’archivage, vous pouvez activer la mise en miroir de la base de données SQL Server pour votre base de données d’archivage.

  - **Archivage de tableaux blancs et de sondages.**    Le contenu des conférences archivées inclut désormais les tableaux blancs et les sondages partagés pendant la réunion.

Les types de contenu suivants ne sont pas archivés:

  - Transfert de fichiers d’égal à égal

  - Audio/vidéo pour messages instantanés et conférences P2P

  - Partage d’application pour les messages instantanés et les conférences d’égal à égal

<div>

## <a name="see-also"></a>Voir aussi


[Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

