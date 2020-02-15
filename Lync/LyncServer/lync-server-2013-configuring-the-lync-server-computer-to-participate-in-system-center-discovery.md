---
title: Configuration de l’ordinateur Lync Server pour la participation à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b59622306fbde12eb570b72c95b37cec7885c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configuration de l’ordinateur Lync Server 2013 pour la participation à la découverte de System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Pour vous assurer que votre nouvel agent Lync Server participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée :

1.  Sous l’onglet **Administration**, cliquez sur **Géré par agent**.

2.  Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.

Une fois l’étape 2 terminée, redémarrez le service Agent d’intégrité. (Le redémarrage du service va « forcer » la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, la découverte du nouvel ordinateur par le System Center Operations Manager peut prendre jusqu’à 4 heures.). Une fois le service redémarré, vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager sur cet ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

