---
title: 'Lync Server 2013 : activation d’Office Web Apps Server et de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7da09c42c296aa842cd82693a63c5ec6efc4964
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Configuration de l’intégration avec Office Web Apps Server et Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-08-19_

Lync Server 2013 utilise Office Web Apps Server pour gérer les présentations PowerPoint. Pour plus d’informations sur les avantages de cette approche, reportez-vous à la rubrique [vue d’ensemble de la conférence Web dans Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Pour pouvoir utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 pour communiquer avec Office Web Apps Server. Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server. Cette documentation ne fournit pas d’informations sur l’installation d’Office Web Apps Server lui-même ; Pour plus d’informations, consultez le site Web de déploiement de Microsoft <https://go.microsoft.com/fwlink/p/?linkid=257525>Office Web Apps à l’adresse. Ce guide inclut des informations préalables sur les éléments prérequis pour Office Web Apps Server ; Notez qu’Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, Microsoft SQL Server ou toute autre application serveur. (Aucune version de Microsoft Office n’est installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également disposer d’un ensemble spécifique de logiciels installés (y compris .NET Framework 4,5 et Windows PowerShell 3,0); ces conditions requises, ainsi que des informations sur la configuration des certificats et des services Internet (IIS), sont décrites en détail dans le site Web de déploiement <https://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps à l’adresse.

<div>


> [!NOTE]  
> La dernière itération d’Office Web Apps Server est appelée Office Online Server, qui est pris en charge par Lync Server 2013. Pour plus d’informations, reportez-vous à la <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentation d’Office Online Server</A>.



</div>

Ce document aborde les sujets suivants :

  - [Configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Publication d’Office Web Apps Server dans Lync Server 2013 à l’aide d’un serveur proxy inverse](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Validation de la configuration d’Office Web Apps Server dans Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configuration des clients de Lync Server 2013 pour une utilisation avec Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

