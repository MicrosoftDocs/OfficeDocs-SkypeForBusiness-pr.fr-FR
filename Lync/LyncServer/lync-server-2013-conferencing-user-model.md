---
title: Modèle d’utilisateur de conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Le modèle utilisateur de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

La taille de la réunion est une partie essentielle du modèle utilisateur de conférence de Lync Server. Après la collecte des données à partir de plusieurs points de données (comme décrit dans la section précédente), nous avons déterminé les éléments suivants:

  - La plupart des réunions sont en fait de petites réunions en équipe avec une moyenne de quatre à six participants.

  - Environ 80% des réunions ont moins de 20 participants.

  - 99,98% des réunions ont moins de 100 participants.

En plus de la taille de la réunion, le modèle utilisateur de conférence prend également en compte plusieurs facteurs, tels que:

  - **Réunions simultanées**   combien d’utilisateurs sont-ils censés avoir en même temps des réunions?

  - **Media Mix**   quels types de médias sont disponibles et censés être utilisés par les utilisateurs dans les réunions?

  - **Les types**   d’utilisateurs sont des utilisateurs internes, des utilisateurs distants, des utilisateurs fédérés ou des utilisateurs anonymes.

  - **Durée**   de la réunion avec le temps nécessaire pour permettre à tous les utilisateurs d’une réunion de participer à une réunion?

Pour plus d’informations sur le modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

Pour déterminer le nombre de réunions et d’utilisateurs à utiliser pour le test, nous avons effectué les opérations suivantes:

  - A suivi le nombre total d’utilisateurs au sein d’une organisation (par exemple, les utilisateurs 80 000) et multiplié par le taux de concurrence de la réunion (par exemple, 5% de l’ensemble des utilisateurs) pour déterminer le nombre total d’utilisateurs censés participer à des réunions en même temps (dans cet exemple, , 4000 utilisateurs).

  - Divisez le nombre total d’utilisateurs par le nombre de serveurs Lync Server 2013, serveurs frontaux du déploiement (par exemple, 8 serveurs) pour déterminer le nombre estimé de participants de la réunion par serveur frontal (dans cet exemple, 500 utilisateurs par serveur frontal).

  - Divisez le nombre d’utilisateurs par serveur frontal en fonction de la taille de la réunion moyenne (par exemple, 4 utilisateurs) pour déterminer le nombre de réunions moyenne estimée par serveur frontal (dans cet exemple, les réunions 125 par serveur principal).

  - Pour obtenir la charge de média par chaque serveur frontal, nous avons estimé la combinaison de médias. Par exemple, en supposant que 75% des réunions nécessitent plus qu’une prise en charge du son et 50% de celles-ci nécessitent le partage d’application, une moyenne de 47 réunions et des utilisateurs 188 se connectent à chaque serveur frontal pour le partage d’application.

  - A testé une large gamme de tailles de réunion (en fonction de notre modèle utilisateur d’un maximum de 250 utilisateurs dans un pool partagé) pour s’assurer de l’évolutivité du serveur.

</div>

<span> </span>

</div>

</div>

</div>

