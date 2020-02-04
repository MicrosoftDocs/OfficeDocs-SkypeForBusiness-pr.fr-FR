---
title: Empêcher les nouvelles connexions à Lync Server pour la maintenance du serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Empêcher les nouvelles connexions à Lync Server 2013 pour la maintenance du serveur

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à jour logicielles ou matérielles) sans perte de service aux utilisateurs.

Lorsque vous spécifiez l’option permettant d’éviter de nouvelles connexions ou appels vers un serveur d’un pool, il cesse de prendre de nouvelles connexions et appels dès que vous implémentez cette option. Ces nouvelles connexions et appels sont routés par le biais d’autres serveurs du pool. Un serveur qui empêche de nouvelles connexions autorise la poursuite de ses sessions sur les connexions existantes jusqu’à ce qu’il se termine de façon naturelle. Lorsque toutes les sessions existantes sont terminées, le serveur est prêt à être déconnecté.

Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Lync Server dépendent de l’équilibrage de charge DNS pour s’assurer qu’elle fonctionne correctement. Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs au cours de la période pendant laquelle le serveur empêche les nouvelles connexions, et par conséquent, lorsque le serveur est hors connexion, certaines sessions et appels peuvent être garantir. Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :

  - Intendant

  - application d’annonce de conférence

  - application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

Outre qu’il n’est pas possible d’empêcher les nouvelles connexions de tous les services sur un serveur exécutant Lync Server, vous pouvez également éviter de nouvelles connexions pour les services Lync Server individuels. Par exemple, cette méthode est utile dans le cas où vous devez appliquer une mise à jour du serveur Lync qui ne nécessite pas l’arrêt de l’intégralité du serveur. Notez que lorsque vous interdisez les connexions d’un service, vous devez sélectionner un service tel qu’il est groupé et affiché dans la liste des services Windows. Par exemple, le service frontal de Lync Server et l’agent de collecte des données pour la surveillance sont des services Lync Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés comme le service frontal de Lync Server. Vous pouvez empêcher de nouvelles connexions pour le service frontal de Lync Server, mais vous ne pouvez pas empêcher les nouvelles connexions de ces deux services Lync Server sous-jacents séparément.

<div>


> [!IMPORTANT]
> Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage. Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Pour éviter de nouvelles connexions à Lync Server :

1.  Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2.  Ouvrez la console enfichable Services : cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.

3.  Dans la liste, double-cliquez sur le service Windows Server Lync pour lequel vous voulez empêcher les nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **État du service : démarré**, cliquez sur **suspendre**.

5.  Si vous le souhaitez, mais que vous avez le choix, en regard de **type de démarrage**, cliquez sur **Manuel**.
    
    <div>
    

    > [!IMPORTANT]
    > Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage. Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.

    
    </div>

6.  Lorsque vous avez terminé, cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

