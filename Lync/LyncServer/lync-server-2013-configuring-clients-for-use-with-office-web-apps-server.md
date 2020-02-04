---
title: 'Lync Server 2013 : configuration des clients pour une utilisation avec Office Web Apps Server'
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
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Configuration des clients de Lync Server 2013 pour une utilisation avec Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Si vous souhaitez que les utilisateurs bénéficient de toutes les fonctionnalités d’Office Web App Server, vous devez mettre à niveau ces utilisateurs vers Microsoft Lync 2013. Seuls les utilisateurs de Lync 2013 seront en mesure d’effectuer ces opérations dans les diapositives PowerPoint indépendamment de la présentation PowerPoint. (C’est-à-dire que ces utilisateurs peuvent examiner n’importe quelle diapositive de la présentation à tout moment, sans interférer avec la présentation réelle.) Les utilisateurs qui n’utilisent pas Lync 2013 pourront toujours accéder à des conférences en ligne et afficher la présentation PowerPoint. Toutefois, ils ne seront pas en mesure de faire défiler les diapositives, mais ils ne pourront pas voir les transitions entre les diapositives et afficher les vidéos incorporées.

Notez que ces fonctionnalités seront toujours accessibles aux utilisateurs de Lync 2013 ; C’est vrai même si le présentateur PowerPoint exécute Microsoft Lync 2010. Si une présentation PowerPoint est hébergée par un utilisateur exécutant Lync 2010, Lync Server 2013 coordonnéa avec Office Web Apps Server pour vérifier que les utilisateurs de Lync 2013 pourront voir la version Server d’Office Web Apps de cette présentation. Office Web Apps Server ne fournit pas de services PowerPoint aux utilisateurs exécutant des clients autres que Lync 2013. Au lieu de cela, les utilisateurs qui se connectent au service du serveur de conférence et d’afficher des présentations PowerPoint de la même façon que dans Microsoft Lync Server 2010. Cela signifie également que ces utilisateurs auront uniquement accès aux fonctionnalités les plus limitées proposées par Lync Server 2010.

Bien qu’il n’est pas nécessaire de configurer le client pour Office Web Apps Server (à l’exception de la mise à niveau des utilisateurs vers Lync 2013), il est recommandé de mettre à niveau vers Internet Explorer 9. Bien que les conférences puissent être consultées à l’aide d’Internet Explorer 8, il existe certaines limites à l’utilisation de ce navigateur Web. Par exemple, les utilisateurs d’Internet Explorer 8 ne seront pas en mesure de redimensionner la présentation PowerPoint à une taille personnalisée ; au lieu de cela, il est limité à l’utilisation d’une des trois tailles d’étapes prédéfinies. De même, les utilisateurs d’Internet Explorer 8 ne seront pas en mesure de lire des fichiers multimédias.

</div>

<span> </span>

</div>

</div>

</div>

