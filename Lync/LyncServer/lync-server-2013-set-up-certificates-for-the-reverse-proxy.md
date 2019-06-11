---
title: 'Lync Server 2013 : Configuration des certificats pour le serveur proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configuration des certificats pour le serveur proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Chaque serveur proxy inverse nécessite un certificat de serveur Web pour une utilisation par le service d’écoute. Le certificat de serveur Web doit être émis par une autorité de certification (CA) publique.

Pour plus d’informations sur ce problème et sur les autres exigences relatives aux certificats, voir [exigences relatives aux certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Pour configurer un certificat de services Web pour le proxy inverse

  - Vous avez déjà configuré votre proxy inverse, y compris la configuration du certificat de services Web. Si vous ne l’avez pas fait avant de commencer le déploiement de vos serveurs de périphérie, utilisez les procédures de [Configuration des serveurs proxy inverse pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) pour créer une demande et installer le certificat de services Web, puis créez chaque règle de publication Web et Configurez-le pour utiliser le certificat.

</div>

</div>

<span> </span>

</div>

</div>

</div>

