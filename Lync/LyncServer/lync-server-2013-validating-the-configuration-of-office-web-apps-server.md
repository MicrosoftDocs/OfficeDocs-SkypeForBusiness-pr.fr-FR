---
title: 'Lync Server 2013: vérification de la configuration d’Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validation de la configuration d’Office Web Apps Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-04-22_

Une fois qu’Office Web Apps Server a été ajouté à la topologie et après la publication de cette topologie, vous devriez voir deux nouveaux événements du journal des événements dans le journal des événements de Lync Server. D’abord, un événement LS Data MCU (ID d’événement 41034) devrait être ajouté, cet événement va signaler la découverte du serveur Office Web Apps :

**Le serveur de conférence Web Office Web Apps Server est découvert, le contenu PowerPoint est activé.**

En plus de cela, un autre événement LS Data MCU devrait être affiché (ID d’événement 41032), retournant les URL du serveur Office Web Apps. Par exemple, vous devriez voir un message semblable à :

**La découverte du serveur de conférence Web Office Web Apps Server a réussi.**

**Page de présentateur interne d’Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Page Office Web Apps Server en interne:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Page de présentateur externe d’Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Page Office Web Apps Server en interne:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si vous voyez un événement MCU de données LS avec l’ID d’événement de 41033 qui signifie que la découverte d’Office Web Apps Server a échoué. Dans ce cas, Microsoft Lync Server 2013 essaie autant de fois que nécessaire pour découvrir le serveur Office Web Apps que vous venez de configurer. Si le processus de découverte échoue à plusieurs reprises, il est recommandé de supprimer Office Web Apps Server de votre document topologique, de publier la topologie mise à jour, puis de réessayer d’ajouter Office Web Apps Server à la topologie suite à la résolution des problèmes de connectivité.

Si Office Web Apps Server semble correctement configuré et a été reconnu par le processus de découverte, vous pouvez vérifier qu’Office Web Apps Server fonctionne comme prévu en partageant une présentation PowerPoint entre deux clients Microsoft Lync 2013. Si l’utilisateur A peut charger et afficher la présentation PowerPoint et s’il peut rejoindre la réunion et voir cette présentation, Office Web Apps Server fonctionne.

Même si Office Web Apps Server semble correctement configuré, vous pouvez recevoir le message d’erreur «certaines fonctionnalités de partage ne sont pas disponibles en raison de problèmes de connectivité du serveur» lorsque vous essayez de partager une présentation PowerPoint. Si vous recevez ce message d’erreur, vous devez redémarrer le ou les serveurs frontaux associés au nouveau serveur Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

