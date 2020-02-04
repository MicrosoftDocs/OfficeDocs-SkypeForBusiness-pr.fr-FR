---
title: 'Lync Server 2013 : désactivation de la contournement de média réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0457281a743d317e17a5fd0728e1a747b4d88271
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Désactivation de la contournement de média réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

Les paramètres de contournement de média s’appliquent globalement dans le déploiement de Microsoft Lync Server 2013. Bypass Media accepte les appels pour ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planification d’une dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section planification. Vous pouvez désactiver la dérivation multimédia du panneau de configuration de Lync Server. Pour plus d’informations sur l’activation et la configuration du contournement du son, voir [activation du contournement de média réseau dans Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Pour désactiver la dérivation multimédia

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **Global**.

4.  Dans la page **Global** , cliquez sur configuration **globale** . Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.

5.  Dans le menu **édition** , cliquez sur **afficher les détails**.

6.  Dans la page **modifier le paramètre global** , décochez la case **activer le contournement multimédia** .

7.  Cliquez sur **valider** pour enregistrer vos modifications.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activation du contournement de média réseau dans Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

