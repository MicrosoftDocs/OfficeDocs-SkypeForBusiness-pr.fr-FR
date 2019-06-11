---
title: Supprimer l’association au serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5703153bb1034f1318fbe14ca3583ad5744ffdb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Supprimer l’association au serveur de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance. Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’Association du serveur de surveillance

1.  Ouvrez le serveur frontal Lync Server 2013, ouvrez le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Dans le générateur de topologie, développez **Pools frontal Enterprise Edition**, **serveurs front end Standard Edition**ou **sites**de succursales en fonction de la définition du serveur de surveillance.

4.  Si vous avez un serveur de succursales Survivable associé, développez **sites**de succursales, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG>appareils de branchement survivables</STRONG> dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant.

    
    </div>

5.  Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.

6.  Dans la boîte de **dialogue Modifier les propriétés**, sous **général**, sous **associations**, décochez la case associer le **serveur de suivi** , puis cliquez sur **OK**.

7.  Répétez l’étape précédente pour tout autre serveur ou appareil associé au serveur de surveillance.

8.  Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**.

9.  Sur **Supprimer les magasins**dépendants, cliquez sur **OK**.

10. Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Lync Server selon vos besoins.

</div>

</div>

<span> </span>

</div>

</div>

</div>

