---
title: 'Lync Server 2013 : Exportation des cas de test de routage des communications vocales'
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
ms.openlocfilehash: 781c9e312044193cb6195ee849a880bea6e08485
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportation des cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les scénarios de test vous permettent de tester les itinéraires vocaux au sein de votre organisation : vous définissez des éléments tels que le numéro à composer, le plan de numérotation et la politique vocale à utiliser, et Lync Server peut alors vérifier qu’il est possible d’utiliser le numéro fourni. correctement routés vers le réseau PSTN.

Les cas de test, qui peuvent être créés à l’aide du panneau de configuration de Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été créé et exécuté à l’origine. Toutefois, ces cas de test peuvent être exportés sous forme de fichiers XML (avec l’extension. vtest), puis importés sur d’autres serveurs. Cela vous permet d’exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Pour exporter un cas de test de routage vocal

1.  Dans le panneau de configuration de Lync Server, cliquez sur **routage des communications vocales** , puis cliquez sur **tester le routage vocal**.

2.  Dans l’onglet **tester le routage vocal** , sélectionnez le cas de test (ou les cas de test) à exporter. Pour sélectionner plusieurs cas de test, cliquez sur la première case à exporter, puis maintenez la touche CTRL enfoncée et sélectionnez les cas supplémentaires à exporter.

3.  Cliquez sur **action**, puis sur **Exporter les cas de test**.

4.  Dans la boîte de dialogue **Enregistrer sous** , sélectionnez un dossier pour stocker les cas de test exportés et tapez un nom pour le fichier XML obtenu dans la zone **nom de fichier** . Notez que si vous exportez plusieurs cas de tests, tous ces cas de test seront enregistrés dans un fichier XML unique.

5.  Pour enregistrer les cas de test, cliquez sur **Enregistrer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Importation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

