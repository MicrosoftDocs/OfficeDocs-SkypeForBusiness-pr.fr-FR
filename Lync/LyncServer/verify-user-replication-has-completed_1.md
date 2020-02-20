---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b526bd5dc6c451d8e8bd9998043d20a7c185f6b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Lors de l’exécution de la cmdlet **Move-CsLegacyUser** , vous pouvez être confronté à un échec dû à des informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Lync Server 2013 désynchronisées car la réplication initiale est incomplète. Le temps nécessaire à la synchronisation initiale de Lync Server 2013 le service Réplicateur d’utilisateurs dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory hébergeant le pool Lync Server 2013. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs Lync Server 2013 se produit lorsque le serveur frontal Lync Server 2013 est démarré pour la première fois. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Procédez comme suit pour vérifier que la réplication utilisateur est terminée avant d’exécuter la cmdlet **Move-CsLegacyUser** .

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Pour vérifier que la réplication utilisateur est terminée

1.  À partir du serveur frontal Lync Server 2013, cliquez sur le menu **Démarrer** , puis sur **exécuter**.

2.  Entrez **eventvwr.exe**, puis cliquez sur **OK**.

3.  Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.

4.  Dans le volet **Actions**, cliquez sur **Filtrer le journal actuel**.

5.  Dans la liste **Sources de l’événement**, cliquez sur **LS User Replicator**.

6.  Dans ** \<tous les ID\> d’événement** , entrez **30024** , puis cliquez sur **OK**.

7.  Dans la liste des événements filtrés, dans l’onglet **Général**, recherchez une entrée qui stipule que la réplication utilisateur s’est achevée avec succès.

</div>

</div>

<span> </span>

</div>

</div>

</div>

