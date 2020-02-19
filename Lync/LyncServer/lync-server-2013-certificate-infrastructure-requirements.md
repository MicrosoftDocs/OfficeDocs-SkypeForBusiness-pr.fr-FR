---
title: Configuration requise pour l’infrastructure de certificat Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd1aa5bdde1c94e3d0558be14c67cf62ec8142a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour l’infrastructure de certificat pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-23_

Lync Server 2013 nécessite une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS et Mutual TLS (MTLS).

Lync Server utilise des certificats aux fins suivantes :

  - Connexions TLS entre client et serveur

  - Connexions MTLS entre serveurs

  - Fédération à l’aide de la découverte automatique de partenaires via le DNS

  - Accès des utilisateurs distants à la messagerie instantanée

  - Accès des utilisateurs externes aux sessions audio/vidéo (A/V), au partage d’application et aux conférences

  - Demandes mobiles utilisant la découverte automatique de services web

Pour Lync Server, les exigences communes suivantes s’appliquent :

  - Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).

  - Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).

  - Tous les certificats doivent être signés à l’aide d’un algorithme de signature pris en charge par le système d’exploitation. Lync Server 2013 prend en charge la suite SHA-1 et SHA-2 de tailles de condensé (224, 256, 384 et 512 bits) et répond ou dépasse la configuration requise du système d’exploitation. Pour la prise en charge du [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)système d’exploitation, voir.
    
    <div>
    

    > [!NOTE]  
    > L’utilisation de l’algorithme de signature RSASSA-PSS n’est pas prise en charge et peut entraîner des erreurs de connexion et de transfert d’appel, entre autres problèmes.

    
    </div>

  - L’enregistrement automatique est pris en charge pour les serveurs internes exécutant Lync Server.

  - L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge Lync Server.

  - Pour soumettre une demande de certificat web à une Autorité de certification Windows Server 2003, vous devez utiliser un ordinateur exécutant Windows Server 2003 avec SP2 ou Windows XP.
    
    Notez que bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription avec les services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une Autorité de certification Windows Server 2003.

  - Les longueurs de clés de chiffrement de 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé de 2048 et supérieures sont recommandées.

  - L’algorithme de chiffrement par défaut, ou signature de hachage, est RSA. Les algorithmes ECDH\_P256\_, ECDH P384 et\_ECDH P521 sont également pris en charge. 

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Conditions requises pour les certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Conditions requises pour le certificat pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Exigences relatives aux certificats pour la mobilité dans Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

