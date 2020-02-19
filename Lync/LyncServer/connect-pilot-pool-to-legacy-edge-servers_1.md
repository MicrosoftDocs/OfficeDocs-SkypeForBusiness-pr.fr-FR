---
title: Connecter le pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ed4ae4b8714a4bd8e8969748fb62fa9f6bc5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connecter le pool pilote aux serveurs Edge hérités

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Après le déploiement de Lync Server 2013, un itinéraire de Fédération pour ce site n’est pas configuré. Pour utiliser l’itinéraire fédéré utilisé par Office Communications Server 2007 R2, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.

Pour activer le site Lync Server 2013 afin qu’il utilise le directeur et le serveur Edge du BackCompatSite, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool Edge hérité à l’aide du Générateur de topologie

1.  Ouvrez la topologie du pool pilote dans le Générateur de topologie.

2.  Sélectionnez votre site Lync Server 2013.

3.  Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.

4.  Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Office Communications Server 2007 R2 ou le serveur Edge Office Communications Server 2007 R2 si aucun directeur n’est mentionné.
    
    ![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")  

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

6.  Dans le générateur de topologie, sous le nœud Lync Server 2013, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.

7.  Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**.

8.  Dans la liste, sélectionnez l’interface de serveur Edge pour le BackCompatSite.
    
    ![Boîte de dialogue Modifier les propriétés, page général](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")  

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

10. Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Lync Server**.

11. Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.

12. Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

