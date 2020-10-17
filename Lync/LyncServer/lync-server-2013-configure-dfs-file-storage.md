---
title: 'Lync Server 2013 : configurer le stockage de fichiers DFS'
description: 'Lync Server 2013 : configurez le stockage de fichiers DFS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564380"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurer le stockage de fichiers DFS pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-05-23_

Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur un système de fichiers DFS. Pour plus d’informations sur DFS pour Windows Server 2008, voir le guide pas à pas de DFS pour Windows Server 2008 à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Pour utiliser un DFS, Lync Server 2013 requiert les éléments suivants :

  - Les espaces de noms sont basés sur un domaine

  - Tous les serveurs d’espaces de noms exécutent un minimum de Windows 2008

Le programme d’installation de Lync Server 2013 nécessite que les autorisations sur le dossier partagé autorisent l’accès total à l’administrateur. Lync Server 2013 utilise alors les autorisations de fichiers NTFS pour afficher la liste de contrôle d’accès des dossiers. Les autorisations héritées du partage DFS ne seront pas utilisées pour limiter l’accès.

Pour plus d’informations sur les exigences en matière de partage de fichiers, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation de prise en charge.

<div>


> [!NOTE]  
> Vous pouvez consulter des informations sur la configuration d’un partage non DFS. Si c’est le cas, consultez la <A href="lync-server-2013-hardware-setup.md">Configuration matérielle de Lync Server 2013</A>.



</div>

La procédure suivante décrit comment configurer correctement les autorisations des dossiers partagés à l’aide de l’Assistant espace de noms DFS (comme décrit dans le Guide de configuration DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Pour configurer les autorisations des dossiers partagés

1.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **gestion du système de fichiers distribués DFS**.

2.  Dans l’arborescence de la console du composant logiciel enfichable de gestion du système de fichiers distribués DFS, cliquez avec le bouton droit sur le serveur d’espace de noms (par exemple, filesrv1.contoso.com), puis cliquez sur **modifier les paramètres**.

3.  Sélectionnez **autorisations sur les dossiers partagés**.

4.  Sélectionnez **utiliser des autorisations personnalisées**.

5.  Pour le groupe administrateurs, sélectionnez les éléments suivants sous **autoriser**:
    
      - **Contrôle total**
    
      - **Change**
    
      - **Read**

6.  Cliquez sur **Appliquer**, puis sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

