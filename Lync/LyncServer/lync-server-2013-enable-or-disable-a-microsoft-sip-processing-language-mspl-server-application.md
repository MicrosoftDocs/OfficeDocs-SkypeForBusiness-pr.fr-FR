---
title: 'Lync Server 2013: activation ou désactivation d’une application serveur Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Le panneau de configuration de Lync Server vous permet d’activer ou de désactiver les applications serveur MSPL (Microsoft SIP Processing Language) qui s’exécutent dans votre environnement Lync Server 2013. Ces applications sont des applications uniquement basées sur des scripts qui utilisent un langage de script au lieu de l’API Microsoft Lync 2013 preview.

Tous les scripts ne peuvent pas être activés ou désactivés. Par exemple, le script DefaultRouting est activé, et cette option ne peut pas être modifiée pour DefaultRouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Pour activer ou désactiver une application serveur MSPL

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **topologie** , puis sur **application serveur**.

4.  Dans la page de l' **application serveur** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant, puis cliquez sur l’application serveur que vous voulez modifier.

5.  Cliquez sur **action**.

6.  Cliquez sur **activer l’application** ou désactiver l' **application** (autrement dit, si le script prend en charge cette option).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

