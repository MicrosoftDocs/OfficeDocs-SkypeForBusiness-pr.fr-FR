---
title: Connexion du pool pilote aux serveurs Edge hérités
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
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connexion du pool pilote aux serveurs Edge hérités

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Après le déploiement de Lync Server 2013, vous devez configurer un itinéraire de Fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par Lync Server 2010, Lync Server 2013 doit être configuré pour utiliser cet itinéraire.

Pour permettre au site Lync Server 2013 d’utiliser le directeur et le serveur de périphérie du déploiement de Lync Server 2010, utilisez le générateur de topologie pour associer le pool de bords hérités.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool de bords antérieurs à l’aide du générateur de topologie

1.  Ouvrez le **Générateur de topologie**.

2.  Sélectionnez votre site, qui se trouve juste en dessous du nœud du **serveur Lync** .

3.  Dans le menu **actions** , cliquez sur **modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **gamme de Fédération**.

5.  Sous **affectation**de l’itinéraire de Fédération de site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le serveur Lync Server 2010 ou le serveur Edge Lync Server 2010 si aucun réalisateur n’est répertorié.
    
    ![Modifier les propriétés, page itinéraire de Fédération](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")  

6.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

7.  Dans le générateur de topologie, sous le nœud Lync Server 2013, accédez aux **Pools front end Server ou Enterprise Edition** **standard** , cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

8.  Sous **associations**, activez la case à cocher en regard de **associer le pool de bords (pour les composants multimédias)**.

9.  Dans la liste, sélectionnez le serveur de bord hérité.
    
    ![Boîte de dialogue Modifier les propriétés, sélection du bord hérité](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, sélection du bord hérité")  

10. Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

11. Dans **Générateur de topologie**, sélectionnez le nœud supérieur, **Lync Server**.

12. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

13. À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

