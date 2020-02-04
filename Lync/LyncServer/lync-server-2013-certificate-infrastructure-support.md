---
title: Prise en charge des infrastructures de certificat dans Lync Server 2013
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
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Prise en charge des infrastructures de certificat dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Lync Server 2013 nécessite une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS (Transport Layer Security) et Mutual TLS (MTLS). Par défaut, Lync Server 2013 est configuré de manière à utiliser TLS pour les connexions client-serveur. MTLS est utilisé pour les connexions entre les serveurs.

Les certificats MTLS doivent être émis par les autorités de certification de confiance pour Lync Server 2013. Lync Server prend en charge les certificats émis par les autorités de certification suivantes :

  - Certificats émis par une autorité de certification interne :
    
      - L’autorité de certification du système d’exploitation Windows Server 2003
    
      - L’autorité de certification du système d’exploitation Windows Server 2008
    
      - Autorité de certification du système d’exploitation Windows Server 2008 R2
    
      - L’autorité de certification du système d’exploitation Windows Server 2012
    
      - Autorité de certification du système d’exploitation Windows Server 2012 R2

  - Certificats émis par une autorité de certification publique

La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et d’autres produits Microsoft Server, dont Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation Open (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à la section [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenariat dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.

Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008 R2 et Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclut la prise en charge des certificats de l’SHA-256 fonction de hachage cryptographique. Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Pour plus d’informations sur les exigences relatives aux certificats, voir [configurations requises en matière d’infrastructure de certificats pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de caractères génériques avec des certificats, voir [prise en charge de certificat générique dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) dans la documentation relative à la prise en charge.

</div>

<span> </span>

</div>

</div>

</div>

