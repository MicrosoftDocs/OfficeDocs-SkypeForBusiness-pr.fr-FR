---
title: 'Lync Server 2013 : résolution des problèmes du plug-in Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc58629ea7c641427347600be48538cd555022c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Résolution des problèmes liés au plug-in Lync VDI dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Résolution des problèmes liés à l’installation du plug-in Lync VDI sur un client léger

Si vous rencontrez des problèmes lors de l’installation du plug-in VDI sur un client léger, vérifiez les points suivants :

  - Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.

  - Assurez-vous que la protection en écriture est désactivée. Reportez-vous à la documentation du fabricant de votre périphérique pour en savoir plus.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Résolution des problèmes liés au jumelage

Lorsque le jumelage du plug-in VDI échoue, l’icône du jumelage qui se trouve dans l’angle inférieur droit prend la forme d’un « X » rouge, comme ceci :

![Icône Lync VDI montrant le jumelage réussi](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône Lync VDI montrant le jumelage réussi")

Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier.

  - **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    L’utilisateur doit se déconnecter de Lync et se reconnecter avec les informations d’identification appropriées. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.

  - **Une autre instance du client Bureau à distance est en cours d’exécution.**
    
    S’ils utilisent la connexion Bureau à distance dans Windows, les utilisateurs doivent procéder comme suit :
    
    1.  Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr**, puis cliquez sur **Démarrer le Gestionnaire des tâches**.
    
    2.  Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.
    
    3.  Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**.
    
    4.  Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter.

  - **Les fichiers nécessaires n’ont pas été installés correctement.**
    
    Une fois le plug-in installé sur l’ordinateur local, les fichiers suivants doivent être présents sous C :\\Program Files\\Microsoft Office\\Office15 (ou la lettre de lecteur appropriée) :
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    Si des problèmes liés au jumelage VDI se sont produits, vérifiez que ces fichiers sont présents sur l’ordinateur local.

  - **Le client Lync est en cours d’exécution sur l’ordinateur local.**
    
    Pour utiliser le plug-in Lync VDI, un client Lync ne doit pas être en cours d’exécution sur l’ordinateur local, sinon le jumelage échoue. La meilleure pratique consiste à ne pas installer un client Lync sur l’ordinateur local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

