---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connexion du pool pilote aux serveurs Edge hérités

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Après le déploiement de Lync Server 2013, un itinéraire de Fédération pour ce site n’est pas configuré. Pour pouvoir utiliser l’itinéraire fédéré utilisé par Office Communications Server 2007 R2, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.

Pour permettre au site Lync Server 2013 d’utiliser le serveur directeur et le serveur de périphérie du BackCompatSite, utilisez le générateur de topologie pour associer le pool de bords hérité.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool de bords antérieurs à l’aide du générateur de topologie

1.  Ouvrez la topologie du pool de pilotes dans le générateur de topologie.

2.  Sélectionnez votre site Lync Server 2013.

3.  Dans le menu **action** , cliquez sur **modifier les propriétés**.

4.  Sous **affectation**de l’itinéraire de Fédération de site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur Office Communications Server 2007 R2 ou le serveur Office Communications Server 2007 R2, si aucun directeur n’est répertorié.
    
    ![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")  

5.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

6.  Dans le générateur de topologie, sous le nœud Lync Server 2013, accédez aux **Pools front end Server ou Enterprise Edition** **standard** , cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

7.  Sous **associations**, activez la case à cocher en regard de **associer le pool de bords (pour les composants multimédias)**.

8.  Dans la liste, sélectionnez l’interface du serveur Edge pour le BackCompatSite.
    
    ![Boîte de dialogue Modifier les propriétés, page général] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")  

9.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

10. Dans **Générateur de topologie**, sélectionnez le nœud supérieur, **Lync Server**.

11. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

12. À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

