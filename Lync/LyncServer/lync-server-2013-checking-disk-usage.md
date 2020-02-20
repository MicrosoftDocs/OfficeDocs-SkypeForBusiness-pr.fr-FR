---
title: 'Lync Server 2013 : vérification de l’utilisation du disque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d8881bc8b8a55351cc088c230574b958718a63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Vérification de l’utilisation du disque dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-30_

Les disques durs sont un composant important du déploiement de Lync Server 2013. Sans volume de disque libre suffisant, ni le système d’exploitation ni les bases de données Lync Server 2013 ne fonctionnent correctement. Vous devez surveiller quotidiennement les statistiques de la base de données principale Lync Server 2013 afin de vous assurer que les serveurs ne manquent pas d’espace disque et de se préparer à ajouter des ressources de stockage selon les besoins.

Outre l’espace sur les disques hébergeant le système d’exploitation, les fichiers de programme, les bases de données et les journaux de transaction (Lync Server 2013 back end), vous devez également surveiller l’utilisation du système de fichiers qui inclut l’espace disque pour les partages de fichiers qui contiennent les éléments suivants. Datacenter

  - Contenu de la réunion

  - Métadonnées de contenu de réunion

  - Journaux de conformité des réunions

  - Fichiers de données d’application (utilisés en interne par le composant du serveur d’applications)

  - Dossiers de service Web et de conformité du serveur de conversation de groupe (pour stocker les fichiers téléchargés vers le service Web de conversation de groupe)

  - Fichiers XML de conformité de conversation de groupe (qui contiennent des enregistrements de conformité de conversation de groupe)

  - Mettre à jour les fichiers (pour le service de mise à jour des périphériques)

  - Fichiers du carnet d’adresses

Lync Server 2013 a besoin d’espace disque pour stocker ses bases de données et ses journaux de transaction en plus des fichiers figurant dans la zone de partage de fichiers précédemment indiquée.

Vous devez surveiller régulièrement l’espace disque afin de vous assurer que le déploiement de Lync Server 2013 n’est pas affecté par des ressources de stockage insuffisantes.

Comparez et gérez les informations statistiques relatives à l’espace disque disponible sur chaque volume Lync Server 2013 et la croissance attendue des bases de données et des fichiers journaux de transactions. Cela permet de planifier la capacité et d’ajouter de l’espace de stockage lorsque les ressources de stockage sont requises.

Pour tenir compte des situations de dépannage et de récupération d’urgence, nous vous recommandons d’utiliser un espace de volume disponible égal ou supérieur à 110% de la taille de la base de données.

Vous pouvez vérifier l'espace disque disponible en utilisant les méthodes suivantes :

1.  **System Center Operations Manager**   System Center Operations Manager peut être utilisé pour avertir les administrateurs lorsque l’espace de volume est limité.

2.  **Exécution d’un**   script de l’espace disque en exécutant un script qui vous envoie un message si l’espace disponible sur le disque tombe en dessous de 20%. Vous trouverez un exemple de script sur le centre de scripts Microsoft sur TechNet :[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **L’Explorateur**   Windows utilise l’Explorateur Windows pour vérifier l’espace disque sur les volumes qui stockent les journaux et les bases de données Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

