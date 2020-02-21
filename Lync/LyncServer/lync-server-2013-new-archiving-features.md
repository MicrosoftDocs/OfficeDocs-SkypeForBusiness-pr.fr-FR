---
title: 'Lync Server 2013 : nouvelles fonctionnalités d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a8969924acdf8268f059ae3b3660b70ca1dca7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nouvelles fonctionnalités d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

L’archivage dans Lync Server 2013 peut archiver les types de contenu suivants :

  - Messages instantanés d’égal à égal

  - Conférences (réunions) constituant des messages instantanés entre utilisateurs multiples

  - Contenu de conférence, dont le contenu téléchargé (documents, par exemple) et le contenu lié à un événement (par exemple, rejoindre ou quitter la conférence, télécharger des données partagées ou modifier la visibilité)

De plus, l’archivage dans Lync Server 2013 offre de nouvelles fonctionnalités qui améliorent l’efficacité du déploiement et des opérations. Voici ces nouvelles options :

  - **Colocalisation de l’archivage sur les serveurs frontaux.**    Lync Server 2013 ne dispose pas d’un rôle de serveur d’archivage distinct. L’archivage est une fonctionnalité facultative disponible sur tous les serveurs frontaux dans un déploiement Enterprise Edition, ainsi que sur les serveurs Standard Edition Server qui peuvent être implémentés pour un pool ou un site.

  - **Intégration de Microsoft Exchange.**    Lorsque vous déployez l’archivage, vous pouvez intégrer le stockage des données pour l’archivage à votre stockage Exchange 2013 existant pour tous les utilisateurs hébergés sur Exchange 2013 et disposer de leurs boîtes aux lettres en conservation inaltérable, de sorte que vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour archiver les données Lync. Si vous ne disposez pas d’un déploiement d’Exchange 2013 ou si vous préférez ne pas l’intégrer ou si vous avez des utilisateurs Lync 2013 qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées en conservation inaltérable, vous pouvez déployer des bases de données d’archivage distinctes à l’aide de SQL Server to Stor e données archivées à partir de Lync communications. Vous pouvez utiliser à la fois l’intégration de Microsoft Exchange et les bases de données d’archivage Lync Server 2013 pour utiliser l’intégration de Microsoft Exchange pour certains utilisateurs, mais pas pour tous, dans votre déploiement. Pour plus d’informations sur le blocage sur place, consultez la rubrique « conservation inaltérable [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500)» à l’adresse.

  - **Mise en miroir du magasin SQL.**    Lorsque vous déployez l’archivage, vous pouvez activer la mise en miroir de base de données SQL Server pour votre base de données d’archivage.

  - **Archivage des tableaux blancs et des sondages.**    Le contenu de conférence archivé inclut désormais des tableaux blancs et des sondages partagés au cours de la réunion.

Les types de contenu suivants ne sont pas archivés :

  - Transferts de fichiers d’égal à égal

  - Audio/vidéo pour messages instantanés et conférences d’égal à égal

  - Partage d’application pour messages instantanés et conférences d’égal à égal

<div>

## <a name="see-also"></a>Voir aussi


[Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

