---
title: 'Serveurs Edge Lync Server 2013: audio/vidéo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation). Outre l’audio et la vidéo, le service Edge A/V assure également la prise en charge du partage de bureau et du transfert de fichiers.

Le service Edge A/V est essentiellement géré à l’aide de la configuration A/V Edge. ces paramètres vous permettent de gérer le volume maximal de bande passante à allouer par port et par utilisateur, et de spécifier la durée pendant laquelle il est possible d’utiliser un jeton d’authentification avant le renouvellement du jeton. Les paramètres de configuration de Microsoft Edge peuvent être appliqués à des sites ou à des serveurs Edge A/V individuels. Lorsque vous déterminez la collection de paramètres qui sera prioritaire, utilisez le guide suivant:

  - Les paramètres configurés au niveau de l’étendue de service (autrement dit, sur un serveur individuel) sont prioritaires sur tout.

  - Les paramètres configurés lors de l’étendue du site sont prioritaires sur les paramètres configurés au niveau de l’étendue globale. Toutefois, les paramètres d’étendue de service remplacent également les paramètres d’étendue de site.

  - Les paramètres au niveau de l’étendue globale seront utilisés uniquement s’il n’y a aucun paramètre de service configuré sur le serveur individuel et s’il n’y a aucun paramètre de site pour le site sur lequel se trouve le serveur.

Le service Edge A/V peut être géré uniquement à l’aide de Lync Server PowerShell et des cmdlets CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

