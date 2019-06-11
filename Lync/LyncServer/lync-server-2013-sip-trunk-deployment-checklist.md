---
title: Liste de vérification du déploiement de la jonction SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Avant de pouvoir déployer un connecteur SIP, votre fournisseur de services et vous devez échanger des informations de connexion de base sur les points de terminaison de votre connecteur SIP correspondants.

Obtenez les informations suivantes pour chaque passerelle ITSP à laquelle vous voulez vous connecter:

  - Adresse IP

  - Nom de domaine complet (FQDN)

<div>


> [!NOTE]  
> Le prestataire de services pourra vous demander de vous connecter à plusieurs passerelles ITSP. Dans ce cas, vous devez configurer une connexion entre chaque passerelle ITSP et chaque serveur de médiation de votre pool.



</div>

Les informations que vous fournissez à votre fournisseur de services dépendent de votre type de connexion SIP Trunk:

  - Pour les connexions au changement d’étiquette multiprotocole ou au réseau privé, attribuez à l’ITSP l’adresse IP routable publique du routeur dans votre réseau de périmètre (également connu sous le nom de DMZ, zone démilitarisée et sous-réseau filtré). Vérifiez que la passerelle ou le contrôleur de bordure de session (SBC) sur le ITSP peut joindre cette adresse. Donnez également au ITSP le nom de domaine complet du serveur de médiation.

  - Pour les connexions de réseau privé virtuel (VPN), attribuez l’adresse IP du serveur VPN à ITSP.

<div>

## <a name="certificate-considerations"></a>Considérations relatives aux certificats

Pour déterminer si vous avez besoin d’un certificat pour le trunking SIP, contactez votre ITSP à propos du protocole pris en charge:

1.  Si votre ITSP prend en charge le protocole TCP (Transmission Control Protocol) uniquement, vous n’avez pas besoin d’un certificat.

2.  Si votre ITSP prend en charge le protocole TLS (Transport Layer Security), ITSP doit vous fournir un certificat.

<div>


> [!NOTE]  
> SIP fonctionne conjointement avec le protocole RTP (Real-Time Transport Protocol) ou SRTP (Secure Real-Time Transport Protocol), les protocoles qui gèrent les données vocales réelles dans les appels VoIP.



</div>

</div>

<div>

## <a name="deployment-process"></a>Processus de déploiement

Pour implémenter le côté serveur Lync de la connexion SIP Trunk, procédez comme suit:

1.  À l’aide du générateur de topologie de Lync Server, créez et configurez la topologie de domaine SIP. Pour plus d’informations, reportez-vous à la section [définir et configurer une topologie dans le générateur de topologies de Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) dans la documentation de déploiement.

2.  À l’aide du panneau de configuration de Lync Server, configurez le routage vocal pour le nouveau domaine SIP. Pour plus d’informations, reportez-vous à la rubrique [configuration de Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md) dans la documentation de déploiement.

3.  Testez la connectivité à l’aide de l’applet de **contrôle test-CsPstnOutboundCall** . Pour plus d’informations, reportez-vous à la documentation de Lync Server Management Shell ou à l’aide de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

