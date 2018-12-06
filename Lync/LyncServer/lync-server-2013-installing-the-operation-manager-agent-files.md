---
title: Installation des fichiers de l’agent Operation Manager
TOCTitle: Installation des fichiers de l’agent Operation Manager
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205345(v=OCS.15)
ms:contentKeyID: 49299108
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des fichiers de l’agent Operation Manager

 

_**Dernière rubrique modifiée :** 2012-10-20_

Pour installer les fichiers de l’agent Operations Manager sur l’ordinateur, procédez comme suit.

1.  Dans votre support d’installation System Center, double-cliquez sur **SetupOM.exe**.

2.  Dans l’installation de System Center Operation Manager, cliquez sur **Installer l’agent Operations Manager**.

3.  Dans l’Assistant Installation de System Center, sur la page **Bienvenue dans l’installation de System Center Operations Manager**, cliquez sur **Suivant**.

4.  Sur la page **Dossier de destination**, sélectionnez le dossier où les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **Suivant**.

5.  Sur la page **Configuration du groupe d’administration**, sélectionnez **Spécifier les informations du groupe d’administration**, puis cliquez sur **Suivant**.

6.  Sur la page **Configuration du groupe d’administration**, tapez le nom de votre groupe d’administration Operations Manager dans la zone **Nom du groupe d‘administration**, puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, atl-scom-001) dans la zone **Serveur d’administration**. Si vous avez modifié le numéro de port utilisé par Operations Manager, tapez le nouveau numéro de port dans la zone Port de serveur d’administration. Sinon, laissez la valeur par défaut sur 5723, puis cliquez sur **Suivant**.

7.  Sur la page **Compte d’action d’agent**, sélectionnez **Système local**, puis cliquez sur **Suivant**.

8.  Sur la page **Microsoft Update**, sélectionnez **Je ne souhaite pas utiliser Microsoft Update**, puis cliquez sur **Suivant**.

9.  Sur la page **Prêt pour l’installation**, cliquez sur **Installer**.

10. Sur la page **Terminer l’Assistant Installation de System Center Operations Manager**, cliquez sur **Terminer**.

11. Cliquez sur **Quitter**.

Si vous utilisez System Center 2007 R2, vous pouvez vérifier que l’agent a bien été créé en cliquant sur **Démarrer**, **Tous les programmes**, **System Center Operations Manager 2007 R2**, puis **Interpréteur de commandes d’Operations Manager**. Dans l’Interpréteur de commandes d’Operations Manager, tapez la commande Windows PowerShell suivante, puis appuyez sur Entrée :

    Get-Agent 

Une liste de tous vos agents Operations Manager apparaît à l’écran.

Si vous utilisez System Center 2012, exécutez cette commande à partir de l’Interpréteur de commandes d’Operations 2012 :

    Get-SCOMAgent

