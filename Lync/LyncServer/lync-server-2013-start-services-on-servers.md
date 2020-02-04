---
title: 'Lync Server 2013 : démarrer des services sur les serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6474071e7f95228f3c04c4931b4f899df68b40
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Démarrer des services sur les serveurs pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-03_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations appropriées déléguées. Pour plus d’informations sur la délégation d’autorisations, voir la rubrique [autorisations de configuration de délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Une fois que vous avez installé le magasin de configuration local sur vos serveurs, installé les composants Lync Server 2013 et configuré des certificats sur un serveur frontal ou un serveur frontal, vous devez démarrer les services Lync Server 2013 sur le serveur. Utilisez la procédure suivante pour démarrer des services sur chaque serveur frontal de votre déploiement.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Pour démarrer des services sur un serveur frontal ou édition standard

1.  Dans l’Assistant Déploiement de Lync Server, sur la page **Lync server 2013** , cliquez sur **exécuter** à côté de l' **étape 4 : démarrer les services**.

2.  Dans la page **Démarrer des services** , cliquez sur **suivant** pour démarrer les services Lync Server sur le serveur.

3.  Dans la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > La commande permettant de démarrer les services sur le serveur est la méthode la plus efficace pour signaler que les services ont bien démarré. Cependant, il est possible qu’elle n’indique pas l’état réel du service. Nous vous recommandons d’utiliser l’état du service d’étape <STRONG>(facultatif)</STRONG> immédiatement après les <STRONG>services de démarrage</STRONG> pour ouvrir la console MMC (Microsoft Management Console) et vérifier que les services ont bien démarré. Si un service Lync Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC, puis cliquer sur <STRONG>Démarrer</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

