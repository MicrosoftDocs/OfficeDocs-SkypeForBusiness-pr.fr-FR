---
title: Configuration d’un nœud observateur pour participer à la découverte de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b0d1fe5f2865f5c8797b2018ab8493bfb4d830c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configuration d’un nœud observateur dans Lync Server 2013 pour la participation à la découverte de System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Pour vous assurer que votre nœud observateur participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur un ordinateur sur lequel la console System Center Operations Manager a été installée :

1.  Sous l’onglet **Administration**, cliquez sur **Géré par agent**.

2.  Cliquez avec le bouton droit sur le nom de l’ordinateur du nœud observateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.

Après avoir configuré le nœud observateur pour qu’il se comporte comme un proxy, démarrez l’ordinateur du nœud observateur. Une fois l’ordinateur redémarré, vérifiez qu’aucun événement d’erreur n’est enregistré dans le journal des événements Operations Manager sur cet ordinateur. Une fois que l’ordinateur est en cours d’exécution pendant 15 minutes, utilisez la console Operations Manager pour vérifier que vos ordinateurs Lync Server sont répertoriés sous la catégorie **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

