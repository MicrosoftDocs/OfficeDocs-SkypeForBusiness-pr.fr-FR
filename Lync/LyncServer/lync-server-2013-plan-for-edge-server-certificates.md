---
title: 'Lync Server 2013 : Planification des certificats de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737e0845b4b9966accd8c450b8a300b4f1bb128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planification des certificats de serveur Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-05_

La création de certificats pour Edge est simplifiée dans Lync Server 2013.

**Diagramme de certificats pour le serveur Edge**

![a5fc20db-7ced-4364-b577-6a709a8367cd] (images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Créez un certificat public unique, assurez-vous d’avoir une clé privée exportable définie pour le certificat et attribuez-la aux interfaces externes du serveur Edge suivantes à l’aide de l’Assistant Certificat:

<div>


> [!IMPORTANT]  
> Les certificats génériques ne sont pas pris en charge dans Lync Server, sauf s’ils sont utilisés pour résumer les URL simples par le biais du proxy inverse. Vous devez définir des noms secondaires d’objet distincts (San) pour chaque nom de domaine SIP, service Edge de conférence Web, service Edge A/V et domaine XMPP offert par votre déploiement.



</div>

<div>


> [!NOTE]  
> Introduite dans Lync Server 2013, les certificats d’authentification audio et vidéo intermédiaires qui avancent l’expiration du certificat actuel nécessitent une planification supplémentaire. Au lieu d’utiliser un certificat à des fins différentes pour l’interface de bord externe, vous devez disposer de deux certificats, l’un attribué au service Edge d’accès et au service Edge de conférence Web, et un certificat pour le service Edge A/V. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Configuration des certificats d’audiovisuel et des certificats OAuth dans Lync Server 2013 avec l’application Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> Dans le cas d’un pool de serveurs Edge, vous exportez le certificat avec la clé privée vers chaque serveur Edge et vous attribuez le certificat à chaque service Edge Server. Procédez de la même façon pour le certificat de serveur Edge interne, en exportant le certificat avec la clé privée et en l’affectant à chaque interface de bord interne.



</div>

  - Vérifiez que vous avez affecté une clé privée exportée au certificat.

  - Service Edge d’accès (appelé **Edge d’accès SIP externe** dans l’Assistant certificat)

  - Service Edge de conférence Web (connu sous le nom de **conférence Web externe** dans l’Assistant certificat)

  - Service d’authentification a/V (appelé par le biais de l' **extérieur** de l’Assistant certificat)

Créez un certificat interne unique avec une clé privée exportable, puis copiez-le et attribuez-le à chaque interface interne du serveur Edge:

  - Serveur Edge (appelé **Edge Internal** dans l’Assistant certificat)

<div>


> [!IMPORTANT]  
> Il est possible d’utiliser des certificats distincts et distincts pour chaque service Edge Server. Il peut s’avérer utile de choisir des certificats séparés si vous souhaitez utiliser la nouvelle fonctionnalité de certificat de déploiement pour le certificat de service Edge A/V. Dans le cas de cette fonctionnalité, il est recommandé de découpler le certificat de service Edge A/V du service Edge d’accès et du service Edge de conférence Web. Si vous choisissez de demander, d’acquérir et d’affecter des certificats séparés pour chaque service, vous devez demander à la clé privée d’être exportable pour le service Edge A/v (de nouveau, il s’agit du service d’authentification a/v) et de lui attribuer le même certificat Interface externe latérale sur chaque serveur Edge.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test de l’audiovisuel et des certificats OAuth dans Lync Server 2013 à l’aide du CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

