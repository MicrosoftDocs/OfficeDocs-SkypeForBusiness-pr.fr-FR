---
title: 'Lync Server 2013 : lecture de journaux de capture à partir du service de journalisation centralisé'
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
ms.openlocfilehash: 2713c9a1209aad4a96fcb3a76afaf7c2bc61c0dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lecture de journaux de capture à partir du service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-28_

Vous pouvez bénéficier de l’avantage réel du service de journalisation centralisé après avoir exécuté la recherche et disposer d’un fichier que vous pouvez utiliser pour effectuer le suivi d’un problème signalé. Il existe plusieurs façons de lire le fichier. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad. exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil comme Snooper. exe, conçu pour lire et analyser la sortie de la journalisation à partir du service de journalisation centralisé. La fonction Snoop est incluse dans les outils de débogage de Lync Server 2013 qui sont disponibles en téléchargement séparé. Vous pouvez télécharger les outils de débogage de Lync Server [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)2013 ici :. Lorsque vous installez les outils de débogage de Lync Server 2013, des raccourcis courts et des éléments de menu ne sont pas créés. Après l’installation des outils de débogage de Lync Server 2013, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Lync Server Management Shell, puis accédez au répertoire (emplacement\\par défaut\\) C : Program\\Files Microsoft Lync Server 2013 outils de débogage. Double-cliquez sur Snoop. exe ou tapez Snoop. exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Cette rubrique n’a pas pour objectif de détailler et de discuter des techniques de résolution des problèmes. Le dépannage et les processus associés constituent un sujet complexe. Pour plus d’informations sur la résolution des problèmes de base liés à la résolution des problèmes liés à la résolution <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>des problèmes de charge de travail, voir le kit de ressources Microsoft Lync Server 2010 Les processus et procédures s’appliquent toujours à Lync Server 2013.



</div>

Lync Server 2013 introduit une version mise à jour de l’application Snoop qui inclut de nouvelles fonctionnalités. La capture d’écran suivante montre la version de Snoop d’Office Communications Server 2007.

![Version d’Office Communications 2007 de Snoop.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Version d’Office Communications 2007 de Snoop.")

La capture d’écran suivante montre la nouvelle version de Snoop incluse dans les outils de débogage de Lync Server 2013.

![Version 2013 de Lync Server de Snoop.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Version 2013 de Lync Server de Snoop.")

La capture d’écran suivante illustre la barre d’outils avec les fonctions les plus fréquemment utilisées.

![Barre d’outils Snoop 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barre d’outils Snoop 2013.")

En plus, la fonction la plus récente qui ajoute value est la vue de diagramme du diagramme de flux (flux d’appels). Sélectionnez un flux de messages dans l’onglet **message** , puis cliquez sur le bouton **flux d’appels** . Lorsque vous parcourez les messages, le diagramme de flux d’appels est mis à jour avec les nouvelles données.

![Le diagramme de flux d’appels d’Snoop 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Le diagramme de flux d’appels d’Snoop 2013.")

Vous pouvez pointer sur la vue de diagramme et obtenir des informations sur les messages et le contenu des flux et des messages ainsi que les éléments du serveur. Cliquez sur une flèche de flux d’appels pour accéder au message dans l’affichage messages.

![Détails du message du diagramme de flux d’appels.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Détails du message du diagramme de flux d’appels.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1.  Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Après l’installation des outils de débogage de Lync Server (LyncDebugTools. msi), modifiez le répertoire pour l’emplacement de Snoop. exe à l’aide de l’Explorateur Windows ou de la ligne de commande. Par défaut, les outils de débogage se trouvent dans les outils\\de débogage de\\Microsoft Lync\\Server 2013. Double-cliquez ou exécutez Snooper.exe.

3.  Après avoir ouvert Snooper, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.

4.  Les messages de **suivi** du fichier journal sont affichés dans l’onglet **Suivi**. Cliquez sur l’onglet **Messages** pour afficher le contenu des suivis collectés.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux des appels

1.  Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de suivi dans l’onglet **Suivi**.

3.  Cliquez sur **Flux des appels**.
    
    <div>
    

    > [!NOTE]  
    > Si vous cliquez sur un message ou une trace qui ne fait pas partie d’un flux des appels, le diagramme n’apparaît pas et le message d’état « Ce message n’est pas éligible pour le flux des appels » est affiché en bas de Snooper. Choisissez un autre message ou une autre trace. Le flux des appels réapparaît si le message ou la trace fait partie d’un flux des appels.

    
    </div>

4.  Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.

5.  Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.

</div>

</div>

<span> </span>

</div>

</div>

</div>

