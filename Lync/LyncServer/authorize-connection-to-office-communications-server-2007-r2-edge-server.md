---
title: Autoriser la connexion au serveur Edge Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6adeaa07efea62697ecfbd38fede7d2f2191b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autoriser la connexion au serveur Edge Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Pour chaque serveur frontal Lync Server 2013 ou serveur Standard Edition dans votre pool pilote, vous devez mettre à jour la liste des serveurs internes autorisés à se connecter au serveur Edge Office Communications Server 2007 R2. Sans ces mises à jour, les conférences audio/vidéo (A/V) externes ne peuvent pas fonctionner pour les participants qui utilisent un serveur Edge hérité.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Pour autoriser la connexion au serveur Edge Office Communications Server 2007 R2

1.  À partir du serveur Edge Office Communications Server 2007 R2, à partir du groupe **Outils d’administration** , ouvrez le composant logiciel enfichable Gestion de l' **ordinateur** .

2.  Dans l’arborescence de la console, développez **Services et applications**.

3.  Cliquez avec le bouton droit sur **Office Communications Server 2007 R2**, puis sur **Propriétés**.

4.  Cliquez sur l’onglet **Interne**.

5.  Sous **Ajouter un serveur**, cliquez sur **Ajouter**.

6.  Dans la boîte de dialogue **Ajouter Office Communications Server**, entrez les informations appropriées :
    
      - Spécifiez le nom de domaine complet (FQDN) de chaque serveur frontal Lync Server 2013 ou serveur Standard Edition, ainsi que le pool Lync Server 2013.
    
      - Spécifiez le nom de domaine complet (FQDN) du directeur Lync Server 2013 si vous avez configuré un itinéraire statique sur le pool qui spécifie l’ordinateur du tronçon suivant par son nom de domaine complet (FQDN).

7.  Une fois que vous avez ajouté une entrée pour chaque Lync Server 2013, serveur frontal, serveur Standard Edition, pool et directeur, cliquez sur **appliquer** , puis sur **OK** pour fermer la page Propriétés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

