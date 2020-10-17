---
title: 'Lync Server 2013 : serveurs Edge audio/vidéo (A/V)'
description: 'Lync Server 2013 : serveurs Edge audio/vidéo (A/V).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5aefd4516540485b84ba0eb80f1a809d89eba0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568790"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). Outre les données audio et vidéo, le service Edge A/V fournit également une prise en charge du partage du Bureau et du transfert de fichiers.

La gestion du service Edge A/V s’effectue à l’aide de la configuration de ce service. Ces paramètres vous permettent de gérer la quantité maximale de bande passante à allouer par port et par utilisateur, ainsi que de spécifier la durée pendant laquelle un jeton d’authentification peut être utilisé avant de devoir être renouvelé. Les paramètres de configuration Edge A/V peuvent être appliqués à des sites ou à des serveurs Edge A/V individuels. Lors de la détermination de la collection de paramètres qui sera prioritaire, utilisez le guide suivant :

  - Les paramètres configurés au niveau du service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.

  - Les paramètres configurés au niveau du site prévalent sur les paramètres configurés au niveau global. Les paramètres au niveau du service, quant à eux, prévalent sur les paramètres au niveau du site.

  - Les paramètres au niveau global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.

Le service Edge A/V peut uniquement être géré à l’aide de Lync Server PowerShell et des applets de commande CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

