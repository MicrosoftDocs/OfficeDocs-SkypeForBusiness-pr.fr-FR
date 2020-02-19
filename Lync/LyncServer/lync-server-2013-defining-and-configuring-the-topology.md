---
title: 'Lync Server 2013 : définition et configuration de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a443aaa7cf523e1cb02beb3d944ec53632732291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Définition et configuration de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-14_

Vous définissez et configurez votre topologie à l’aide du générateur de topologie. Le générateur de topologie ne requiert pas que vous soyez membre du groupe Administrateurs local ou d’un groupe de domaine privilégié (tel que Admins du domaine). Vous pouvez définir votre topologie en tant qu’utilisateur standard. Lorsque vous démarrez le Générateur de topologies pour la première fois et lors des sessions de modification ultérieures, le système vous invite à spécifier l’emplacement où le Générateur de topologies doit charger le document de configuration actuel. Les choix sont les suivants :

  - Télécharger la topologie à partir d’un déploiement existant

  - Ouvrir la topologie à partir d’un fichier local

  - Nouvelle topologie

Si vous avez déjà défini une topologie et que vous avez établi le magasin central de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant. Le Générateur de topologies lit la base de données et récupère la définition actuelle. Si vous disposez d’un magasin central de gestion, vous devez toujours choisir cette option.

Si vous n’avez pas établi de magasin central de gestion et que vous souhaitez modifier une configuration enregistrée précédemment, vous devez choisir d’ouvrir la topologie à partir d’un fichier local. Le fichier que vous ouvrirez sera le fichier de configuration qui a été enregistré dans une session précédente. Vous pouvez utiliser cette option pour modifier la topologie précédemment enregistrée.

<div>


> [!WARNING]  
> Si vous disposez déjà d’une topologie publiée, ne chargez aucun fichier de configuration local. Choisissez de télécharger la topologie à partir d’un déploiement existant.



</div>

Choisissez de créer une nouvelle topologie, si vous voulez créer une nouvelle configuration de générateur de topologie. Une conception précédemment enregistrée n’est pas remplacée sauf si vous choisissez de l’enregistrer à la place du fichier que vous avez créé lors d’une session de conception précédente.

Dans chacune de ces options, vous serez invité à indiquer l’emplacement de stockage du fichier de configuration du générateur de topologie. L’emplacement du fichier peut être un emplacement local, un emplacement partagé sur un partage de fichiers défini ou un média amovible.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définition et configuration d’une topologie dans le générateur de topologies pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Sélectionnez le serveur de gestion centralisée dans Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

