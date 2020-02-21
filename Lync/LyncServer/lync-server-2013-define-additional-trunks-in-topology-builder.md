---
title: 'Lync Server 2013 : définir des jonctions supplémentaires dans le générateur de topologies'
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
ms.openlocfilehash: d5632a5f28a5a56d077235e28be41c19b5496c10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Définir d’autres jonctions dans le générateur de topologies dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Procédez comme suit pour utiliser le générateur de topologie afin de définir une jonction supplémentaire à laquelle vous pouvez associer un *homologue* à un serveur de médiation. Un homologue fournit aux utilisateurs activés pour voix entreprise la connectivité au réseau téléphonique commuté (PSTN). Un homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (session Border Controller) pour un fournisseur de services de téléphonie Internet (téléphonie Internet). La jonction définit cette connexion entre le serveur de médiation et l’homologue. Plusieurs jonctions peuvent être définies par serveur de médiation. Un serveur de médiation peut être associé à plusieurs homologues.

Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple :

{Nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP de passerelle et nom de domaine complet, port d’écoute de passerelle}

<div>


> [!NOTE]  
> Cette rubrique suppose que vous avez configuré une passerelle PSTN et une jonction racine avec au moins un serveur ou pool de médiation colocalisé ou autonome, comme décrit dans <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a Gateway in Topology Builder in Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Cette rubrique suppose que vous ayez configuré au moins un pool frontal ou un serveur Standard Edition dans au moins un site central, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir une jonction supplémentaire entre un serveur de médiation et un homologue de passerelle

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Sous Lync Server 2013, le nom de votre site, **composants partagés**, cliquez avec le bouton droit sur le nœud **jonctions** , puis cliquez sur **nouvelle jonction**.
    
    ![Écran structure des fichiers du générateur de topologie Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Écran structure des fichiers du générateur de topologie Lync Server")

3.  Dans **define New jonction**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Vous ne pouvez pas avoir deux jonctions de même nom.
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez le protocole TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.

    
    </div>

4.  Sous **passerelle RTC associée**, sélectionnez l’homologue de passerelle PSTN à associer à cette jonction.
    
    ![Paramètres de propriété pour l’homologue de passerelle PSTN pour jonction](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Paramètres de propriété pour l’homologue de passerelle PSTN pour jonction")

5.  Sous **port d’écoute pour la passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) reçoit les messages SIP du serveur de médiation qui doit être associé à cette jonction. Les ports d’homologue par défaut sont 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security). Les ports Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.

6.  Sous **protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation pouvant utiliser le protocole TLS.

    
    </div>

7.  Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer à la jonction racine de cet homologue.

8.  Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation recevra les messages SIP de l’homologue.
    
    <div>
    

    > [!NOTE]  
    > Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, deux jonctions avec différents noms de jonctions ne peuvent pas être configurées avec le même <STRONG>port de serveur de médiation</STRONG> et le même <STRONG>port d’écoute pour la passerelle IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation pour la communication avec plusieurs homologues. Lors de la définition d’une jonction, le numéro de <STRONG>port du serveur de médiation associé</STRONG> doit être compris dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Lync Server 2013 et pools de serveurs de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation approprié, puis sélectionnez <STRONG>modifier les propriétés</STRONG>. Spécifiez la plage de ports dans le champ <STRONG>Ports d’écoute</STRONG>.

    
    </div>

9.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier une jonction dans le générateur de topologies dans Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

