---
title: 'Lync Server 2013 : composants utilisés par le parcage d’appel'
description: 'Lync Server 2013 : composants utilisés par le parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576770"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Composants utilisés par le parcage d’appel dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-13_

L’application de parcage d’appel est installée automatiquement lorsque vous déployez voix entreprise. Vous activez le parcage d’appel en configurant la stratégie de voix. Les composants Lync Server 2013 suivants prennent en charge l’application de parcage d’appel :

  - **Service**     d’application Application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que l’application de parcage d’appel. Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.

  - Application de parcage d' **appel**     L’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application. Il est inclus automatiquement lorsque vous déployez Voix Entreprise. Appeler des parcs de parcage et récupère les appels et gère les orbites de parcage d’appel.

  - Fichier de blocage **sur la musique**     Si la musique est activée, le fichier de musique est lu pendant le parcage d’un appel. Un fichier de musique par défaut est inclus lors de l’installation de l’application de parcage d’appel.

  - **Magasin**     de fichiers L’application de parcage d’appel utilise le magasin de fichiers pour contenir des fichiers audio personnalisés.

  - **Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table d’orbites de parcage d’appel et activer le parcage d’appel pour les utilisateurs.

  - **Lync Server Management Shell**     Toute la configuration de l’application parcage d’appel peut être effectuée à l’aide des applets de commande Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

