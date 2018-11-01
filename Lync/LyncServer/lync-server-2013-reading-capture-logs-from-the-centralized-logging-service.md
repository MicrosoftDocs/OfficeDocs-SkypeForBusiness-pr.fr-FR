---
title: "Lecture des journ. de capt. à partir du service de journalisation centralisée"
TOCtitle: "Lecture des journ. de capt. à partir du service de journalisation centralisée"
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49891533
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lecture des journaux de capture à partir du service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2016-12-28_

Vous vous rendez compte des avantages du service de journalisation centralisée après avoir exécuté la recherche et obtenu un fichier que vous pouvez utiliser pour suivre un problème signalé. Vous pouvez lire le fichier de plusieurs façons. Le fichier de sortie est au format texte standard. Vous pouvez utiliser Notepad.exe ou tout autre programme permettant d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper.exe, conçu pour lire et analyser les sorties de journalisation du service de journalisation centralisée. Snooper est inclus dans les outils de débogage de Lync Server 2013 (disponibles séparément). Aucun raccourci ou élément de menu n’est créé pour les outils de débogage de Lync Server 2013. Après avoir installé les outils de débogage de Lync Server 2013, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Lync Server Management Shell, puis accédez au répertoire (emplacement par défaut) C:\\Programmes\\Microsoft Lync Server 2013\\Outils de débogage. Double-cliquez sur Snooper.exe ou tapez Snooper.exe, puis appuyez sur ENTRÉE si vous utilisez la ligne de commande ou Lync Server Management Shell.

> [!IMPORTANT]  
> Cette rubrique n’est pas destinée à aborder les techniques de résolution des problèmes. Le dépannage et les processus associés constituent un sujet complexe. Pour plus d’informations sur les bases de résolution des problèmes et les charges de travail spécifiques, voir le manuel du Kit de ressources de Microsoft Lync Server 2010 à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=211003%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=211003&amp;clcid=0x40C</a>. Les processus et procédures s’appliquent également à Lync Server 2013.

Lync Server 2013 inclut une version mise à jour de Snooper avec de nouvelles fonctionnalités. La capture d’écran suivante montre la version de Snooper associée à Office Communications Server 2007.

![Office Communications 2007 version de Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version de Snooper.")

La capture d’écran suivante montre la nouvelle version de Snooper incluse dans les outils de débogage de Lync Server 2013.

![Lync Server 2013 version de Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version de Snooper.")

La capture d’écran suivante montre la barre d’outils avec les fonctions fréquemment utilisées.

![Barre d’outils Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barre d’outils Snooper 2013.")

La vue de diagramme Organigramme (flux des appels) est une fonctionnalité inédite et utile. Sélectionnez un flux de messages sous l’onglet **Message**, puis cliquez sur le bouton **Flux des appels**. Tandis que vous traitez les messages, le diagramme de flux des appels est mis à jour avec de nouvelles données.

![Diagramme de flux des appels Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagramme de flux des appels Snooper 2013.")

Vous pouvez placer le pointeur sur la vue de diagramme pour obtenir des informations sur les messages, le contenu des flux et messages, et les éléments de serveur. Cliquez sur une flèche du flux des appels pour accéder au message dans la vue des messages.

![Détails du message du diagramme de flux des appels.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Détails du message du diagramme de flux des appels.")

## Pour ouvrir un fichier journal dans Snooper

1.  Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Après l’installation des outils de débogage de Lync Server (LyncDebugTools.msi), définissez le répertoire sur l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande. Par défaut, les outils de débogage sont situés dans C:\\Programmes\\Microsoft Lync Server 2013\\Outils de débogage. Double-cliquez ou exécutez Snooper.exe.

3.  Une fois Snooper ouvert, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.

4.  Les messages de **trace** du fichier journal sont affichés sous l’onglet **Trace**. Cliquez sur l’onglet **Messages** pour afficher le contenu des traces collectées.

## Pour afficher un diagramme de flux des appels

1.  Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.

2.  Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de trace sous l’onglet **Trace**.

3.  Cliquez sur **Flux des appels**.
    
    > [!NOTE]  
    > Si vous cliquez sur un message ou une trace que ne fait pas partie d’un flux des appels, le diagramme n’apparaît pas et le message d’état « Ce message n’est pas éligible pour le flux des appels » est affiché en bas de Snooper. Choisissez un autre message ou une autre trace. Le flux des appels réapparaît si le message ou la trace fait partie d’un flux des appels.

4.  Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.

5.  Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.

