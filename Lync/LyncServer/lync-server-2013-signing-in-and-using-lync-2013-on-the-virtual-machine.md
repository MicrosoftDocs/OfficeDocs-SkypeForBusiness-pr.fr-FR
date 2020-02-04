---
title: Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel
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
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Une fois que le plug-in VDI est activé, les étapes suivantes se produisent lorsque l’utilisateur se connecte à Lync 2013.

1.  L’utilisateur tape ses informations d’identification dans le client 2013 Lync exécuté sur l’ordinateur virtuel.

2.  Après que Lync a détecté la disponibilité du plug-in VDI, Lync invite l’utilisateur à entrer à nouveau ses informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.

3.  Lync entame le jumelage avec le plug-in VDI. Avant de procéder à un jumelage, le client affiche deux icônes dans la barre d’État Lync. L’icône située dans le coin inférieur gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotant dans le coin inférieur droit indique que le jumelage VDI est en cours, comme illustré ci-dessous :
    
    ![Icône VDI de Lync montrant une jumelage réussie](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône VDI de Lync montrant une jumelage réussie")  

4.  Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :
    
    ![Icône d’appariement VDI de Lync indiquant le succès](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icône d’appariement VDI de Lync indiquant le succès")  

5.  Après paires Lync avec le plug-in VDI, l’utilisateur peut voir son statut de connexion sur les appareils compatibles Lync qui sont connectés à l’ordinateur local. L’utilisateur peut désormais passer et répondre aux appels comme d’habitude.

</div>

<span> </span>

</div>

</div>

</div>

