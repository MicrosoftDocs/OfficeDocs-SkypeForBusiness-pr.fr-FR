---
title: 'Lync Server 2013 : marquez une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique'
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
ms.openlocfilehash: 42c40b115e81736cbbf8769292ab251953d3a752
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524761"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les applications serveur MSPL (Microsoft SIP Processing Language) sont des applications script uniquement qui utilisent le langage de script MSPL au lieu de l’API 2010 de Microsoft Lync. Certaines applications serveur MSPL sont spécifiées comme critiques. Si un script est critique, le script doit démarrer pendant le démarrage du système afin que Lync Server 2013 puisse démarrer. Si le script échoue lorsque Lync Server est en cours d’exécution, le serveur ne s’arrête pas, mais il cesse d’envoyer du trafic au script et il écrit des erreurs dans le journal des événements.

Vous pouvez utiliser le panneau de configuration Lync Server pour marquer les applications serveur MSPL (Microsoft SIP Processing Language) comme critiques ou ne pas les marquer.

Les scripts ne prennent pas tous en charge cette option. Par exemple, le script DefaultRouting est marqué comme critique, et cette option ne peut pas être modifiée pour DefaultRouting.

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>Pour marquer ou démarquer une application serveur MSPL comme critique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.

4.  Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Marquer comme critique** ou **Désélectionner comme critique** (si le script prend en charge cette option).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

