---
title: 'Lync Server 2013 : exporter des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d871379f9c9be161aec879b7ca8da16ac40e2b5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exporter des cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les scénarios de test vous permettent de tester les itinéraires des communications vocales dans votre organisation : vous définissez des éléments tels que le numéro à composer et le plan de numérotation et la stratégie de voix à utiliser, et Lync Server peut ensuite vérifier que, étant donné ces conditions, le numéro fourni peut correctement acheminés vers le réseau RTC.

Les cas de test, qui peuvent être créés à l’aide du panneau de configuration Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été initialement créé et exécuté. Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs. Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Pour exporter un cas de test de routage des communications vocales

1.  Dans le panneau de configuration Lync Server, cliquez sur **routage** des communications vocales, puis sur **tester le routage des communications vocales**.

2.  Sous l’onglet **Tester le routage des communications vocales**, sélectionnez le cas de test (ou les cas de test) à exporter. Pour sélectionner plusieurs cas de test, cliquez sur le premier cas à exporter, puis maintenez la touche Ctrl enfoncée et sélectionnez les cas supplémentaires à exporter.

3.  Cliquez sur **Action**, puis sur **Exporter des cas de test**.

4.  Dans la boîte de dialogue **Enregistrer sous** , sélectionnez un dossier pour stocker les cas de test exportés et tapez un nom pour le fichier XML résultant dans la zone **nom de fichier** . Notez que si vous exportez plusieurs cas de test, tous ces cas de test seront enregistrés dans un seul fichier XML.

5.  Pour enregistrer les cas de test, cliquez sur **Enregistrer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Importer des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

