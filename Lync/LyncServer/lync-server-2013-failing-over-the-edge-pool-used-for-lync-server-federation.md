---
title: 'Lync Server 2013 : Basculement vers le pool Edge utilisé pour la fédération Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

Si le pool de périphériques sur lequel vous avez configuré Lync Server Federation s’affiche, vous devez modifier la Fédération de manière à utiliser un pool de périphérie différent pour que la Fédération fonctionne.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Échec du pool Edge utilisé pour la Fédération Lync Server

1.  Sur un serveur frontal, ouvrez le générateur de topologie. Développez pools de **bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération. Sélectionnez **modifier les propriétés**.

2.  Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**. Cliquez sur **OK**.

3.  Développez pools de **bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous voulez utiliser pour la Fédération. Sélectionnez **modifier les propriétés**.

4.  Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.

5.  Cliquez sur **action**, sélectionnez **topologie**, puis **publier**. Lorsque le système vous **le**demande, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.

6.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **installer ou mettre à jour le système serveur Lync**, puis cliquez sur **configurer ou supprimer les composants Lync Server**. Cliquez de **nouveau sur exécuter**.

7.  Dans configurer les composants serveur Lync, cliquez sur **suivant**. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool de périphériques en échec contient des serveurs frontaux qui sont toujours en cours d’exécution, vous devez mettre à jour les services de conférence Web et de conférence A/V sur ces pools frontal pour qu’ils utilisent un pool de bords sur un site distant qui est toujours en cours d’exécution. Pour plus d’informations, reportez-vous à [la section changement du pool de bords associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

