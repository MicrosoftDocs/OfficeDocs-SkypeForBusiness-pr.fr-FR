---
title: 'Lync Server 2013 : définition d’une adresse IP de passerelle SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59b2d236cc9a261f07b2f2e9dc26102efff908f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Si Lync Server se connecte à la passerelle SIP/CSTA que vous avez déployée pour le contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez définir l’adresse IP de la passerelle dans le générateur de topologies. Cette étape n’est pas nécessaire pour les passerelles qui prennent en charge les connexions TLS (Transport Layer Security). Pour toute passerelle qui prend en charge les connexions TLS, vous pouvez ignorer cette procédure et continuer le déploiement du contrôle d’appel distant en suivant les étapes de la procédure [activer les utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Pour définir l’adresse IP de la passerelle SIP/CSTA à l’aide du Générateur de topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

3.  Choisissez l’option consistant à télécharger une topologie existante.

4.  Développez le nœud **Serveurs d’applications approuvés**.

5.  Cliquez avec le bouton droit sur le pool d’applications approuvées que vous avez créé, comme décrit dans [Configure a Trusted application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), puis cliquez sur **modifier les propriétés**.

6.  Désactivez la case à cocher **Activer la réplication des données de configuration sur ce pool**.

7.  Cliquez sur **Limiter l’utilisation des services aux adresses IP sélectionnées**. Le paramètre par défaut est **Utiliser toutes les adresses IP configurées**.

8.  Dans la zone de texte **Adresse IP principale**, entrez l’adresse IP de la passerelle SIP/CSTA.

9.  Pour mettre à jour la topologie dans le magasin central de gestion, dans l’arborescence de la console, cliquez sur **Lync Server**, puis, dans le volet **Actions**, cliquez sur **Publier**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

