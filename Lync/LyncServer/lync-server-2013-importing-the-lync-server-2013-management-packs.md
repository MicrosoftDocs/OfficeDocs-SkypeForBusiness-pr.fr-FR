---
title: Importation des packs d’administration de Lync Server 2013
TOCTitle: Importation des packs d’administration de Lync Server 2013
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205052(v=OCS.15)
ms:contentKeyID: 49297936
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importation des packs d’administration de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant des packs d’administration — logiciel qui indique les éléments que System Center Operations Manager peut surveiller, et la façon dont ces éléments doivent être surveillés et les alertes déclenchées et signalées. Lync Server 2013 comprend deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes :

  - Le pack d’administration Composant et utilisateur (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) suit les problèmes Lync Server enregistrés dans les journaux des événements, enregistrés par les compteurs de performances, ou enregistrés dans les bases de données d’enregistrements des détails des appels (CDR) ou de qualité de l’expérience (QoE). Pour des problèmes critiques, System Center Operations Manager peut être configuré pour avertir immédiatement les administrateurs via e-mail, messagerie instantanée ou messages texte (SMS). SMS est la technologie utilisée pour envoyer des messages texte entre appareils mobiles.
    
    > [!NOTE]  
    > Pour plus d’informations sur la configuration de notification Operations Manager, voir Configurer les notifications dans la bibliothèque TechNet à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x40C</a>.

  - Le pack d’administration Surveillance active (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) teste de façon proactive les composants Lync Server clés, par exemple l’ouverture de session, l’échange de messages instantanés ou les appels vers un téléphone situé sur un réseau téléphonique commuté (PSTN). Ces tests sont exécutés à l’aide des applets de commande de transaction synthétique Lync Server. Par exemple, vous pouvez utiliser l’applet de commande **Test-CsIM** pour simuler une conversation par message instantané entre deux utilisateurs test. Si cette conversation simulée échoue, une alerte est générée.

Vous devez importer les packs d’administration. Si vous ne le faites pas, vous ne pouvez pas utiliser Operations Manager pour surveiller les événements Lync Server ou exécuter des transactions synthétiques Lync Server.

Le pack d’administration Composant et utilisateur est utilisé uniquement pour surveiller Lync Server 2013. Si vous utilisez un scénario de coexistence, dans lequel Lync Server 2013 et Lync Server 2010 sont installés, utilisez le pack d’administration Lync Server 2010 pour vos ordinateurs Lync Server 2010.

> [!NOTE]  
> Les packs d’administration pour Lync Server 2010 comprennent le pack d’administration Surveillance Lync Server 2010 et le pack d’administration Surveillance des conversations de groupe Lync Server 2010.

Vous pouvez utiliser l’un des outils suivants pour importer les packs d’administration :

  - **System Center Operations Manager**   Avec cette méthode, vous utilisez Operations Manager pour surveiller Lync Server.

  - Interpréteur de commandes **Operations Manager**   Vous pouvez utiliser l’interpréteur de commandes Operations Manager pour importer directement ou pour dépanner les problèmes rencontrés quand vous importez des packs d’administration avec la console System Center Operations Manager.

## Importation des packs d’administration avec System Center Operations Manager

1.  Téléchargez les fichiers Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp et Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  Dans System Center Operations Manager, cliquez sur **Administration**.

3.  Dans le volet **Administration**, cliquez avec le bouton droit sur **Packs d’administration**, puis cliquez sur **Importer les packs d’administration**.

4.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Ajouter**, puis sur **Ajouter à partir du disque**.

5.  Dans la boîte de dialogue **Connexion au catalogue en ligne**, cliquez sur **Annuler** pour empêcher Operations Manager de se connecter pour voir si des dépendances existent pour les packs d’administration Lync Server. Si vous utilisez System Center Operations Manager 2012, cliquez sur **Non**.

6.  Dans la boîte de dialogue **Sélectionner les packs d’administration à importer**, recherchez et sélectionnez les fichiers **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** et **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, puis cliquez sur **Ouvrir**. Pour sélectionner plusieurs fichiers dans la boîte de dialogue, cliquez sur le premier fichier, maintenez la touche Ctrl enfoncée et cliquez sur un autre fichier.

7.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Installer**. Si vous obtenez un message d’erreur et que l’installation échoue, cela signifie que les fichiers des packs d’administration se trouvent dans un dossier protégé par le contrôle du compte d’utilisateur Windows. Si cela se produit, copiez les fichiers dans un autre dossier et redémarrez le processus d’importation et d’installation.

8.  Dans la boîte de dialogue **Sélectionner les packs d’administration**, cliquez sur **Fermer**. Notez que le processus d’importation et d’installation peut prendre plusieurs minutes.

## Importation des packs d’administration avec l’interpréteur de commandes Operations Manager

En règle générale, il est plus facile d’importer les packs d’administration avec Operations Manager.Cependant, si une erreur se produit et que l’importation échoue, la console ne fournit pas forcément des rapports d’erreurs clairs. L’interpréteur de commandes Operations Manager fournit lui des informations détaillées. Si vous utilisez Operations Manager et que vous rencontrez des problèmes lors de l’importation d’un pack d’administration, importez le pack avec l’interpréteur de commandes Operations Manager. L’interpréteur de commandes Operations Manager fournit davantage d’informations susceptibles de vous aider à identifier les problèmes d’importation.

Si vous utilisez System Center Operations Manager 2007 R2, exécutez la procédure suivante :

1.  Cliquez sur **Démarrer**, **Tous les programmes**, **System Center Operations Manager 2007 R2**, puis sur Interpréteur de commandes **Operations Manager**.

2.  Dans l’interpréteur de commandes Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur Entrée :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Fermez l’interpréteur de commandes Operations Manager.

Si vous utilisez System Center Operations Manager 2012, exécutez la procédure suivante à la place :

1.  Cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft System Center 2012**, cliquez sur **Operations Manager**, puis sur Interpréteur de commande **Operations Manager**.

2.  Dans l’interpréteur de commandes Operations Manager, tapez la commande suivante à l’invite de commandes, en utilisant le chemin d’accès réel à votre copie du fichier Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, puis appuyez sur Entrée :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Une fois le premier pack d’administration importé, répétez la procédure à l’aide du chemin vers votre copie du fichier Microsoft.LS.2013.Monitoring.ComponentAndUser.mp :
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

