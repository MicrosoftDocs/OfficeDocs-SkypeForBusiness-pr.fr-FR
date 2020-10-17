---
title: Exportation de votre topologie et copie vers le support externe pour l’installation Edge
description: Exportez votre topologie et copiez-la sur un support externe pour l’installation Edge.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564760"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exportation de votre topologie Lync Server 2013 et copie vers le support externe pour l’installation Edge

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Une fois que vous avez publié votre topologie, l’Assistant Déploiement de Lync Server a besoin d’accéder aux données du magasin central de gestion afin de démarrer le processus de déploiement sur le serveur. Dans le réseau interne, les données sont disponibles directement depuis les serveurs, mais les serveurs Edge ne figurant pas dans le domaine interne ne peuvent pas accéder à ces informations. Pour que les données de configuration de topologie soient disponibles pour un déploiement de serveur Edge, vous devez exporter les données de topologie vers un fichier et les copier sur un support externe (par exemple, un lecteur USB ou un partage réseau disponible à partir du serveur Edge) avant d’exécuter l’Assistant Déploiement de Lync Server sur le serveur Edge. Utilisez la procédure suivante pour rendre vos données de configuration de topologie accessibles au serveur Edge que vous déployez.

<div>


> [!NOTE]
> Une fois que vous avez installé Lync Server 2013 sur un serveur Edge, vous devez gérer le serveur Edge à l’aide des outils d’administration du réseau interne, qui répliquent automatiquement les serveurs de périphérie de votre déploiement. Les seules exceptions concernent l’attribution et l’installation de certificats, ainsi que l’arrêt et le démarrage des services, qui doivent tous deux être effectués sur le serveur Edge.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Pour rendre vos données de topologie accessibles sur un serveur Edge à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Dans Lync Server Management Shell, exécutez l’applet de commande suivante :
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copiez le fichier exporté sur un support externe (par exemple, une clé USB ou un partage réseau disponible depuis le serveur Edge lors du déploiement).

</div>

</div>

<span> </span>

</div>

</div>

</div>

