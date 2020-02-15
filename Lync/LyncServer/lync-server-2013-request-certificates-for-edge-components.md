---
title: 'Lync Server 2013 : demande de certificats pour les composants Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10e7a724edd6e68602e4655a783f953ad1e2bc2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Demander des certificats pour les composants Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Les certificats nécessaires à la prise en charge de l’accès des utilisateurs externes incluent les certificats émis par une autorité de certification publique et les certificats émis par une autorité de certification d’entreprise interne :

  - Les certificats requis pour l’interface externe du serveur Edge et le proxy inverse doivent être émis par une autorité de certification publique.

  - Les certificats requis pour l’interface interne peuvent être émis par une autorité de certification publique ou une autorité de certification d’entreprise interne. Nous vous recommandons d’utiliser une autorité de certification Windows Server 2008 interne, Windows Server 2008 R2 CA, Windows Server 2012 CA ou Windows Server 2012 R2 pour créer ces certificats afin d’économiser sur les frais d’utilisation des certificats publics.

<div>


> [!IMPORTANT]  
> Le traitement des demandes de certificat, en particulier les demandes adressées aux autorités de certification publiques, peut prendre du temps, donc vous devez demander des certificats pour vos serveurs Edge suffisamment tôt pour vous assurer qu’ils sont disponibles lorsque vous démarrez le déploiement de vos composants de serveur Edge. Pour obtenir un résumé des exigences en matière de certificats pour les serveurs Edge, reportez-vous à <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for External User Access in Lync Server 2013</A>.



</div>

Même si vous pouvez choisir d’utiliser une autorité de certification publique pour le certificat Edge interne, nous vous conseillons plutôt d’utiliser une autorité de certification d’entreprise interne pour les autres certificats pour en réduire le coût. Pour obtenir un résumé des exigences en matière de certificats pour les serveurs Edge, reportez-vous à [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Lorsque vous installez un serveur Edge, le programme d’installation inclut un Assistant certificat qui facilite les tâches de demande, d’affectation et d’installation des certificats, comme décrit dans la section <A href="lync-server-2013-set-up-edge-certificates.md">set up Edge Certificates for Lync Server 2013</A> . Si vous souhaitez demander des certificats avant d’installer un serveur Edge (par exemple, pour gagner du temps pendant le déploiement réel des composants de serveur Edge), vous pouvez le faire à l’aide de serveurs internes tant que vous vous assurez que les certificats sont exportables et qu’ils contiennent tous les autres noms de sujet requis. Cette documentation ne fournit pas de procédures relatives à l’utilisation de serveurs internes pour la demande de certificats.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Demander des certificats à une autorité de certification publique

Le déploiement de votre serveur Edge nécessite un certificat public unique pour les interfaces externes des serveurs Edge, utilisé pour le service Edge d’accès, le service Edge de conférence Web et le service d’authentification A/V. Ce certificat doit disposer d’une clé privée exportable pour s’assurer que le service d’authentification A/V utilise les mêmes clés sur tous les serveurs Edge d’un pool. Le proxy inverse, qui est utilisé avec Microsoft Internet Security and Acceleration (ISA) Server 2006 ou Microsoft Forefront Threat Management Gateway 2010, nécessite également un certificat public.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Demander des certificats à partir d’une autorité de certification d’entreprise interne

Les certificats nécessaires à l’interface interne du serveur Edge peuvent être émis par une autorité de certification publique ou interne. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat. Si votre organisation en a déployé une, les certificats des serveurs Edge internes doivent être émis par cette autorité de certification. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat.

Pour obtenir un résumé des exigences en matière de certificats pour les composants Edge, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Pour plus d’informations sur l’utilisation d’une autorité de certification publique pour obtenir des certificats, voir [demander des certificats pour les composants Edge dans Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Pour plus d’informations sur la demande, l’installation et l’affectation de certificats, voir [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

