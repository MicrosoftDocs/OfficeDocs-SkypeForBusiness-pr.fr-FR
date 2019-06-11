---
title: 'Lync Server 2013 : Configuration du stockage des fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configuration du stockage des fichiers pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-05-23_

Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur un système de fichiers DFS. Pour plus d’informations sur le système de fichiers DFS pour Windows Server 2008, voir le guide détaillé pour Windows Server 2008 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)à l’adresse. Pour utiliser un système de fichiers DFS, Lync Server 2013 nécessite les éléments suivants:

  - Les espaces de noms sont basés sur le domaine

  - Tous les serveurs d’espaces de noms exécutent au moins une 2008 Windows

Le programme d’installation de Lync Server 2013 exige que les autorisations sur le dossier partagé autorisent l’accès total à l’administrateur. Lync Server 2013 utilisera alors les autorisations de fichier NTFS pour afficher une liste de contrôle d’accès aux dossiers. Les autorisations héritées du partage DFS ne seront pas utilisées pour limiter l’accès.

Pour plus d’informations sur la configuration requise du partage de fichiers, voir [prise en charge du stockage de fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation relative à la prise en charge.

<div>


> [!NOTE]  
> Vous recherchez des informations sur la configuration d’un partage non-DFS. Si tel est le cas, consultez <A href="lync-server-2013-hardware-setup.md">Configuration matérielle pour Lync Server 2013</A>.



</div>

La procédure suivante décrit comment configurer correctement les autorisations de dossier partagé à l’aide de l’Assistant espace de noms DFS (comme décrit dans le Guide de configuration de DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Pour configurer les autorisations sur les dossiers partagés

1.  Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **gestion DFS**.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le serveur d’espaces de noms (par exemple, filesrv1.contoso.com), puis cliquez sur **modifier les paramètres**.

3.  Sélectionnez **autorisations sur le dossier partagé**.

4.  Sélectionnez **utiliser des autorisations personnalisées**.

5.  Pour le groupe administrateur, sélectionnez les options suivantes sous **autoriser**:
    
      - **Contrôle total**
    
      - **Modification**
    
      - **Suit**

6.  Cliquez sur **appliquer**, puis sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

