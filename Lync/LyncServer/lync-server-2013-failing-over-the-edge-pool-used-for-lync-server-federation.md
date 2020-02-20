---
title: 'Lync Server 2013 : basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e374337f261c6747bc1b147c9f2e02fa51efe3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Si le pool de serveurs Edge où la fédération Lync Server est configurée tombe en panne, vous devez modifier la fédération de manière à ce qu’elle utilise un pool de serveurs Edge différent pour la rendre opérationnelle.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Basculement du pool de serveurs Edge utilisé pour la fédération Lync Server

1.  Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **Pool de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.

2.  Dans **Modifier les propriétés**, sous **Général**, désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.

3.  Développez **Pool de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez à présent utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.

4.  Dans **Modifier les propriétés**, sous **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.

5.  Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.

6.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server**, puis sur **Installer ou supprimer des composants Lync Server**. Cliquez sur **Réexécuter**.

7.  Dans Installer les composants Lync Server, cliquez sur **Suivant**. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.
    
    Si le site contenant le pool de serveurs Edge ayant échoué contient des serveurs frontaux qui sont encore en cours d’exécution, vous devez mettre à jour le service de conférence web et le service de conférence A/V sur ces pools de serveurs frontaux afin d’utiliser un pool de serveurs Edge dans un site distant qui est encore en cours d’exécution. Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

