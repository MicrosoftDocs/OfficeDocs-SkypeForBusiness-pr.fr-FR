---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e33642fe4556397f4c3f71d5dfb582e1868a7ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir la fonctionnalité de communications unifiées Lync Server. Après avoir migré un déploiement Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets contact associés au téléphone de partie commune hérité. À l’aide de Lync Server Management Shell, vous devez tout d’abord récupérer tous les objets contact associés aux téléphones de zone commune Lync Server 2010, puis déplacer ces objets vers le pool Lync Server 2013.

**Migration des téléphones de partie commune**

1.  À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Pour vérifier que tous les objets contact ont été déplacés vers le pool Lync Server 2013, dans Lync Server Management Shell, tapez ce qui suit :
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Vérifiez que tous les objets contact sont maintenant associés au pool Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

