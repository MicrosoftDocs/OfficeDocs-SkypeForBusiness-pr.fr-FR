---
title: 'Lync Server 2013 : connexion et utilisation de Lync 2013 sur l’ordinateur virtuel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e638fd734f00633b22664b4d4862733eb6d078da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Connexion et utilisation de Lync 2013 sur l’ordinateur virtuel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Une fois le plug-in VDI activé, les étapes suivantes se produisent lorsque l’utilisateur se connecte à Lync 2013.

1.  L’utilisateur tape ses informations d’identification dans le client Lync 2013 qui s’exécute sur l’ordinateur virtuel.

2.  Une fois que Lync a détecté la disponibilité du plug-in VDI, Lync invite l’utilisateur à entrer de nouveau ses informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.

3.  Lync commence le jumelage avec le plug-in VDI. Avant que le jumelage n’ait été effectué, le client affiche deux icônes dans la barre d’État Lync. L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible, tandis que l’icône qui clignote en bas à droite indique que le jumelage VDI est en cours, comme indiqué :
    
    ![Icône Lync VDI montrant le jumelage réussi](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône Lync VDI montrant le jumelage réussi")  

4.  Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :
    
    ![Icône d’appariement VDI Lync indiquant la réussite](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icône d’appariement VDI Lync indiquant la réussite")  

5.  Une fois que Lync est pair avec le plug-in VDI, l’utilisateur peut voir sa présence sur les appareils compatibles avec Lync qui sont connectés à l’ordinateur local. L’utilisateur peut alors passer et recevoir des appels comme d’habitude.

</div>

<span> </span>

</div>

</div>

</div>

