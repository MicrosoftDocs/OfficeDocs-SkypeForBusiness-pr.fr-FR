---
title: Prise en charge de l’infrastructure de certificat Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea4ea71564feca6c23c6d9e16b4ca336fa95e87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Prise en charge de l’infrastructure de certificat dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Lync Server 2013 nécessite une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS (Transport Layer Security) et MTLS (Mutual TLS). Par défaut, Lync Server 2013 est configuré pour utiliser le protocole TLS pour les connexions client à serveur. MTLS est utilisé pour les connexions entre serveurs.

Les certificats MTLS doivent être émis par des autorités de certification approuvées pour Lync Server 2013. Lync Server prend en charge les certificats qui sont émis à partir des autorités de certification suivantes :

  - Certificats émis par une autorité de certification interne :
    
      - Autorité de certification de système d’exploitation Windows Server 2003
    
      - Autorité de certification de système d’exploitation Windows Server 2008
    
      - Autorité de certification du système d’exploitation Windows Server 2008 R2
    
      - Autorité de certification de système d’exploitation Windows Server 2012
    
      - Autorité de certification du système d’exploitation Windows Server 2012 R2

  - Certificats émis par une autorité de certification publique

La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et d’autres produits serveur Microsoft, y compris Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.

Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008 R2 et Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclut une prise en charge pour (mais pas pour autant que nécessaire) des certificats signés à l’aide de l’algorithme SHA-256 fonction de hachage de chiffrement. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Pour plus d’informations sur les certificats requis, voir [Certificate infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des caractères génériques avec des certificats, voir [générique Certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) dans la documentation de prise en charge.

</div>

<span> </span>

</div>

</div>

</div>

