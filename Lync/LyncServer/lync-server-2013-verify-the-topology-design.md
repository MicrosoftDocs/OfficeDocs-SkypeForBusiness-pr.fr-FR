---
title: 'Lync Server 2013 : vérifier la conception de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 361713c22842abee7de1d8e29de498f4d4ad5cc7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Vérifier la conception de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-02_

Le générateur de topologies vérifie automatiquement la topologie. Toute erreur de topologie est identifiée en tant qu’erreur de validation et signalée par l’icône d’erreur de validation en regard du rôle serveur. Il est également important de vérifier que la topologie représente correctement la topologie du déploiement.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Pour vérifier la topologie avant la publication

1.  Vérifiez que toutes les URL simples sont configurées correctement.

2.  Vérifiez que le serveur basé sur SQL Server est en ligne et disponible pour l’ordinateur sur lequel le générateur de topologies est installé, y compris les règles de pare-feu nécessaires.

3.  Confirmez que le partage de fichiers est disponible et qu’il dispose des autorisations appropriées qui ont été définies.

4.  Confirmez que les rôles serveur corrects qui répondent à la configuration requise pour le déploiement sont définis dans la topologie.

5.  Vérifiez que les serveurs existent dans les services de domaine Active Directory. Cela se produit automatiquement si vous avez joint les serveurs au domaine.

Lorsque vous avez vérifié la topologie et qu’aucune erreur de validation n’a été détectée, vous êtes prêt à publier la topologie. Si des erreurs de validation sont détectées, vous devez les corriger pour pouvoir publier la topologie. Pour plus d’informations sur la publication de votre topologie, voir [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

