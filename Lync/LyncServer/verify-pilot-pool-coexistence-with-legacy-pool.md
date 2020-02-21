---
title: Vérifier la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c30f15b7a4e40b5c814ed5f21d07e213b69cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérifier la coexistence du pool pilote avec le pool hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Après avoir déployé le premier pool, vous devez vérifier la coexistence des deux pools à l’aide des outils d’administration pour afficher les informations des pools. Pour les pools hérités et les pools Lync Server 2013, vous devez utiliser le panneau de configuration Lync Server 2013 et les outils du générateur de topologies.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Vérifier que les services Lync Server 2013 ont démarré

1.  À partir du serveur frontal Lync Server 2013, accédez à l’applet\\services d’administration.

2.  Vérifiez que les services suivants sont exécutés sur le serveur frontal :

**Services Lync Server 2013**

![Liste des services Lync Server démarré](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste des services Lync Server démarré")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Ouvrir le panneau de configuration Lync Server 2013

À partir du serveur frontal de votre déploiement Lync Server 2013, ouvrez le panneau de configuration Lync Server 2013 et sélectionnez le pool Lync Server 2010. Répétez la procédure pour ouvrir le pool Lync Server 2013.

**Ouvrez le Panneau de configuration Lync Server 2013.**

![Boîte de dialogue Sélectionner une URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Boîte de dialogue Sélectionner une URL")

<div>


> [!IMPORTANT]  
> Sur Lync Server 2013, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le panneau de configuration Lync Server.



</div>

Cette topologie inclut désormais les rôles serveur Lync Server 2010 et Lync Server 2013.

**Page Topologie du Panneau de configuration Lync Server 2013**

![Panneau de configuration Lync Server-page topologie](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panneau de configuration Lync Server-page topologie")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Ne pas essayer d’ouvrir la topologie dans le générateur de topologies Lync Server 2010

Si vous tentez d’ouvrir la topologie à l’aide du générateur de topologie Lync Server 2010, vous rencontrerez l’erreur ci-dessous. La topologie peut uniquement être visualisée à l’aide du générateur de topologie Lync Server 2013. Le générateur de topologies Lync Server 2013 doit être utilisé pour créer des pools pour Lync Server 2013 et Lync Server 2010.

**Message d’erreur du générateur de topologie Lync Server 2010**

![Erreur du Snap MMC du générateur de topologies Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Erreur du Snap MMC du générateur de topologies Lync Server")

</div>

</div>

<span> </span>

</div>

</div>

</div>

