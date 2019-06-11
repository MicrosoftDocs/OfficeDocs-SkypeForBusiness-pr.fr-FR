---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Vérification de la coexistence du pool pilote avec le pool hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Vérifier le regroupement dans l’outil d’administration Office Communications Server 2007 R2

1.  Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.

2.  Développez le nœud de la **forêt** , développez le nœud **Standard Edition Servers** ou pools d' **entreprise** , puis développez le nom du pool ou du serveur.

3.  Vérifiez que les services Office Communications Server 2007 R2 s’exécutent sur le pool.
    
    ![Console d’administration Office Communications Server 2007 R2] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console d’administration Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Vérifier le pool de pilotes dans Lync Server 2013 panneau de configuration

1.  À partir d’un compte d’utilisateur membre du rôle CsAdministrator, connectez-vous au serveur frontal Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Topology**.

4.  Vérifiez que les serveurs que vous avez déployés sont répertoriés dans votre pool pilote.
    
    ![Page Topology du panneau de configuration de Lync Server] (images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Page Topology du panneau de configuration de Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Vérifiez que les services Lync Server 2013 ont démarré

1.  Sur le serveur frontal Lync Server 2013, ouvrez l’applet **services** à partir du groupe **Outils d’administration** .

2.  Vérifiez que les services répertoriés correspondent à la liste de la figure suivante.
    
    ![Page services indiquant le démarrage de Lync services] (images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Page services indiquant le démarrage de Lync services")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

