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
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Vérifier que la réplication utilisateur est terminée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Lors de l’exécution de l’applet de contrôle **Move-CsLegacyUser** , il est possible que vous constatiez un échec en raison d’informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Lync Server 2013 en dehors de la synchronisation, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool 2013 Server. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 se produit lorsque le serveur frontal de Lync Server 2013 est démarré pour la première fois. Après cela, la synchronisation est alors basée sur l’intervalle du réplicateur d’utilisateurs. Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet **de commande Move-CsLegacyUser** .

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Pour vérifier que la réplication des utilisateurs est terminée

1.  À partir du serveur frontal Lync Server 2013, cliquez sur le menu **Démarrer** , puis sur **exécuter**.

2.  Entrez **eventvwr. exe** , puis cliquez sur **OK**.

3.  Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.

4.  Dans le volet **actions** , cliquez sur **filtrer le journal actuel**.

5.  Dans la liste **sources d’événements** , cliquez sur réplicateur d' **utilisateurs LS**.

6.  Dans ** \<tous les ID\> d’événement** entrez **30024** , puis cliquez sur **OK**.

7.  Dans la liste des événements filtrés, sous l’onglet **général** , recherchez une entrée qui indique que la réplication des utilisateurs s’est déroulée correctement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

