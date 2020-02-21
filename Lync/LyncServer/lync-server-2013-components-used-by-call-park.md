---
title: 'Lync Server 2013 : composants utilisés par le parcage d’appel'
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
ms.openlocfilehash: 2a6585663ac6dedcd83e00ca4abc4f57047fcb7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Composants utilisés par le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-13_

L’application de parcage d’appel est installée automatiquement lorsque vous déployez voix entreprise. Vous activez le parcage d’appel en configurant la stratégie de voix. Les composants Lync Server 2013 suivants prennent en charge l’application de parcage d’appel :

  - **Application service**   application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que l’application de parcage d’appel. Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.

  - **Application de parcage d’appel**   l’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application. Il est inclus automatiquement lorsque vous déployez Voix Entreprise. Appeler des parcs de parcage et récupère les appels et gère les orbites de parcage d’appel.

  - **Musique-en attente-fichier**   si la musique est activée, le fichier de musique est lu pendant le parcage d’un appel. Un fichier de musique par défaut est inclus lors de l’installation de l’application de parcage d’appel.

  - **Magasin de fichiers**   l’application de parcage d’appel utilise le magasin de fichiers pour contenir des fichiers audio personnalisés.

  - **Panneau de configuration Lync Server**   vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table d’orbites de parcage d’appel et activer le parcage d’appel pour les utilisateurs.

  - **Lync Server Management Shell**   la configuration de l’application de parcage d’appel peut être effectuée à l’aide des applets de commande Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

