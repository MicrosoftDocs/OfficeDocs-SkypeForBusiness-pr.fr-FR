---
title: 'Lync Server 2013 : Composants utilisés par l’application d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Composants utilisés par l’application d’annonce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-13_

Dans Lync Server 2013, l’application d’annonce est un composant de l’application Response Group. Lorsque vous déployez Enterprise Voice, l’application d’annonce est automatiquement installée et activée conjointement avec l’application Response Group. Cette section décrit les composants qui prennent en charge l’application d’annonce.

<div>

## <a name="announcement-application-components"></a>Composants de l’application annonce

Les composants Lync Server suivants prennent en charge l’application d’annonce:

  - ****   Le service d’application de service d’application fournit une plate-forme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. Le service d’application est automatiquement installé sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server.

  - **Application de Response Group**   l’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application. Lorsqu’une plage de numéros de téléphone non attribués est configurée pour diriger vers une annonce, l’application de groupe de réponse est requise pour acheminer les appels passés vers le numéro de téléphone. (L’application Response Group n’est pas nécessaire si toutes les plages sont configurées pour le routage à la messagerie unifiée Exchange (MU).)

  - **** Les fichiers audio sont utilisés pour les annonces.   

  - **Magasin de fichiers**   l’application d’annonce utilise le magasin de fichiers pour stocker ses fichiers audio.

  - **Panneau de configuration**   de Lync Server vous pouvez utiliser le panneau de configuration de Lync Server pour configurer la table des numéros non attribués.

  - **Lync Server Management Shell**   vous pouvez utiliser les applets de applet Lync Server Management Shell pour configurer les paramètres d’annonce et la table des numéros non attribués.

</div>

</div>

<span> </span>

</div>

</div>

</div>

