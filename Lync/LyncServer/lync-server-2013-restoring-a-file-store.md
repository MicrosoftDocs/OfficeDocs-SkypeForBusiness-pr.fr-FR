---
title: 'Lync Server 2013 : restauration d’un magasin de fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restauration d’un magasin de fichiers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Les magasins de fichiers pour l’édition standard sont généralement situés sur le serveur Standard Edition Server. Les magasins de fichiers pour Enterprise Edition sont généralement situés sur un serveur de fichiers ou un cluster. La procédure suivante vous explique comment restaurer un magasin de fichiers.

<div>

## <a name="to-restore-a-file-store"></a>Pour restaurer un magasin de fichiers

1.  En cas d’échec d’un magasin de fichiers, copiez le\\ magasin de fichiers approprié à partir de $Backup à l’emplacement de stockage des fichiers sur le serveur de fichiers ou Standard Edition Server, puis partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être exactement les mêmes que ceux du magasin de fichiers sauvegardés, afin que les composants qui utilisent les fichiers puissent y accéder.

    
    </div>

2.  Le cas échéant, définissez les listes de contrôle d’accès (ACL) pour le magasin de fichiers. À partir de la ligne de commande, tapez :
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Vous ne devez effectuer cette étape que si vous n’avez pas exécuté de générateur de topologie lors du processus de restauration.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

