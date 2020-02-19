---
title: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b644b5b703e1515a4417b7fa318b4e9ed6080b94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-19_

Utilisez la cmdlet **Disable-CsAdForest** pour inverser la procédure de préparation d’une forêt.

<div>


> [!WARNING]  
> Si vous exécutez l’applet de commande <STRONG>Disable-CsAdForest</STRONG> dans un environnement où vous avez également une version antérieure de Lync Server déployée, les paramètres globaux de la version précédente seront également supprimés.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Pour utiliser des cmdlets afin d’inverser la préparation d’une forêt

1.  Ouvrez une session sur un ordinateur qui est associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Par exemple :
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Le paramètre Force spécifie s’il faut forcer l’exécution de la tâche. Si ce paramètre n’est pas présent, la commande ne s’exécutera pas si un seul domaine de la forêt est toujours préparé pour Lync Server 2013. Si le paramètre Force est spécifié, l’action se poursuit quel que soit l’état des autres domaines dans la forêt.
    
    Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exécution de la préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

