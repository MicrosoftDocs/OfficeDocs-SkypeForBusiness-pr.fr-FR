---
title: 'Lync Server 2013 : lecture de journaux de capture à partir du service de journalisation centralisée'
description: 'Lync Server 2013 : lecture des journaux de capture à partir du service de journalisation centralisée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559160"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lecture des journaux de capture à partir du service de journalisation centralisée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-28_

Vous profitez de l’avantage réel du service de journalisation centralisée après avoir exécuté la recherche et vous disposez d’un fichier que vous pouvez utiliser pour repérer un problème signalé. Vous pouvez lire le fichier de plusieurs façons. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad.exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil comme Snooper.exe conçu pour lire et analyser la sortie de journalisation à partir du service de journalisation centralisée. Snooper est inclus avec les outils de débogage Lync Server 2013, qui peuvent être téléchargés séparément. Vous pouvez télécharger les outils de débogage Lync Server 2013 ici : [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) . Lorsque vous installez les outils de débogage Lync Server 2013, les raccourcis et les éléments de menu ne sont pas créés. Une fois que vous avez installé les outils de débogage Lync Server 2013, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Lync Server Management Shell et accédez au répertoire (emplacement par défaut) C : \\ Program Files \\ Microsoft Lync Server 2013 \\ Debugging Tools. Double-cliquez sur Snooper.exe ou tapez Snooper.exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> L’objectif de cette rubrique n’est pas de détailler et de discuter des techniques de résolution des problèmes. Le dépannage et les processus qui l’entourent constituent un sujet complexe. Pour plus d’informations sur la résolution des problèmes de base et sur la résolution des charges de travail spécifiques, consultez le Guide du kit de ressources Microsoft Lync Server 2010 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> . Les processus et procédures s’appliquent toujours à Lync Server 2013.



</div>

Lync Server 2013 introduit une version mise à jour du Snooper qui inclut quelques nouvelles fonctionnalités. La capture d’écran suivante montre la version d’un Snooping à partir d’Office Communications Server 2007.

![Version d’Office Communications 2007 de Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Version d’Office Communications 2007 de Snooper.")

La capture d’écran suivante montre la nouvelle version de Snooper incluse dans les outils de débogage Lync Server 2013.

![Version Lync Server 2013 de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Version Lync Server 2013 de Snooper.")

La capture d’écran suivante montre la barre d’outils avec des fonctions fréquemment utilisées.

![Snooper 2013 barre d’outils.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 barre d’outils.")

La dernière fonctionnalité qui ajoute value est l’affichage Diagramme de l’organigramme (flux d’appels). Sélectionnez un flux de messages dans l’onglet **message** , puis cliquez sur le bouton **flux d’appels** . Lorsque vous parcourez les messages, le schéma de flux d’appels est mis à jour avec les nouvelles données.

![Le diagramme de flux d’appels Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Le diagramme de flux d’appels Snooper 2013.")

Vous pouvez pointer sur l’affichage Diagramme et obtenir des détails sur les messages et le contenu des flux et des messages, ainsi que sur les éléments serveur. Cliquez sur une flèche de flux d’appels pour accéder au message dans la vue messages.

![Détails du message du diagramme de flux d’appels.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Détails du message du diagramme de flux d’appels.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1.  Pour utiliser le Snooper et les fichiers journaux ouverts, vous avez besoin d’un accès en lecture aux fichiers journaux. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité CsAdministrator ou du contrôle d’accès basé sur le rôle CsServerAdministrator (RBAC), ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Après l’installation des outils de débogage Lync Server (LyncDebugTools.msi), modifiez le répertoire à l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande. Par défaut, les outils de débogage se trouvent dans C : \\ Program Files \\ Microsoft Lync Server 2013 \\ Debugging Tools. Double-cliquez sur ou exécutez Snooper.exe.

3.  Une fois le Snooper ouvert, cliquez avec le bouton droit sur **fichier**, cliquez sur **OpenFile**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **ouvrir** , puis cliquez sur **ouvrir**.

4.  Les messages de **suivi** du fichier journal sont affichés sous l’onglet **suivi** . Cliquez sur l’onglet **messages** pour afficher le contenu des messages des traces collectées.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux d’appels

1.  Pour utiliser le Snooper et les fichiers journaux ouverts, vous avez besoin d’un accès en lecture aux fichiers journaux. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle CsServerAdministrator), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Ouvrez un fichier journal, cliquez sur l’onglet **messages** , sélectionnez une conversation dans la vue messages ou sélectionnez un composant de suivi dans l’onglet **suivi** .

3.  Cliquez sur **flux des appels**.
    
    <div>
    

    > [!NOTE]  
    > Si vous cliquez sur un message ou un suivi qui ne fait pas partie d’un flux d’appels, le diagramme n’apparaît pas et un message d’État apparaît au bas du Snooping, indiquant « ce message n’est pas éligible pour callfow ». Choisissez un autre message ou suivi et le flux d’appels s’affichera si le message ou le suivi fait partie d’un flux d’appels.

    
    </div>

4.  Parcourez les messages ou les lignes de suivi et notez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.

5.  Pointez sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.

</div>

</div>

<span> </span>

</div>

</div>

</div>

