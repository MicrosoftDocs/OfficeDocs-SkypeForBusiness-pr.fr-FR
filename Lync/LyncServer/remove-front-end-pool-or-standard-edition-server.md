---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92b6f0dc28c44d3a77bd5af2ff67a61e2f23973f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Supprimer un pool frontal ou un serveur Standard Edition

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez tous les serveurs frontaux qui appartiennent au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du magasin SQL du générateur de topologies.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Pour supprimer un pool de serveurs frontaux

1.  Ouvrez le Générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **Pools frontaux Enterprise Edition**, développez le pool frontal, cliquez avec le bouton droit sur le pool frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.

4.  Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Pour supprimer un serveur frontal Standard Edition

1.  Ouvrez le Générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **serveurs frontaux Standard Edition**, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.

4.  Développez **magasins SQL**, cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Standard Edition, puis cliquez sur **supprimer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez supprimer la définition des bases de données SQL Server colocalisées à partir du serveur frontal Standard Edition.

    
    </div>

5.  Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server selon vos besoins.

</div>

</div>

<span> </span>

</div>

</div>

</div>

