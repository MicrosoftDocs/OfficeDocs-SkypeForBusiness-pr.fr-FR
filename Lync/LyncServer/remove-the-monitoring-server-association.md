---
title: Supprimer l’Association du serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a12ec30f42106c3515376a0d408016e31c1cba5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Supprimer l’Association du serveur de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Pour supprimer l’association du serveur de surveillance

1.  Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où le serveur de surveillance est défini.

4.  Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable Branch Appliances</STRONG> dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance.

    
    </div>

5.  Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.

6.  Dans **Modifier les propriétés**, sous **Général**, sous **Associations**, décochez la case **Associer un serveur de surveillance**, puis cliquez sur **OK**.

7.  Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur de surveillance.

8.  Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**.

9.  Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.

10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.

</div>

</div>

<span> </span>

</div>

</div>

</div>

