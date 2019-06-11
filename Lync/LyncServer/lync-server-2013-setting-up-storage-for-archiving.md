---
title: 'Lync Server 2013: configuration du stockage pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6728c02e9aa73faceaa8b3e681a5cf9cc4c700cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configuration du stockage pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-17_

Le stockage d’archivage pour Lync Server 2013 comprend les éléments suivants:

  - ****   Le stockage des données de stockage de données est requis pour stocker le contenu des messages instantanés.

  - ****   Le stockage de fichiers de stockage de fichiers est requis pour stocker les données de contenu de conférence et le stockage des fichiers.

<div>

## <a name="setting-up-data-storage"></a>Configurer le stockage des données

La configuration requise pour le stockage des données pour l’archivage dans Lync Server 2013 dépend de la manière dont vous voulez stocker les données d’archivage:

  - Intégrez l’archivage Lync Server 2013 à votre déploiement Exchange pour stocker les données d’archivage à l’aide du stockage Exchange.

  - Configurez des serveurs de base de données SQL Server distincts pour le stockage des données d’archivage.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configuration du stockage Exchange pour l’archivage des données

La configuration d’Exchange pour le stockage des données d’archivage nécessite que votre déploiement Exchange exécute Exchange 2013. De plus, les boîtes aux lettres d’utilisateur doivent être hébergées sur le serveur Exchange 2013 et leurs boîtes aux lettres doivent être placées dans la conservation inaltérable. Pour plus d’informations sur la configuration d’Exchange 2013, voir la documentation du produit Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configuration de serveurs de base de données SQL Server pour le stockage des données d’archivage

Le logiciel de base de données SQL Server que vous archivez dans Lync Server 2013 nécessite le stockage des données archivées, sauf si vous intégrez votre déploiement à Exchange.

Pour les bases de données d’archivage SQL Server, vous devez installer SQL Server sur l’ordinateur qui héberge la base de données d’archivage. Vous pouvez utiliser la même instance SQL que celle utilisée pour la base de données principale d’un pool frontal. Pour des performances optimales, vous devez déployer la base de données d’archivage sur un ordinateur différent du magasin de gestion central. Pour plus d’informations sur les composants collocating de Lync Server 2013, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation relative à la prise en charge.

Chaque serveur de base de données doit exécuter une version prise en charge de SQL Server. Pour plus d’informations sur les versions prises en charge, voir [configuration technique requise pour l’archivage dans Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) dans la documentation de planification.

Vous devez configurer les plates-formes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir le site TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server à l’adresse.

<div>


> [!NOTE]  
> Assurez-vous que le type de démarrage du service de l’agent SQL Server est automatique et que le service de l’agent SQL Server est en cours d’exécution pour l’instance SQL qui conserve la base de données d’archivage, de telle sorte que le travail de maintenance SQL Server d’archivage par défaut puisse s’exécuter conformément aux contrôle du service de l’agent SQL Server.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configurer le stockage de fichiers

L’archivage utilise le partage de fichiers Lync Server 2013 que vous avez spécifié lorsque vous avez configuré votre pool frontal ou Standard Edition Server. Vous ne pouvez pas modifier le partage de fichiers utilisé pour l’archivage. Pour plus d’informations sur les systèmes de stockage de fichiers pris en charge, voir [prise en charge du stockage de fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation relative à la prise en charge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

