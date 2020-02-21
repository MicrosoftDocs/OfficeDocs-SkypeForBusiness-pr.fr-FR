---
title: 'Lync Server 2013 : état de réplication du magasin central de gestion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ada48a9510be6d6deecedf063156abadbd59162f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>État de réplication du magasin central de gestion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-01-26_

Lorsqu’un administrateur apporte une modification d’un type à Lync Server (par exemple, lorsqu’un administrateur crée une nouvelle stratégie de voix ou modifie les paramètres de configuration du serveur de carnet d’adresses), cette modification est enregistrée dans le magasin central de gestion. À son tour, la modification doit être répliquée sur tous les ordinateurs qui exécutent des services ou des rôles serveur Lync Server.

Pour répliquer des données, le réplicateur principal (exécuté sur le serveur de gestion centralisée) crée une capture instantanée des données de configuration modifiées. Une copie de cette capture instantanée est ensuite envoyée à chaque ordinateur exécutant des services ou des rôles serveur Lync Server. Sur ces ordinateurs, un agent de réplication reçoit la capture instantanée et télécharge les données modifiées. L’agent envoie ensuite au réplicateur principal un message signalant l’état de la réplication la plus récente.

La cmdlet Get-CsManagementStoreReplicationStatus vous permet de vérifier l’état de réplication de tout ou partie des ordinateurs Lync Server de votre organisation.

Qui peut exécuter cette applet de commande ? Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Get-CsManagementStoreReplicationStatus : RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

