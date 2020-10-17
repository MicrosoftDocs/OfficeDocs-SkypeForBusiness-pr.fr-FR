---
title: 'Lync Server 2013 : démarrer les services sur les serveurs'
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
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532961"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>Démarrer des services sur des serveurs pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-03_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées adéquates. Pour plus d’informations sur la délégation d’autorisations, consultez la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Après avoir installé le magasin de configuration local sur vos serveurs, installé les composants Lync Server 2013 et configuré des certificats sur un serveur frontal ou un serveur frontal, vous devez démarrer les services Lync Server 2013 sur le serveur. Utilisez la procédure suivante pour démarrer les services sur chaque serveur frontal de votre déploiement.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Pour démarrer les services sur un serveur frontal ou Standard Edition

1.  Dans l’Assistant Déploiement de Lync Server, sur la page **Lync server 2013** , cliquez sur **exécuter** à côté de **étape 4 : démarrer les services**.

2.  Sur la page **Démarrer les services** , cliquez sur **suivant** pour démarrer les services Lync Server sur le serveur.

3.  Sur la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour vérifier que les services ont bien démarré, nous vous recommandons d’utiliser la commande de démarrage des services sur le serveur. Cependant, il est possible qu’elle n’indique pas l’état actuel du service. Nous vous recommandons de suivre l’étape <STRONG>État des services (facultatif)</STRONG> juste après <STRONG>Démarrage de services</STRONG> pour ouvrir la console MMC (Microsoft Management Console) et confirmer que les services ont correctement démarré. Si un service Lync Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC, puis cliquer sur <STRONG>Démarrer</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

