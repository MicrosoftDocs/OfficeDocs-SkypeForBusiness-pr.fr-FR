---
title: 'Lync Server 2013 : validation de la configuration d’Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1cabdf03250a056c2fedaeb41e1f6839aea75a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validation de la configuration d’Office Web Apps Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-22_

Une fois qu’Office Web Apps Server a été ajouté à la topologie et une fois la topologie publiée, vous devez voir deux nouveaux événements de journal des événements dans le journal des événements Lync Server. Tout d’abord, un événement de MCU de données LS (ID d’événement 41034) doit être ajouté ; Cet événement signale que le serveur Office Web Apps a été découvert :

**Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**

En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :

**Serveur de conférence Web la découverte d’Office Web Apps Server a réussi.**

**Page du présentateur interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Page du participant interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Page du présentateur externe Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Page du participant interne Office Web Apps Server :https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si un événement LS Data MCU ayant l’ID d’événement 41033 s’affiche, cela signifie que la découverte d’Office Web Apps Server na pas fonctionné. Dans ce cas, Microsoft Lync Server 2013 essaiera autant de fois que nécessaire pour découvrir le serveur Office Web Apps nouvellement configuré. Si le processus de découverte ne fonctionne pas à chaque essai, nous vous conseillons de supprimer Office Web Apps Server de votre document de topologie, de publier la topologie mise à niveau, puis d’essayer de rajouter Office Web Apps Server à votre topologie une fois les problèmes de topologie résolus.

Si Office Web Apps Server semble être configuré correctement et qu’il a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Microsoft Lync 2013. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et si l’utilisateur B peut ensuite rejoindre la réunion et consulter la présentation, alors Office Web Apps Server fonctionne correctement.

Même si Office Web Apps Server semble être configuré correctement, il est possible que le message d’erreur suivant s’affiche : « Certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité de serveur » lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés à la nouvelle configuration d’Office Web Apps Server.

</div>

<span> </span>

</div>

</div>

</div>

