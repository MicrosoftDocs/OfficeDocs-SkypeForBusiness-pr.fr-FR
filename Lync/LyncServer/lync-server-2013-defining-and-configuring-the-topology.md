---
title: 'Lync Server 2013 : Définition et configuration de la topologie'
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
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Définition et configuration de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-14_

Vous définissez et configurez votre topologie à l’aide du générateur de topologie. Le générateur de topologie ne doit pas nécessairement être membre du groupe Administrateurs local ou d’un groupe de domaine privilégié (par exemple, administrateurs de domaine). Vous pouvez définir votre topologie en tant qu’utilisateur standard. Lorsque vous démarrez le générateur de topologie lors de la première utilisation et des sessions d’édition ultérieures, vous êtes invité à indiquer l’emplacement où vous voulez que le générateur de topologie charge le document de configuration actuel. Les choix possibles sont les suivants :

  - Téléchargement de la topologie à partir d’un déploiement existant

  - Ouvrir la topologie à partir d’un fichier local

  - Nouvelle topologie

Si vous avez déjà défini une topologie et que vous avez établi la Banque centrale de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant. Le générateur de topologie lira la base de données et récupérera la définition actuelle. Si vous avez déjà un magasin central de gestion, vous devez toujours choisir cette option.

Si vous n’avez pas établi de magasin de gestion central et voulez modifier une configuration déjà enregistrée, vous devez choisir d’ouvrir la topologie à partir d’un fichier local. Le fichier que vous allez ouvrir sera le fichier de configuration enregistré dans une session précédente. Vous pouvez utiliser cette option pour modifier la topologie précédemment enregistrée.

<div>


> [!WARNING]  
> Si vous disposez déjà d’une topologie publiée, vous ne devez pas charger de fichier de configuration local. Vous devez choisir de télécharger la topologie à partir d’un déploiement existant.



</div>

Choisissez de créer une nouvelle topologie si vous voulez créer une nouvelle configuration de générateur de topologie. Une conception déjà enregistrée n’est pas remplacée, sauf si vous choisissez de l’enregistrer dans le même fichier que celui que vous avez créé lors d’une session de conception antérieure.

Dans chacune de ces options, vous êtes invité à fournir un emplacement pour le stockage du fichier de configuration du générateur de topologie. L’emplacement du fichier peut correspondre à un emplacement local, à un emplacement partagé sur un partage de fichiers établi ou un média amovible.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Modification ou configuration des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Sélection du serveur de gestion centralisée dans Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

