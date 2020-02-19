---
title: Connecter le pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eea7d203638e891dbda1b91c53967a4632cc1df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connecter le pool pilote aux serveurs Edge hérités

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Après avoir déployé Lync Server 2013, vous devez configurer un itinéraire de Fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par Lync Server 2010, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.

Pour activer le site Lync Server 2013 afin qu’il utilise le directeur et le serveur Edge du déploiement de Lync Server 2010, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool Edge hérité à l’aide du Générateur de topologie

1.  Ouvrez le **Générateur de topologie**.

2.  Sélectionnez votre site, qui est affiché juste en dessous du nœud **Lync Server**.

3.  Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **Itinéraire de fédération**.

5.  Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Lync Server 2010 ou le serveur Edge Lync Server 2010 si aucun directeur n’est mentionné.
    
    ![Modifier les propriétés, page itinéraire de Fédération](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")  

6.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

7.  Dans le générateur de topologie, sous le nœud Lync Server 2013, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.

8.  Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.

9.  Dans la liste, sélectionnez le serveur Edge hérité.
    
    ![Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, sélection du serveur Edge hérité")  

10. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

11. Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.

12. Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.

13. Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

