---
title: 'Lync Server 2013 : Définition d’une adresse IP de passerelle SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Si Lync Server se connecte à la passerelle SIP/CSTA déployée pour le contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez définir l’adresse IP de la passerelle dans le générateur de topologie. Cette étape n’est pas nécessaire pour les passerelles qui prennent en charge les connexions TLS (Transport Layer Security). Pour toute passerelle qui prend en charge les connexions TLS, vous pouvez ignorer cette procédure et poursuivre le déploiement du contrôle d’appel distant en suivant les étapes décrites dans l’article [permettre aux utilisateurs de Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Pour définir l’adresse IP de la passerelle SIP/CSTA à l’aide du générateur de topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

3.  Sélectionnez l’option de téléchargement d’une topologie existante.

4.  Développez le nœud **serveurs d’applications de confiance** .

5.  Cliquez avec le bouton droit sur le pool d’applications approuvé que vous avez créé, comme décrit dans [la rubrique Configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), puis cliquez sur **modifier les propriétés**.

6.  Décochez la case **activer la réplication des données de configuration pour ce pool** .

7.  Cliquez sur **limiter l’utilisation du service aux adresses IP sélectionnées**. Le paramètre par défaut est **utiliser toutes les adresses IP configurées**.

8.  Dans la zone de texte **adresse IP principale** , entrez l’adresse IP de la passerelle SIP/CSTA.

9.  Pour mettre à jour la topologie dans le magasin central de gestion, dans l’arborescence de la console, cliquez sur **Lync Server**, puis, dans le volet **actions** , cliquez sur **publier**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

