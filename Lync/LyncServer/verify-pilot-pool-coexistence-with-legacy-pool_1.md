---
title: Vérifier la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3bdc71c1c45add045527a57efa0311ce37f79ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérifier la coexistence du pool pilote avec le pool hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Vérifier le pool dans l’outil d’administration d’Office Communications Server 2007 R2

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.

3.  Assurez-vous que les services Office Communications Server 2007 R2 sont en cours d’exécution sur le pool.
    
    ![Office Communications Server 2007 R2, console d’administration](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2, console d’administration")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Vérifier le pool pilote dans le panneau de configuration Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du rôle CsAdministrator, ouvrez une session sur le serveur frontal Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Topologie**.

4.  Vérifiez que les serveurs que vous avez déployés sont présents dans votre pool pilote.
    
    ![Page topologie du panneau de configuration Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Page topologie du panneau de configuration Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Vérifier que les services Lync Server 2013 ont démarré

1.  Sur le serveur frontal Lync Server 2013, ouvrez l’applet **services** à partir du groupe **Outils d’administration** .

2.  Vérifiez que les services répertoriés correspondent à la liste présentée dans la figure suivante.
    
    ![Page services affichant le démarrage de Lync services](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Page services affichant le démarrage de Lync services")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

