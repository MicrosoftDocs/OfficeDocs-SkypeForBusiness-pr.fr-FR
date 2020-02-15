---
title: Distribution de la charge de conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dad04b445421e27e68cf49900d4bb925918bd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribution de la charge de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Contrairement à d’autres solutions de conférence dédiées, l’architecture Lync Server est un modèle de matériel partagé. Cela signifie que le même matériel est partagé par de nombreux composants logiciels, chacun d’entre eux prenant en charge différentes communications en temps réel. Chaque type de communication en temps réel place des charges spécifiques sur les serveurs. Par exemple, le serveur frontal peut exécuter les composants de routage SIP (Session Initiation Protocol), les applications Web (telles que la recherche de carnet d’adresses), le service de conférence Web, le service de conférence A/V, les applications voix entreprise (par exemple, l’application de surveillance de conférence et l’application Response Group) et le serveur de médiation. Un ensemble de bases de données sur le serveur frontal assure également le stockage et le traitement des données d’utilisateur, de contact, de présence, de conférence et de routage des communications vocales. Avec ce partage matériel, les composants, les services et les processus rivalisant pour les ressources du processeur et de la mémoire, les charges de travail non relatives aux conférences ont un impact direct sur la mise à l’échelle du serveur.

Par rapport aux autres solutions de conférence basées sur les ports matériels, l’architecture de conférence Lync Server est un modèle sans réservation. Lorsqu’un utilisateur planifie une réunion, Lync Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve pas de ressources matérielles pour la réunion planifiée à l’avance. Au lieu de cela, Lync Server dispose d’une logique d’équilibrage de charge intégrée pour allouer dynamiquement les ressources de conférence sur les serveurs frontaux d’une manière qui distribue équitablement les charges sur tous les serveurs frontaux du pool. Cela permet d’approvisionner et d’utiliser les ressources matérielles mais rend difficile la prise en charge des réunions de très grande taille (surtout sans planification appropriée). Par exemple, lorsqu’un pool Lync Server 2013 est exécuté près de sa capacité maximale, chaque serveur frontal peut héberger environ 125 réunions de taille moyenne. L’ajout d’une autre petite réunion ne serait pas un problème, mais l’ajout d’une réunion pour 1000 utilisateurs serait un problème, car les serveurs frontaux ne seraient probablement pas en mesure de prendre en charge une réunion de grande taille en même temps que les autres réunions 125.

</div>

<span> </span>

</div>

</div>

</div>

