---
title: Vérifier que la réplication utilisateur est terminée
description: Vérifiez que la réplication utilisateur est terminée.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555480"
---
# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Lors de l’exécution de la cmdlet **Move-Csuser** , vous pouvez être confronté à un échec car les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Lync Server 2013 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la synchronisation initiale de Lync Server 2013 le service Réplicateur d’utilisateurs dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory hébergeant le pool Lync Server 2013. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs Lync Server 2013 se produit lorsque le serveur frontal Lync Server 2013 est démarré pour la première fois. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Procédez comme suit pour vérifier que la réplication utilisateur est terminée avant d’exécuter la cmdlet **Move-Csuser** .

<div>

## <a name="to-verify-user-replication-has-completed"></a>Pour vérifier que la réplication utilisateur est terminée

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Cliquez sur le menu **Démarrer**, puis sur **Exécuter**.

3.  Entrez **eventvwr.exe**, puis cliquez sur **OK**.

4.  Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.

5.  Dans le volet **Actions**, cliquez sur **Filtrer le journal actuel**.

6.  Dans la liste **Sources de l’événement**, cliquez sur **LS User Replicator**.

7.  Dans **\<All Event IDs\>** entrez **30024** , puis cliquez sur **OK**.

8.  Dans la liste des événements filtrés, dans l’onglet **Général**, recherchez une entrée qui stipule que la réplication utilisateur s’est achevée avec succès.

</div>

</div>

<span> </span>

</div>

</div>

</div>

