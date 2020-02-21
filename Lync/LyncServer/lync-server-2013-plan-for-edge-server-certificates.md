---
title: 'Lync Server 2013 : planification des certificats de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ac330914a0d748c366d2a6e40ac0ad9f03543d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planification des certificats de serveur Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-05_

La création de certificats pour Edge est simplifiée dans Lync Server 2013.

**Organigramme des certificats pour le serveur Edge**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Créez un seul certificat public, vérifiez que vous disposez d’une clé privée exportable définie pour le certificat, et affectez-la aux interfaces externes du serveur Edge suivantes à l’aide de l’Assistant Certificat :

<div>


> [!IMPORTANT]  
> Les certificats génériques ne sont pas pris en charge dans Lync Server, sauf s’ils sont utilisés pour résumer les URL simples via le proxy inverse. Vous devez définir des noms d’autres objets distincts (San) pour chaque nom de domaine SIP, service Edge de conférence Web, service Edge A/V et domaine XMPP offert par votre déploiement.



</div>

<div>


> [!NOTE]  
> Introduit dans Lync Server 2013, la mise en place de certificats d’authentification audio/vidéo avant le délai d’expiration du certificat actuel nécessite une planification supplémentaire. Au lieu d’un certificat à plusieurs fins pour l’interface Edge externe, vous aurez besoin de deux certificats, un affecté au service Edge d’accès et au service Edge de conférence Web, et un certificat pour le service Edge A/V. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth Certificates in Lync Server 2013 using-rouleaux in set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> Dans le cas d’un pool de serveurs Edge, vous exportez le certificat avec la clé privée vers chaque serveur Edge et vous affectez le certificat à chaque service serveur Edge. Procédez de la même manière pour le certificat de serveur Edge interne, en exportant le certificat avec la clé privée et en l’affectant à chaque interface Edge interne.



</div>

  - Assurez-vous qu’une clé privée exportable est attribuée au certificat.

  - Service Edge d’accès (appelé serveur **Edge d’accès SIP externe** dans l’Assistant certificat)

  - Service Edge de conférence Web (appelé serveur **Edge de conférence Web externe** dans l’Assistant certificat)

  - Service d’authentification a/V (appelé serveur **Edge a/v externe** dans l’Assistant certificat)

Créez un certificat interne unique avec une clé privée exportable, copiez-le et affectez-le à chacune des interfaces internes du serveur Edge :

  - Serveur Edge (appelé serveur Edge **interne** dans l’Assistant certificat)

<div>


> [!IMPORTANT]  
> Il est possible d’utiliser des certificats distincts et distincts pour chaque service serveur Edge. Si vous souhaitez utiliser la nouvelle fonctionnalité de certificat de déploiement pour le certificat de service Edge A/V, il est recommandé de choisir des certificats distincts. Dans le cas de cette fonctionnalité, nous vous recommandons de découpler le certificat de service Edge A/V du service Edge d’accès et du service Edge de conférence Web. Si vous choisissez de demander, d’acquérir et d’affecter des certificats distincts pour chaque service, vous devez demander à ce que la clé privée soit exportable pour le service Edge A/V (là encore, il s’agit du service d’authentification A/V) et affectez le même certificat à l’interface externe Edge A/V sur chaque serveur Edge.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Staging des certificats AV et OAuth dans Lync Server 2013 avec l’utilisation de la CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

