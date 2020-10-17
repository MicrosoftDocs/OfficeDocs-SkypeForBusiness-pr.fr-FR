---
title: 'Lync Server 2013 : configuration du stockage pour l’archivage'
description: 'Lync Server 2013 : configuration du stockage pour l’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554240"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configuration du stockage pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-17_

Le stockage d’archivage pour Lync Server 2013 inclut les éléments suivants :

  - **Stockage**     des données Le stockage des données est nécessaire pour stocker le contenu de la messagerie instantanée.

  - **Stockage**     de fichiers Le stockage de fichiers est requis pour stocker le stockage des données de contenu de conférence (réunion) et le stockage de fichiers.

<div>

## <a name="setting-up-data-storage"></a>Configuration du stockage des données

La configuration requise pour la configuration du stockage des données pour l’archivage dans Lync Server 2013 dépend de la façon dont vous souhaitez stocker les données d’archivage :

  - Intégrez l’archivage Lync Server 2013 avec votre déploiement Exchange pour stocker les données d’archivage à l’aide du stockage Exchange.

  - Configurez des serveurs de base de données SQL Server distincts pour stocker les données d’archivage.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configuration du stockage Exchange pour les données d’archivage

La configuration d’Exchange pour le stockage des données d’archivage nécessite que votre déploiement Exchange exécute Exchange 2013. De plus, les boîtes aux lettres utilisateur doivent être hébergées sur le serveur Exchange 2013 et leurs boîtes aux lettres doivent être placées en conservation In-Place. Pour plus d’informations sur la configuration d’Exchange 2013, voir la documentation du produit Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configuration des serveurs de base de données SQL Server pour le stockage des données d’archivage

Pour l’archivage dans Lync Server 2013, le logiciel de base de données SQL Server doit être stocké dans les données archivées, sauf si vous intégrez votre déploiement auprès d’Exchange.

Pour les bases de données d’archivage SQL Server, vous devez installer SQL Server sur l’ordinateur qui hébergera la base de données d’archivage. Vous pouvez utiliser la même instance SQL que pour la base de données primaire d’un pool frontal. Pour de meilleures performances, nous vous conseillons de déployer la base de données d’archivage sur un ordinateur distinct du magasin de gestion centralisée. Pour plus d’informations sur les composants colocaliser Lync Server 2013, voir [prise en charge de la colocalisation des serveurs dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

Chaque serveur de base de données doit exécuter une version prise en charge de SQL Server. Pour plus d’informations sur les versions prises en charge, voir [Technical Requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) dans la documentation de planification.

Vous devez configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir SQL Server TechCenter à l’adresse [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

<div>


> [!NOTE]  
> Assurez-vous que le type de démarrage du service SQL Server Agent est automatique et que le service SQL Server Agent est en cours d’exécution pour l’instance SQL qui contient la base de données d’archivage, afin que le travail de maintenance SQL Server d’archivage par défaut puisse s’exécuter à intervalles réguliers sous le contrôle du service SQL Server Agent.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configuration du stockage de fichier

L’archivage utilise le partage de fichiers Lync Server 2013 que vous avez spécifié lors de la configuration de votre pool frontal ou de votre serveur Standard Edition Server. Vous ne pouvez pas modifier le partage de fichiers utilisé pour l’archivage. Pour plus d’informations sur les systèmes de stockage de fichiers pris en charge, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation de prise en charge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

