---
title: 'Lync Server 2013 : définir des lignes supplémentaires dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Définir des lignes supplémentaires dans le générateur de topologies de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Suivez les étapes décrites ci-dessous pour utiliser le générateur de topologie et définir un Trunk supplémentaire auquel vous pouvez associer un *homologue* à un serveur de médiation. Un homologue fournit aux utilisateurs une connectivité voix entreprise compatible avec le réseau téléphonique commuté (PSTN). L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider). Le Trunk définit cette connexion entre le serveur de médiation et l’homologue. Vous pouvez définir plusieurs Trunks par serveur de médiation. Un serveur de médiation peut être associé à plusieurs homologues.

Un Trunk est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple :

Le nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : adresse IP et nom de domaine complet de la passerelle

<div>


> [!NOTE]  
> Cette rubrique part du principe que vous avez configuré une passerelle RTC et un Trunk racine avec au moins un serveur ou un pool de médiation autonome ou autonome comme décrit dans la rubrique <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">définir une passerelle dans le générateur de topologies de Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Cette rubrique part du principe que vous avez configuré au moins un pool frontal ou un serveur Standard Edition Server dans au moins un site central, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Sous Lync Server 2013, le nom de votre site, les **composants partagés**, cliquez avec le bouton droit sur le nœud **Trunks** , puis cliquez sur **nouveau Trunk**.
    
    ![Écran structure de fichiers du générateur de topologie de Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Écran structure de fichiers du générateur de topologie de Lync Server")

3.  Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.

    
    </div>

4.  Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.
    
    ![Paramètres de propriété pour l’homologue de passerelle PSTN pour Trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Paramètres de propriété pour l’homologue de passerelle PSTN pour Trunk")

5.  Sous **port d’écoute pour la passerelle RTC**, tapez le port d’écoute que le pair (passerelle PSTN, IP-PBX ou SBC) reçoit les messages SIP du serveur de médiation qui sera associé à ce Trunk. Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports de l’appareil de branchement Survivable par défaut sont 5081 pour TCP et 5082 pour TLS.

6.  Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS.

    
    </div>

7.  Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cet homologue.

8.  Sous **port du serveur de médiation associé**, tapez le port d’écoute sur lequel le serveur de médiation va recevoir des messages SIP de l’homologue.
    
    <div>
    

    > [!NOTE]  
    > Pour la prise en charge de plusieurs Trunks dans Lync Server 2013, il est impossible de configurer deux lignes avec des noms de Trunk différents avec le même <STRONG>port de serveur de médiation</STRONG> et le même port <STRONG>d’écoute pour la passerelle IP/PSTN</STRONG> .

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > La prise en charge de plusieurs Trunks dans Lync Server 2013 permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec des collègues multiples. Lors de la définition d’un Trunk, le numéro de <STRONG>port du serveur de médiation associé</STRONG> doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation. Cette plage de ports est définie sous Lync Server 2013 et les pools de serveurs de médiation. Cliquez avec le bouton droit sur la liste de serveurs de médiation appropriée, puis sélectionnez <STRONG>modifier les propriétés</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier un Trunk dans le générateur de topologies de Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

