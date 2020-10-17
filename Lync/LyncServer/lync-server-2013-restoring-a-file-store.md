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
ms.openlocfilehash: cd1984c6e51866b1ace707f305fb2a6cc356a132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511611"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restauration d’un magasin de fichiers dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Les magasins de fichiers pour Standard Edition se trouvent généralement sur le serveur Standard Edition. Les magasins de fichiers pour Enterprise Edition sont généralement stockés sur un serveur de fichiers ou un cluster. La procédure suivante décrit comment restaurer un magasin de fichiers.

<div>

## <a name="to-restore-a-file-store"></a>Pour restaurer un magasin de fichiers

1.  Si un magasin de fichiers échoue, copiez le magasin de fichiers approprié à partir de $Backup \\ vers l’emplacement du magasin de fichiers sur le serveur de fichiers ou le serveur Standard Edition, puis partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé, afin que les composants qui utilisent les fichiers puissent y accéder.

    
    </div>

2.  Si nécessaire, définissez les listes de contrôle d’accès (ACL) pour le magasin de fichiers. Sur la ligne de commande, tapez :
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Vous devez effectuer cette étape uniquement si vous n’avez pas exécuté le générateur de topologie lors de votre processus de restauration.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

