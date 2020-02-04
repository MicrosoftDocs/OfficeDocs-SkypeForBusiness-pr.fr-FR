---
title: 'Lync Server 2013 : définir une passerelle dans le générateur de topologie'
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
ms.openlocfilehash: 18f257648ba24930eaab0d314e34178ffd67a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Définir une passerelle dans le générateur de topologies de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Suivez les étapes ci-dessous pour définir un *homologue* qui vous permet d’associer un serveur de médiation afin de fournir une connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs autorisés à utiliser voix entreprise. Un hôte du serveur de médiation peut être une passerelle RTC, un PBX IP ou un contrôleur de bordure de session (SBC) pour un fournisseur de services de téléphonie Internet (ITSP) auquel vous vous connectez en configurant un Trunk SIP.

<div>


> [!NOTE]  
> Dans cette rubrique, nous partons du principe que vous avez configuré au moins une réserve interne ou un serveur Standard Edition Server dans au moins un site central doté d’un serveur de médiation autonome ou autonome, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">la rubrique définir et configurer un pool frontal ou un serveur Standard Edition Server dans Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans la documentation de déploiement. Dans cette rubrique, nous partons également du principe que vous avez vérifié que votre infrastructure répond aux conditions préalables décrites dans la rubrique <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">logiciels requis pour Enterprise Voice de Lync server 2013</A> et de <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">sécurité et configuration requise pour Enterprise Voice dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Sous Lync Server 2013, le nom de votre site, composants partagés, cliquez avec le bouton droit sur le nœud **passerelles RTC** , puis cliquez sur **nouvelle passerelle PSTN**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.

    
    </div>

4.  Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Définissez une *jonction racine* pour la passerelle RTC. Un Trunk est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    Le nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : adresse IP et nom de domaine complet de la passerelle
    
      - Lors de la définition d’une passerelle RTC dans le générateur de topologie, vous devez définir une Trunk racine pour ajouter correctement la passerelle RTC à votre topologie.
    
      - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Sous **port d’écoute pour la passerelle RTC/IP**, tapez le port d’écoute que la passerelle, le PBX ou la SBC utilisera pour les messages SIP du serveur de médiation qui sera associé au Trunk racine de la passerelle RTC. (Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC. Sur une unité de branchement Survivable sur une succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)

7.  Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS.

    
    </div>

8.  Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cette passerelle PSTN.

9.  Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP de la passerelle.
    
    <div>
    

    > [!NOTE]  
    > La prise en charge de l’utilisation de circuits multiples dans Lync Server 2013 permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour communiquer avec plusieurs passerelles RTC. Lors de la définition d’un Trunk, le <STRONG>port du serveur de médiation associé</STRONG> doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation. Cette plage de ports est définie sous Lync Server 2013 et les pools de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez <STRONG>modifier les propriétés</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

10. Cliquez sur **Terminer**.

<div>


> [!IMPORTANT]  
> Avant d’achever cette étape, assurez-vous que l’homologue que vous avez défini s’exécute et utilise le nom de domaine complet ou l’adresse IP que vous avez spécifiée.



</div>

Ensuite, pour ajouter l’homologue à la topologie, suivez les procédures décrites dans [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement. Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour générer ou modifier votre topologie, de telle sorte que les données puissent être utilisées pour installer les fichiers pour les serveurs exécutant Lync Server.

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

