---
title: 'Lync Server 2013 : composants utilisés par l’application d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517711"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Composants utilisés par l’application d’annonce dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-13_

Dans Lync Server 2013, l’application d’annonce est un composant de l’application Response Group. Lorsque vous déployez voix entreprise, l’application d’annonce est automatiquement installée et activée avec l’application Response Group. Cette section décrit les composants qui prennent en charge l’application d’annonce.

<div>

## <a name="announcement-application-components"></a>Composants de l’application d’annonce

Les composants de Lync Server suivants prennent en charge l’application d’annonce :

  - **Service**     d’application Application service fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.

  - **Application**     Response Group L’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application. Lorsqu’une plage de numéros de téléphone non attribués est configurée pour acheminer vers une annonce, l’application Response Group est requise pour acheminer les appels passés au numéro de téléphone. (L’application Response Group n’est pas nécessaire si toutes les plages sont configurées pour acheminer la messagerie unifiée Exchange.)

  - **Fichiers audio**     Les fichiers audio sont utilisés pour les annonces.

  - **Magasin**     de fichiers L’application d’annonce utilise le magasin de fichiers pour stocker ses fichiers audio.

  - **Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table des numéros non attribués.

  - **Lync Server Management Shell**     Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer les paramètres d’annonce et la table des numéros non attribués.

</div>

</div>

<span> </span>

</div>

</div>

</div>

