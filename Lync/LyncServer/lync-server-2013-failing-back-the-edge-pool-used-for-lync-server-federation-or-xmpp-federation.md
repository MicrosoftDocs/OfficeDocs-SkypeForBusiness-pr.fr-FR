---
title: Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lorsqu’un pool Edge en échec qui hébergeait la fédération a été remis en ligne, suivez cette procédure pour restaurer l’itinéraire de fédération Lync Server et/ou l’itinéraire de fédération XMPP pour réutiliser ce pool Edge restauré.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Restauration de la fédération sur un pool Edge restauré

1.  Sur le pool Edge de nouveau disponible, lancez les Services Edge.

2.  Si vous voulez restaurer l’itinéraire de fédération Lync Server pour utiliser le serveur Edge restauré, procédez comme suit :
    
      - Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **Pools Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.
    
      - Dans **Modifier les propriétés**, sous **Général**, désactivez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.
    
      - Développez **Pools Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge d’origine que vous voulez réutiliser pour la fédération. Sélectionnez **Modifier les propriétés**.
    
      - Dans **Modifier les propriétés**, sous **Général**, sélectionnez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.
    
      - Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.
    
      - Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server**, puis sur **Installer ou supprimer des composants Lync Server**. Cliquez sur **Réexécuter**.
    
      - Sur la page Configurer les composants Lync Server, cliquez sur **Suivant**. L’écran de résumé affiche les actions lorsqu’elles sont exécutées. Une fois le déploiement terminé, cliquez sur **Voir le journal** pour voir les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :
    
      - Exécutez la cmdlet suivante pour pointer de nouveau l’itinéraire de fédération XMPP sur le pool Edge qui héberge désormais la fédération XMPP (dans cet exemple, EdgeServer1) :
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Dans cet exemple, Site1 représente le site qui contient le pool Edge qui hébergera désormais l’itinéraire de fédération XMPP, et EdgeServer1.contoso.com représente le nom de domaine complet (FQDN) d’un serveur Edge de ce pool.
    
      - Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.
    
      - Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.

4.  Si les pools frontaux ont continué à s’exécuter sur le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour les services de conférence web et de conférence A/V sur ces pools frontaux pour réutiliser les pools Edge sur leur site local. Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Si le pool frontal du site où le pool Edge a échoué échoue également, vous pouvez désormais utiliser Invoke–CsPoolFailback pour restaurer le pool frontal.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

