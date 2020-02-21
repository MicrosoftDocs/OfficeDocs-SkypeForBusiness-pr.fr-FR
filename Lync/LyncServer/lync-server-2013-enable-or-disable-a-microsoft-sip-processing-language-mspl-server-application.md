---
title: 'Lync Server 2013 : activation ou désactivation d’une application serveur MSPL (Microsoft SIP Processing Language)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19f9918aa1740c8ac80e2c2a51466f5bf2022b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Vous pouvez utiliser le panneau de configuration Lync Server pour activer ou désactiver les applications serveur MSPL (Microsoft SIP Processing Language) qui s’exécutent dans votre environnement Lync Server 2013. Ces applications script uniquement utilisent un langage de script au lieu de l’API de prévisualisation Microsoft Lync 2013.

Il n’est pas possible d’activer ou de désactiver tous les scripts. Par exemple, le script DefaultRouting est activé et ce paramètre ne peut pas être modifié pour DefaultRouting.

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>Pour activer ou désactiver une application serveur MSPL

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.

4.  Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Activer l’application** ou sur **Désactiver l’application** (si le script prend en charge cette option).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

