---
title: Modèle utilisateur de conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7cc640f0ed6ae4de2c0b8b25b83a3ec6bb89bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Modèle utilisateur de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Une partie essentielle du modèle utilisateur de conférence Lync Server est la taille de la réunion. Après avoir collecté des données à partir de plusieurs points de données (comme indiqué dans la section précédente), nous avons déterminé les points suivants :

  - La plupart des réunions sont en fait de petites réunions collaboratives, avec une moyenne de quatre à six participants.

  - Environ 80 % des réunions comptent moins de 20 participants.

  - 99,98 % des réunions comptent moins de 100 participants.

Outre la taille des réunions, le modèle utilisateur des conférences prend également en compte divers facteurs, tels que les suivants :

  - **Réunions simultanées**   combien d’utilisateurs doivent être en réunion en même temps ?

  - **Mélange**   de médias quels types de médias sont disponibles et susceptibles d’être utilisés par les utilisateurs dans les réunions ?

  - **Les types**   d’utilisateur sont les utilisateurs internes, les utilisateurs distants, les utilisateurs fédérés ou les utilisateurs anonymes ?

  - **Temps**   de fonctionnement de la mise en service de la réunion combien de temps faut-il pour que tous les utilisateurs d’une réunion rejoignent une réunion ?

Pour plus d’informations sur le modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).

Pour déterminer le nombre de réunions et d’utilisateurs à utiliser pour effectuer les tests, nous avons procédé comme suit :

  - Nous avons pris le nombre total d’utilisateurs d’une organisation (par exemple, 80 000 utilisateurs) que nous avons multiplié par le taux de simultanéité des réunions (par exemple, 5 % de tous les utilisateurs) afin de déterminer le nombre total d’utilisateurs susceptibles d’assister simultanément à des réunions (dans le présent exemple, 4 000 utilisateurs).

  - Divisé le nombre total d’utilisateurs par le nombre de Lync Server 2013, serveurs frontaux dans le déploiement (par exemple, 8 serveurs) pour déterminer le nombre estimé de participants à la réunion par serveur frontal (dans cet exemple, 500 utilisateurs par serveur frontal).

  - Divisez le nombre d’utilisateurs par serveur frontal en fonction de la taille moyenne des réunions (par exemple, 4 utilisateurs) pour déterminer le nombre moyen estimé de réunions par serveur frontal (dans cet exemple, 125 réunions par serveur frontal).

  - Pour obtenir la charge par support sur chaque serveur frontal, nous avons évalué le mixage multimédia. Par exemple, en supposant que 75% des réunions ont besoin de plus que la prise en charge audio et qu' 50% de ces réunions nécessitent le partage d’application, une moyenne de 47 réunions et de 188 utilisateurs se connectent simultanément à chaque serveur frontal pour le partage d’application.

  - Nous avons testé diverses tailles de réunion (en nous basant sur notre modèle utilisateur qui compte un maximum de 250 utilisateurs dans un pool partagé) afin de garantir l’extensibilité du serveur.

</div>

<span> </span>

</div>

</div>

</div>

