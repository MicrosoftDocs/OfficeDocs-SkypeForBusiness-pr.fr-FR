---
title: 'Lync Server 2013 : démarrer ou arrêter les services Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4396a6110337cfb9d3abdbd8136c78246b12bced
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>Démarrer ou arrêter les services Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Vous pouvez utiliser le panneau de configuration Lync Server pour démarrer ou arrêter tous les services Lync Server 2013 en cours d’exécution sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>Pour démarrer ou arrêter tous les services Lync Server sur un ordinateur

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013. Vous pouvez déterminer si vous avez reçu le CsServerAdministrator ou le rôle RBAC CsAdministrator en exécutant une commande semblable à la suivante :
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Démarrer tous les services** ou **Arrêter tous les services**.

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>Pour démarrer ou arrêter un service spécifique

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Propriétés**.

6.  Triez la liste de services, si nécessaire et cliquez sur le service que vous souhaitez démarrer ou arrêter.

7.  Cliquez sur **Action**.

8.  Cliquez sur **Démarrer le service** ou **Arrêter le service**.

9.  Cliquez sur **Fermer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Empêcher les sessions pour les services dans Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

