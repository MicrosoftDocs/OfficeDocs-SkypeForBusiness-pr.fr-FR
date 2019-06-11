---
title: Configuration requise pour les infrastructures de certificat Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Configuration requise pour les infrastructures de certificat pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-06-23_

Lync Server 2013 a besoin d’une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS et Mutual TLS (MTLS).

Lync Server utilise des certificats aux fins suivantes:

  - Connexions TLS entre le client et le serveur

  - Connexions MTLS entre serveurs

  - Fédération utilisant une découverte automatique de DNS des partenaires

  - Accès des utilisateurs distants à la messagerie instantanée

  - Accès des utilisateurs externes aux sessions audio/vidéo (A/V), au partage d’application et aux conférences

  - Demandes mobiles utilisant la découverte automatique des services Web

Pour Lync Server, les exigences courantes suivantes s’appliquent:

  - Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).

  - Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).

  - Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Lync Server 2013 prend en charge la suite SHA-1 et SHA-2 de tailles synthétiques (224, 256, 384 et 512 bits) et répond ou dépasse la configuration requise du système d’exploitation. Pour la prise en charge du [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)système d’exploitation, voir.
    
    <div>
    

    > [!NOTE]  
    > L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels. 

    
    </div>

  - L’inscription automatique est prise en charge pour les serveurs internes exécutant Lync Server.

  - L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge Lync Server.

  - Lorsque vous envoyez une demande de certification basée sur le Web à une autorité de certification Windows Server 2003, vous devez la transmettre à partir d’un ordinateur exécutant Windows Server 2003 SP2 ou Windows XP.
    
    Notez que, même si KB922706 fournit une prise en charge de la résolution des problèmes liés à l’inscription de certificats Web sur un serveur de certification Windows Server 2003, il ne peut pas être utilisé Windows Server 2008, Windows Vista ou Windows 7 pour demander une certificat d’une autorité de certification Windows Server 2003.

  - Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.

  - L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH\_P256\_, ECDH P384 et\_ECDH P521 sont également pris en charge. 

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Certificats requis pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Exigences relatives aux certificats pour la mobilité dans Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

