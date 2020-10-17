---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
description: Vérifiez la Fédération et l’accès à distance pour les utilisateurs externes.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555070"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-18_

Après avoir effectué la transition de l’itinéraire de Fédération vers le serveur Edge Lync Server 2013, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération se comporte comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et de l’accès externe

  - Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.

  - Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010.

  - Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.

  - Un utilisateur hébergé sur Lync Server 2010 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2010 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.

  - Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Lync Server 2010. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.

</div>

</div>

<span> </span>

</div>

</div>

</div>

