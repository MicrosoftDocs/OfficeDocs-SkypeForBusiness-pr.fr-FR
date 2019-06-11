---
title: Distribution de chargement de conférences de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribution de chargement de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Contrairement à d’autres solutions de conférence dédiées, Lync Server architecture est un modèle de matériel partagé. Cela signifie que le même matériel est partagé par de nombreux composants logiciels, chacun d’entre eux prenant en charge des communications en temps réel différentes. Chaque type de communication en temps réel place des charges spécifiques sur les serveurs. Par exemple, le serveur frontal peut exécuter les composants de routage SIP (Session Initiation Protocol), les applications Web (telles que la recherche dans le carnet d’adresses), le service de conférence Web, le service de conférence A/V, les applications vocales d’entreprise (par exemple, les conférences Application attendant et application de groupe de réponse) et serveur de médiation. Un ensemble de bases de données du serveur frontal permet également de stocker et de traiter les données utilisateur, de contact, de présence, de conférence et de routage vocal. Avec ce partage matériel, ses composants, ses services et ses processus en concurrence pour les ressources de mémoire et d’UC, les charges de travail non associées peuvent avoir un impact direct sur la mise à l’échelle du serveur.

Comparée aux autres solutions de conférence basées sur les ports, l’architecture de conférence serveur Lync est un modèle sans réservation. Lorsqu’un utilisateur planifie une réunion, Lync Server crée un enregistrement dans la base de données de conférence qui stocke les données de conférence, mais ne réserve aucune ressource matérielle pour la réunion planifiée à l’avance. Au lieu de cela, Lync Server dispose d’une logique d’équilibrage de charge intégrée permettant d’allouer dynamiquement les ressources de conférence sur les serveurs frontaux de telle sorte que les données de répartition soient uniformément chargées sur tous les serveurs frontaux de la liste. Cela met en application et utilise efficacement les ressources matérielles, mais contribue à la prise en charge des réunions de très grande taille (en particulier, sans planification appropriée). Par exemple, lorsqu’un pool Lync Server 2013 est en cours d’exécution en plus grande capacité, chaque serveur frontal peut héberger approximativement 125 réunions de taille moyenne. L’ajout d’une autre réunion de petite taille ne serait pas un obstacle à la différence d’une réunion de 1 000 utilisateurs, car les serveurs frontaux ne pourraient probablement pas prendre en charge une grande réunion en même temps que les 125 autres réunions.

</div>

<span> </span>

</div>

</div>

</div>

