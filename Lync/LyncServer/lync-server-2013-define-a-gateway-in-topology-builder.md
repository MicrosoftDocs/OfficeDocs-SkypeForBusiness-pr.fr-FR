---
title: 'Lync Server 2013 : définition d’une passerelle dans le générateur de topologies'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23286d5bb6cd8b1a1b695776258ad5e131743b8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Procédez comme suit pour utiliser le générateur de topologie afin de définir un *homologue* avec lequel vous pouvez associer un serveur de médiation pour fournir la connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs activés pour voix entreprise. Un homologue du serveur de médiation peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (session Border Controller) pour un fournisseur de services de téléphonie Internet (téléphonie Internet) auquel vous vous connectez en configurant une jonction SIP.

<div>


> [!NOTE]  
> Cette rubrique suppose que vous ayez configuré au moins un pool frontal interne ou un serveur Standard Edition dans au moins un site central avec un serveur de médiation colocalisé ou autonome, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation de déploiement. Cette rubrique suppose également que vous ayez vérifié que votre infrastructure répond aux exigences décrites dans <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Prerequisites for Enterprise Voice in Lync server 2013</A> et <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration Prerequisites for Enterprise Voice in Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Sous Lync Server 2013, le nom de votre site, composants partagés, cliquez avec le bouton droit sur le nœud **passerelles RTC** , puis cliquez sur **nouvelle passerelle PSTN**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Dans **Définir une nouvelle passerelle IP/PSTN**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez le protocole TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation.

    
    </div>

4.  Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle PSTN, puis cliquez sur **Suivant**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Définissez une *jonction racine* pour la passerelle PSTN. Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    {Nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP de passerelle et nom de domaine complet, port d’écoute de passerelle}
    
      - Lors de la définition d’une passerelle PSTN dans le générateur de topologie, vous devez définir une jonction racine pour pouvoir ajouter la passerelle PSTN à votre topologie.
    
      - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle PSTN associée n’est pas supprimée.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Sous **port d’écoute pour la passerelle IP/PSTN**, tapez le port d’écoute que la passerelle, PBX ou SBC utilisera pour les messages SIP provenant du serveur de médiation qui sera associé à la jonction racine de la passerelle PSTN. (Par défaut, les ports sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle PSTN, un autocommutateur privé (PBX) ou un contrôleur SBC. Sur un Survivable Branch appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)

7.  Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation pouvant utiliser le protocole TLS.

    
    </div>

8.  Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer à la jonction racine de cette passerelle PSTN.

9.  Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP à partir de la passerelle.
    
    <div>
    

    > [!NOTE]  
    > Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation afin d’être utilisés pour la communication avec plusieurs passerelles RTC. Lors de la définition d’une jonction, le <STRONG>port du serveur de médiation associé</STRONG> doit se situer dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Lync Server 2013 et pools de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez <STRONG>modifier les propriétés</STRONG>. Spécifiez la plage de ports dans le champ <STRONG>Ports d’écoute</STRONG>.

    
    </div>

10. Cliquez sur **Terminer**.

<div>


> [!IMPORTANT]  
> Avant de terminer cette étape, assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP que vous avez spécifié(e).



</div>

Ensuite, pour ajouter l’homologue à la topologie, suivez les procédures de la [publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement. Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie, afin que les données puissent être utilisées pour installer les fichiers pour les serveurs qui exécutent Lync Server.

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

