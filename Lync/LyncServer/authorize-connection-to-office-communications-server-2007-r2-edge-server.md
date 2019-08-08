---
title: Autoriser la connexion à un serveur Edge Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc5d92b45f65c864da046951ce7ebd42155ed2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autoriser la connexion à un serveur Edge Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Pour chaque serveur principal Lync Server 2013 ou Standard Edition Server dans votre pool de pilotes, vous devez mettre à jour la liste des serveurs internes autorisés à se connecter au serveur Edge Office Communications Server 2007 R2. Sans ces mises à jour, les conférences audio/vidéo externes (A/V) pour les utilisateurs qui rejoignent l’utilisation du serveur Edge hérité ne fonctionneront pas.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Pour autoriser la connexion à un serveur Edge Office Communications Server 2007 R2

1.  À partir du serveur Office Communications Server 2007 R2 Edge, accédez au groupe **Outils d’administration** , puis ouvrez le composant logiciel enfichable Gestion de l' **ordinateur** .

2.  Dans l’arborescence de la console, développez **services et applications**.

3.  Cliquez avec le bouton droit sur **Office Communications Server 2007 R2**, puis cliquez sur **Propriétés**.

4.  Cliquez sur l’onglet **interne** .

5.  Sous **Ajouter un serveur**, cliquez sur **Ajouter**.

6.  Dans la boîte de dialogue **Ajouter un serveur Office Communications Server** , entrez les informations appropriées:
    
      - Spécifiez le nom de domaine complet (FQDN) de chaque serveur frontal Lync Server 2013 ou Standard Edition Server et de Lync Server 2013 pool.
    
      - Spécifiez le nom de domaine complet (FQDN) du réalisateur Lync Server 2013 si vous avez configuré un itinéraire statique sur le pool qui spécifie l’ordinateur tronçon suivant par son nom de domaine complet.

7.  Après avoir ajouté une entrée pour chaque serveur Lync Server 2013, serveur frontal, serveur Standard Edition, pool et directeur, cliquez sur **appliquer** , puis sur **OK** pour fermer la page Propriétés.

</div>

</div>

<span> </span>

</div>

</div>

</div>

