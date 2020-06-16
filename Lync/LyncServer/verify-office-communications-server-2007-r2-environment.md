---
title: Vérifier l’environnement Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a7ba7e51e6dd1f6e42aeddfbbbd4ce7581d3fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Vérifier l’environnement Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Avant de déployer Lync Server 2013 dans un état de coexistence avec Office Communications Server 2007 R2, vous devez vérifier que les services Office Communications Server 2007 R2 sont configurés et démarrés.

**Vérifier que le pool est démarré à l’aide de l’outil d’administration Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, développez le nœud **Serveurs Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.

3.  Vérifiez que les services sont exécutés sur le serveur Standard Edition ou le pool d’entreprise.
    
    ![Office Communications Server 2007 R2, console d’administration](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2, console d’administration")

**Passez en revue les utilisateurs configurés pour le serveur Office Communications Server 2007 R2**

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.

3.  Cliquez sur **Utilisateurs**.

4.  Vérifiez la liste des utilisateurs d’Office Communications Server 2007 R2.
    
    ![Répertorier les utilisateurs dans l’outil d’administration OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Répertorier les utilisateurs dans l’outil d’administration OCS")

**Vérifiez la configuration de partenaire fédéré XMPP héritée**

1.  À partir du serveur XMPP hérité, accédez à l’application outils d’administration \\ services.

2.  Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.
    
    ![Service de passerelle XMPP Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle XMPP Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

