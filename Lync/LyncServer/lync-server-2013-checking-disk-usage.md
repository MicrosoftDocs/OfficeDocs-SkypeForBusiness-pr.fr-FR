---
title: 'Lync Server 2013: vérification de l’utilisation du disque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791f4a0f9db56c38c837fa77b443d5aa6de74bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Vérification de l’utilisation du disque dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-04-30_

Les disques durs sont une composante importante du déploiement de Lync Server 2013. Le système d’exploitation et les bases de données 2013 de Lync Server peuvent fonctionner correctement sans le volume de disque libre suffisant. Vous devez surveiller quotidiennement les statistiques de la base de données principale de Lync Server 2013 pour vous assurer que les serveurs ne manquent pas d’espace disque et préparer l’ajout de ressources de stockage selon les besoins.

Outre le contrôle de l’espace sur les disques hébergeant le système d’exploitation, les fichiers de programme, la base de données et les journaux de transactions (serveur principal Lync Server 2013), vous devez également surveiller l’utilisation du système de fichiers qui inclut l’espace disque pour les partages de fichiers qui contiennent les éléments suivants: données

  - Contenu de la réunion

  - Métadonnées de contenu de réunion

  - Journaux de conformité des réunions

  - Fichiers de données d’application (utilisés en interne par le composant Application Server)

  - Service Web de groupe de discussion et dossiers de conformité (pour le stockage des fichiers téléchargés vers le service Web de discussion de groupe)

  - Fichiers XML de mise en conformité des conversations de groupe (qui contiennent les enregistrements de conformité des conversations de groupe)

  - Fichiers de mise à jour (pour le service de mise à jour d’appareils)

  - Fichiers du carnet d’adresses

Lync Server 2013 a besoin d’espace disque dur pour stocker ses bases de données et journaux de transactions en plus des fichiers figurant dans les partages de fichiers figurant précédemment dans la liste.

Vous devez surveiller régulièrement l’espace disque pour vous assurer que le déploiement de Lync Server 2013 n’est pas affecté en raison de ressources de stockage insuffisantes.

Comparer et tenir à jour des informations statistiques sur l’espace disque disponible sur chaque volume Lync Server 2013 et croissance attendue des bases de données et des fichiers du journal des transactions. Cela favorise la planification de la capacité et l’ajout d’espace de stockage lorsque les ressources de stockage sont nécessaires.

Pour prendre en charge la résolution des problèmes et les situations de reprise après sinistre, nous vous recommandons d’utiliser une quantité d’espace libre disponible égale ou supérieure à 110% de la taille de la base de données.

Vous pouvez vérifier l’espace disque disponible en utilisant les méthodes suivantes:

1.  ****   System Center Operations Manager System Center Operations Manager peut être utilisé pour avertir les administrateurs lorsque l’espace disque est limité.

2.  **L’exécution d’un script**   du moniteur de script en exécutant un script qui vous envoie un message si l’espace disponible sur le disque dur est inférieur à 20%. Vous trouverez un exemple de script sur le centre de scripts Microsoft sur TechNet et examinez les éléments suivants:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **L’Explorateur**   Windows permet de vérifier l’espace disque sur les volumes qui stockent les journaux et bases de données Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

