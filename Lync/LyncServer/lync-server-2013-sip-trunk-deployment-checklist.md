---
title: 'Lync Server 2013 : liste de vérification du déploiement de la jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08beaff401b8f261d311ad0d05a07f5221131864
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Avant de pouvoir déployer une jonction SIP, vous et votre fournisseur de services devez échanger des informations de connexion de base concernant vos points de terminaison de jonction SIP respectifs.

Obtenez les informations suivantes pour chaque passerelle téléphonie Internet à laquelle vous allez vous connecter :

  - Adresse IP

  - nom de domaine complet (FQDN)

<div>


> [!NOTE]  
> Le fournisseur de services peut vous demander de vous connecter à plusieurs passerelles téléphonie Internet. Dans ce cas, vous devez configurer une connexion entre chaque passerelle téléphonie Internet et chaque serveur de médiation de votre pool.



</div>

Les informations que vous accordez à votre fournisseur de services dépendent de votre type de connexion de jonction SIP :

  - Pour les connexions de réseau privé (MPLS) ou VPN, donnez à l’téléphonie Internet l’adresse IP routable publique du routeur dans votre réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré). Vérifiez que la passerelle ou le contrôleur de frontière de session (SBC) de l’téléphonie Internet peut atteindre cette adresse. Donnez également au téléphonie Internet le nom de domaine complet de votre serveur de médiation.

  - Pour les connexions de réseau privé virtuel (VPN), attribuez à l’téléphonie Internet l’adresse IP de votre serveur VPN.

<div>

## <a name="certificate-considerations"></a>Considérations relatives aux certificats

Pour déterminer si vous avez besoin d’un certificat pour la jonction SIP, consultez votre téléphonie Internet à propos de la prise en charge du protocole :

1.  Si votre téléphonie Internet prend en charge le protocole TCP (Transmission Control Protocol) uniquement, vous n’avez pas besoin de certificat.

2.  Si votre téléphonie Internet prend en charge le protocole TLS (Transport Layer Security), le téléphonie Internet doit vous fournir un certificat.

<div>


> [!NOTE]  
> Le protocole SIP fonctionne en association avec le protocole RTP (Real-Time Transport Protocol) ou SRTP (Secure Real-Time Transport Protocol), les protocoles qui gèrent les données vocales réelles dans les appels VoIP (Voice over Internet Protocol).



</div>

</div>

<div>

## <a name="deployment-process"></a>Processus de déploiement

Pour implémenter le côté Lync Server de la connexion de jonction SIP, procédez comme suit :

1.  À l’aide du générateur de topologie Lync Server, créez et configurez la topologie de domaine SIP. Pour plus d’informations, reportez-vous à la rubrique [define and Configure a Topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) dans la documentation de déploiement.

2.  À l’aide du panneau de configuration Lync Server, configurez le routage des communications vocales pour le nouveau domaine SIP. Pour plus d’informations, reportez-vous à la rubrique [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md) dans la documentation de déploiement.

3.  Testez la connectivité à l’aide de la cmdlet **test-CsPstnOutboundCall** . Pour plus d’informations, reportez-vous à la documentation de Lync Server Management Shell ou à l’aide de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

