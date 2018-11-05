---
title: "Conf. d’un nœud obs. pour l’util. de l’auth. des info. d’identification"
TOCtitle: "Conf. d’un nœud obs. pour l’util. de l’auth. des info. d’identification"
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204632(v=OCS.15)
ms:contentKeyID: 49296087
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un nœud observateur pour l’utilisation de l’authentification des informations d’identification

 

_**Dernière rubrique modifiée :** 2012-10-20_

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente afin de configurer ce nœud observateur pour qu’il exécute les transactions synthétiques. Surtout, évitez de créer un pool d’applications approuvées et une application approuvée. En revanche, vous devez installer un certificat permettant au nœud observateur d’envoyer des alertes à un ordinateur à l’intérieur du réseau de périmètre. En d’autres termes, vous devez effectuer deux tâches distinctes :

  - Mettre à jour l’appartenance au groupe « RTC Local Read-only Administrators » de l’ordinateur

  - Installer les fichiers de configuration du nœud observateur

## Mise à jour de l’appartenance au groupe « RTC Local Read-Only Administrators »

Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez ajouter le compte Service réseau au groupe « RTC Local Read-only Administrators » sur l’ordinateur de nœud observateur. Pour cela, procédez comme suit sur le nœud observateur :

1.  Cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Ordinateur** et cliquez sur **Gérer**.

2.  Dans le Gestionnaire de serveur, développez **Configuration**, **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Dans le volet Groupes, double-cliquez sur **RTC Local Read-only Administrators**.

4.  Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes**, cliquez sur **Emplacements**.

6.  Dans la boîte de dialogue **Emplacements**, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur **OK**.

7.  Dans la zone **Entrez les noms d’objets à sélectionner**, tapez **Service réseau**, puis cliquez sur **OK**.

8.  Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **OK**, puis fermez le **Gestionnaire de serveur**.

Redémarrez l’ordinateur de nœud observateur.

## Installation des fichiers de configuration du nœud observateur

Une fois que l’ordinateur du nœud observateur a redémarré, vous devez exécuter le fichier Watchernode.msi. Pour exécuter ce fichier, ouvrez Lync Server 2013 Management Shell. Pour cela, cliquez sur **Démarrer**, **Tous les programmes**, puis sur **Lync Server 2013**, et sur **Lync Server Management Shell**. Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur Entrée (veillez à bien indiquer le chemin d’accès au fichier Watchernode.msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

> [!NOTE]  
> Comme indiqué précédemment, vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <strong>Démarrer</strong>, cliquez avec le bouton droit sur <strong>Invite de commandes</strong>, puis cliquez sur <strong>Exécuter en tant qu’administrateur</strong>. Lorsque la fenêtre de commande s’ouvre, tapez la même commande que précédemment.

Le mode Négocier est utilisé à chaque fois que le nœud observateur ne peut pas être configuré en tant que pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.

