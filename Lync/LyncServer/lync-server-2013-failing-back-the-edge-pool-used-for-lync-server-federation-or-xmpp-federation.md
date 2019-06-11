---
title: Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Après un échec de remise du pool de frontière d’hébergement de la Fédération, utilisez la procédure suivante pour restaurer le routage de Fédération de Lync Server et/ou l’itinéraire de Fédération XMPP pour qu’il utilise de nouveau ce pool de périphéries restauré.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Échec de la Fédération d’arrière-plan vers un pool de périphérie restauré

1.  Sur le pool Edge qui est désormais disponible, démarrez les services Edge.

2.  Si vous souhaitez restaurer l’itinéraire de Fédération de Lync Server pour utiliser le serveur de périphérie restauré, procédez comme suit:
    
      - Sur un serveur frontal, ouvrez le générateur de topologie. Développez pools de **bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération. Sélectionnez **modifier les propriétés**.
    
      - Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**. Cliquez sur **OK**.
    
      - Développez pools de **bords**, puis cliquez avec le bouton droit sur le serveur Edge d’origine ou sur le pool de serveurs Edge que vous souhaitez utiliser pour la Fédération. Sélectionnez **modifier les propriétés**.
    
      - Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.
    
      - Cliquez sur **action**, sélectionnez **topologie**, puis **publier**. Lorsque le système vous **le**demande, cliquez sur **suivant**. Lorsque la publication est terminée, cliquez sur **Terminer**.
    
      - Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **installer ou mettre à jour le système serveur Lync**, puis cliquez sur **configurer ou supprimer les composants Lync Server**. Cliquez de **nouveau sur exécuter**.
    
      - Dans configurer les composants serveur Lync, cliquez sur **suivant**. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Si vous souhaitez restaurer l’itinéraire de la Fédération XMPP de manière à utiliser le serveur de périphérie de restauration, procédez comme suit:
    
      - Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers le pool Edge qui hébergera maintenant la Fédération de XMPP (dans cet exemple, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Dans cet exemple, site1 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer1.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.
    
      - Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous. Cet enregistrement SRV doit avoir une valeur de port de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.
    
      - Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.

4.  Si le pool frontal restait en cours d’exécution sur le site contenant le pool de périphériques ayant échoué et a été restauré, vous devez mettre à jour les services de conférence Web et de service de conférence A/V sur ces pools frontal pour pouvoir utiliser les pools de périphérie sur leur site local. Pour plus d’informations, reportez-vous à [la section changement du pool de bords associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Si le pool frontal sur le même site que le pool d’échecs en panne ne fonctionne pas, vous pouvez désormais utiliser Invoke-CsPoolFailback pour restaurer le pool frontal.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

