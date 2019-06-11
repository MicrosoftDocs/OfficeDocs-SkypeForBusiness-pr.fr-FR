---
title: Vérification de l’environnement Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Vérification de l’environnement Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-16_

Avant de déployer Lync Server 2013 dans un état de coexistence avec Office Communications Server 2007 R2, vous devez vérifier que les services Office Communications Server 2007 R2 sont configurés et démarrés.

**Vérifier que le pool est démarré à l’aide de l’outil d’administration Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.

2.  Développez le nœud de la **forêt** , développez le nœud **Standard Edition Servers** ou pools d' **entreprise** , puis développez le nom du pool ou du serveur.

3.  Vérifiez que les services s’exécutent sur le serveur Standard Edition Server ou le pool d’entreprise.
    
    ![Console d’administration Office Communications Server 2007 R2] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console d’administration Office Communications Server 2007 R2")

**Examiner les utilisateurs configurés pour Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.

2.  Développez le nœud de la **forêt** , développez le nœud **Standard Edition Servers** ou pools d' **entreprise** , puis développez le nom du pool ou du serveur.

3.  Cliquez sur **utilisateurs**.

4.  Vérifiez la liste des utilisateurs d’Office Communications Server 2007 R2.
    
    ![Listing FO Users dans l’outil d’administration OCS] (images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Listing FO Users dans l’outil d’administration OCS")

**Vérification de la configuration de partenaire fédéré hérité de XMPP**

1.  À partir du serveur XMPP hérité, accédez à l’applet\\services des outils d’administration.

2.  Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré.
    
    ![Service de passerelle Office Communications Server XMPP] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle Office Communications Server XMPP")

</div>

<span> </span>

</div>

</div>

</div>

