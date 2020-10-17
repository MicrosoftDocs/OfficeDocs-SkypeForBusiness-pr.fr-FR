---
title: Supprimer l’association au serveur d’archivage
description: Supprimez l’Association du serveur d’archivage.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f6c34e49b0217a8318a83752b3878a7625e5d58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570220"
---
# <a name="remove-the-archiving-server-association"></a>Supprimer l’association au serveur d’archivage

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.

<div>

## <a name="to-remove-the-archiving-server-association"></a>Pour supprimer l’association au serveur d’archivage

1.  Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où le serveur d’archivage est défini.

4.  Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable Branch Appliances</STRONG> dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance.

    
    </div>

5.  Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.

6.  Dans **Modifier les propriétés**, sous **Général**, sous **Associations**, désactivez la case à cocher **Associer un serveur d’archivage**, puis cliquez sur **OK**.

7.  Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur d’archivage que vous souhaitez supprimer.

8.  Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.

9.  Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.

10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.

</div>

</div>

<span> </span>

</div>

</div>

</div>

