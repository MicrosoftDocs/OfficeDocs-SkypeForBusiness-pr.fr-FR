---
title: 'Lync Server 2013 : configuration des clients pour une utilisation avec Office Web Apps Server'
description: 'Lync Server 2013 : configuration des clients pour une utilisation avec Office Web Apps Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9bd7cf1e76c481c40381234ba1a84cda5500dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545520"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Configuration des clients de Lync Server 2013 pour une utilisation avec Office Web Apps Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Si vous souhaitez que les utilisateurs bénéficient des fonctionnalités complètes d’Office Web App Server, vous devez mettre à niveau ces utilisateurs vers Microsoft Lync 2013 ; Seuls les utilisateurs de Lync 2013 seront en mesure de faire défiler les diapositives PowerPoint indépendamment de la présentation réelle de PowerPoint. (En d’autres termes, ces utilisateurs peuvent consulter toutes les diapositives de la présentation à tout moment, sans gêner leur présentation.) Les utilisateurs qui n’utilisent pas Lync 2013 pourront toujours participer à des conférences en ligne et afficher la présentation PowerPoint ; Toutefois, ils ne pourront pas faire défiler les diapositives indépendamment et ne pourront pas voir les transitions de diapositives ou afficher des vidéos incorporées.

Notez que ces fonctionnalités sont toujours disponibles pour les utilisateurs de Lync 2013 ; Cela est vrai même si le présentateur PowerPoint exécute Microsoft Lync 2010. Si une présentation PowerPoint est hébergée par un utilisateur de Lync 2010, Lync Server 2013 est coordonné avec Office Web Apps Server pour s’assurer que les utilisateurs de Lync 2013 afficheront la version d’Office Web Apps Server de cette présentation. Office Web Apps Server ne fournit pas de services PowerPoint pour les utilisateurs qui exécutent des clients autres que Lync 2013. Au lieu de cela, ces utilisateurs se connectent au service de serveur de conférence et affichent des présentations PowerPoint de la même manière que dans Microsoft Lync Server 2010. Cela signifie également que ces utilisateurs auront uniquement accès aux fonctionnalités plus limitées proposées par Lync Server 2010.

Bien qu’aucune configuration client ne soit requise pour Office Web Apps Server (autre que la mise à niveau des utilisateurs vers Lync 2013), il est recommandé que les participants à la Conférence soient mis à niveau vers Internet Explorer 9. Les conférences peuvent être accédées via Internet Explorer 8, mais cela comporte certaines limites. Par exemple, les utilisateurs de ce navigateur ne peuvent pas redimensionner la fenêtre PowerPoint de manière personnalisée ; ils sont limités à l؊’utilisation de l’une des trois tailles de fenêtre prédéfinies. Ils ne peuvent pas non plus lire des fichiers multimédia.

</div>

<span> </span>

</div>

</div>

</div>

