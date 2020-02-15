---
title: 'Lync Server 2013 : configuration des cartes réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurer les cartes réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Vous devez affecter une ou plusieurs adresses IP à la carte réseau externe et au moins une adresse IP à la carte réseau interne.

Dans les procédures suivantes, le serveur exécutant soit le service Forefront Threat Management Gateway (TMG) 2010, soit le routage des demandes d’application Internet Information Server a deux cartes réseau :

  - une carte réseau publique ou externe pour les clients qui tentent de se connecter à votre site web (habituellement par le biais d’Internet) ;

  - Une interface réseau privée, ou interne, pour les serveurs internes exécutant Lync Server qui hébergent des services Web.

<div>


> [!IMPORTANT]  
> De la même manière que pour les serveurs Edge, vous devez définir la passerelle par défaut sur la carte réseau externe uniquement. La passerelle par défaut est l’adresse IP du routeur ou du pare-feu côté externe qui dirige le trafic vers Internet. Pour le trafic destiné à la carte réseau côté interne face à partir du proxy inverse, vous devez utiliser des itinéraires statiques permanents (notamment la commande route dans Windows Server) pour tous les sous-réseaux contenant des serveurs référencés par les règles de publication web. La définition d’un itinéraire permanent n’entraîne pas l’ordinateur à devenir un routeur. Si le transfert IP n’est pas activé, l’ordinateur agit uniquement pour diriger le trafic spécifique destiné à un autre réseau vers l’interface appropriée. Il s’agit essentiellement de définir deux passerelles, une comme valeur par défaut pointant vers les réseaux externes, une pour le trafic destiné à l’interface interne et sur un routeur ou un autre réseau.<BR>Toutefois, la création d’itinéraires permanents pour tous les sous-réseaux peut ne pas être nécessaire si les routeurs de votre réseau sont configurés de manière à résumer les itinéraires. Créez un itinéraire permanent au réseau où le routeur est défini et utilisez le routeur comme passerelle par défaut. Si vous n’êtes pas sûr du mode de configuration de votre réseau et que vous avez besoin d’aide concernant les itinéraires permanents à créer, contactez les ingénieurs réseau de votre entreprise.<BR>Le proxy inverse doit être en mesure de résoudre les enregistrements d’hôte DNS (A) pour le serveur frontal ou le serveur frontal et les noms de domaine complets (FQDN) du pool du tronçon suivant utilisés dans les règles de publication Web. Comme pour les serveurs Edge, pour des raisons de sécurité, nous vous recommandons de ne pas configurer un proxy inverse pour utiliser un serveur DNS situé sur le réseau interne. Cela signifie que vous devez utiliser soit des serveurs DNS dans le périmètre, soit des entrées de fichier HOSTS sur le proxy inverse qui résout chacun de ces noms de domaine complets en adresse IP interne des serveurs.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Pour configurer les cartes réseau sur l’ordinateur de proxy inverse

1.  Sur le serveur Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 s’exécutant en tant que proxy inverse, ouvrez **modifier les paramètres** de la carte en cliquant sur **Démarrer**, en pointant sur panneau de **configuration**, en cliquant sur **Centre réseau et partage**, puis en cliquant sur **modifier les paramètres**de la carte.

2.  Cliquez avec le bouton droit sur la connexion réseau externe que vous souhaitez utiliser pour l’interface externe, puis cliquez sur **Propriétés**.

3.  Dans la page **Propriétés**, cliquez sur l’onglet **Réseau**, cliquez sur **Protocole Internet version 4 (TCP/IPv4)** dans la liste **Cette connexion utilise les éléments suivants**, puis cliquez sur **Propriétés**.

4.  Dans la page **Propriétés du protocole Internet (TCP/IP)**, configurez les adresses IP comme il convient pour le sous-réseau auquel la carte réseau est associée.
    
    <div>
    

    > [!NOTE]  
    > Si le proxy inverse est déjà utilisé par d’autres applications qui utilisent le protocole HTTPs/TCP/443, par exemple, pour la publication d’Outlook Web Access, vous devez ajouter une autre adresse IP afin de pouvoir publier les services Web Lync Server 2013 sur HTTPs/TCP/443 sans interférer avec les règles et les écouteurs Web existants, ou vous devez remplacer le certificat existant par un certificat qui ajoute les nouveaux noms de noms de domaine complets externes à l’autre nom de l’objet.

    
    </div>

5.  Cliquez sur **OK**, puis sur **OK**.

6.  Dans **Connexions réseau**, cliquez avec le bouton droit sur la connexion réseau interne que vous souhaitez utiliser pour l’interface interne, puis cliquez sur **Propriétés**.

7.  Répétez les étapes 3 à 5 pour configurer la connexion au réseau interne.

</div>

</div>

<span> </span>

</div>

</div>

</div>

