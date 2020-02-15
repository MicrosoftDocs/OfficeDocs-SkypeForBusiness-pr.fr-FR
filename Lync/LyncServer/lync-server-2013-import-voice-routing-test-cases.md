---
title: 'Lync Server 2013 : importation des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bb5d8e8f29edf0397c9bb9fa12592087ea517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importer des cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Les scénarios de test vous permettent de tester les itinéraires des communications vocales au sein de votre organisation : vous définissez des éléments tels que le numéro à composer, le plan de numérotation et la stratégie de voix à utiliser, et Lync Server 2013 peut ensuite vérifier que, étant donné ces conditions, le numéro fourni peut succes sfully être acheminé vers le réseau RTC.

Les cas de test, qui peuvent être créés à l’aide du panneau de configuration Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été initialement créé et exécuté. Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs. Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>Pour importer un cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Dans le menu **Actions**, cliquez sur **Importer des cas de test**.

5.  Recherchez le fichier de cas de test (.vtest) que vous voulez importer, puis cliquez sur **Ouvrir**.

6.  Cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous importez un fichier .vtest, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier le cas de test. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exporter des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

