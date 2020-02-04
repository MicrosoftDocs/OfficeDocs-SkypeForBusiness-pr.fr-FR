---
title: 'Lync Server 2013 : marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les applications serveur MSPL (Microsoft SIP Processing Language) sont des applications qui utilisent le langage de script MSPL au lieu de l’API 2010 Microsoft Lync. Certaines applications serveur MSPL sont spécifiées comme étant critiques. Si le script est essentiel, le script doit commencer au démarrage du système pour que Lync Server 2013 commence. Si le script échoue alors que Lync Server est en cours d’exécution, le serveur ne s’arrête pas, mais il cesse d’envoyer du trafic au script et il écrit les erreurs dans le journal des événements.

Vous pouvez utiliser le panneau de configuration de Lync Server pour marquer les applications serveur MSPL (Microsoft SIP Processing Language) comme étant critiques ou annuler la marque.

Tous les scripts ne prennent pas en charge cette option. Par exemple, le script DefaultRouting est marqué comme Critical et cette option ne peut pas être modifiée pour DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Pour marquer ou démarquer une application serveur MSPL comme essentielle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **topologie** , puis sur **application serveur**.

4.  Dans la page de l' **application serveur** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant, puis cliquez sur l’application serveur que vous voulez modifier.

5.  Cliquez sur **action**.

6.  Cliquez sur **marquer comme critique** ou **désélectionner comme critique** (autrement dit, si le script prend en charge cette option).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

