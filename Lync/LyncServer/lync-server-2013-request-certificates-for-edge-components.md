---
title: 'Lync Server 2013 : Demande des certificats pour les composants Edge'
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
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Demande des certificats pour les composants Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Les certificats nécessaires à la prise en charge de l’accès des utilisateurs externes incluent des certificats émis par une autorité de certification publique et des certificats émis par une autorité de certification d’entreprise interne :

  - Les certificats requis pour l’interface externe du serveur Edge et le proxy inverse doivent être émis par une autorité de certification publique.

  - Les certificats requis pour l’interface interne peuvent être émis par une autorité de certification publique ou une autorité de certification d’entreprise interne. Nous recommandons l’utilisation d’une autorité de certification Windows Server 2008, de Windows Server 2008 R2, d’une autorité de certification Windows Server 2012 ou d’une autorité de certification Windows Server 2012 R2 pour la création de ces certificats pour faire des économies sur les coûts d’utilisation des certificats publics.

<div>


> [!IMPORTANT]  
> Il est temps de traiter les demandes de certificat, en particulier celles des autorités de certification publiques, afin de vous assurer qu’elles soient disponibles lorsque vous commencez le déploiement de vos composants serveur Edge. Pour obtenir une synthèse des exigences de certificats pour les serveurs Edge, voir exigences relatives aux <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">certificats pour l’accès des utilisateurs externes dans Lync Server 2013</A>.



</div>

Même si vous pouvez opter pour l’utilisation d’une autorité de certification publique pour le certificat Edge interne, nous vous conseillons d’utiliser une autorité de certification d’entreprise interne pour ces certificats au lieu de réduire le coût des certificats. Pour obtenir une synthèse des exigences de certificats pour les serveurs Edge, voir exigences relatives aux [certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Lors de l’installation d’un serveur Edge, le programme d’installation inclut un assistant de certification qui simplifie les tâches de demande, d’attribution et d’installation des certificats, comme décrit dans la section <A href="lync-server-2013-set-up-edge-certificates.md">configurer les certificats d’activation pour Lync Server 2013</A> . Si vous souhaitez demander des certificats avant d’installer un serveur Edge (par exemple, pour gagner du temps au cours du déploiement réel des composants du serveur Edge), vous pouvez le faire à l’aide de serveurs internes tant que vous vous assurez que les certificats sont exportés et contiennent tous les autres noms d’objet obligatoires. Cette documentation ne fournit pas de procédures permettant d’utiliser les serveurs internes pour demander des certificats.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Demander des certificats auprès d’une autorité de certification publique

Le déploiement de votre serveur Edge nécessite un certificat public unique pour les interfaces externes des serveurs Edge, qui est utilisé pour le service Edge d’accès, le service Edge de conférence Web et pour le service d’authentification A/V. Ce certificat doit avoir une clé privée exportable pour s’assurer que le service d’authentification A/V utilise les mêmes clés sur tous les serveurs Edge d’un pool. Le proxy inverse, qui est utilisé avec Microsoft Internet Security and Acceleration (ISA) Server 2006 ou Microsoft Forefront Threat Management Gateway 2010, nécessite également un certificat public.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Demander des certificats auprès d’une autorité de certification d’entreprise interne

Les certificats requis pour l’interface de bord interne peuvent être émis par une autorité de certification (CA) publique ou une autorité de certification interne. Vous pouvez utiliser une autorité de certification d’entreprise interne pour réduire le coût des certificats. Si votre organisation a déployé une autorité de certification interne, les certificats pour le bord interne doivent être émis par l’autorité de certification interne. L’utilisation d’une autorité de certification d’entreprise interne pour les certificats internes peut réduire le coût des certificats.

Pour obtenir une synthèse des exigences en matière de certificats pour les composants Edge, voir exigences relatives aux [certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Pour plus d’informations sur l’utilisation d’une autorité de certification publique pour obtenir des certificats, voir [demander des certificats pour les composants Edge dans Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Pour plus d’informations sur la demande, l’installation et l’attribution de certificats, voir [configurer des certificats Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

