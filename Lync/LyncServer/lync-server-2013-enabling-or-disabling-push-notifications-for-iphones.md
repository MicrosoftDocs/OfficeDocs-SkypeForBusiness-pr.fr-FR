---
title: Activation ou désactivation des notifications push pour les iPhone
TOCTitle: Activation ou désactivation des notifications push pour les iPhone
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49891429
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation des notifications push pour les iPhone

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les notifications Push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un iPhone même quand l’application mobile est inactive. Les notifications Push avertissent un utilisateur d’événements, tels que des invitations de messagerie instantanée nouvelle ou manquée et un message vocal. Vous pouvez activer ou désactiver les notifications Push pour un iPhone en utilisant le Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell.

## Pour activer les notifications Push pour iPhone à partir du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications push**, cliquez sur le site à modifier, sur le menu **Edition**, puis sur **Afficher les détails**.

5.  Cochez la case **Activer les notifications push Apple**.

6.  Cliquez sur **Valider**.

## Pour désactiver les notifications Push pour iPhone à partir du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications push**, cliquez sur le site à modifier, sur le menu **Edition**, puis sur **Afficher les détails**.

5.  Décochez la case **Activer les notifications push Apple**.

6.  Cliquez sur **Valider**.

## Pour activer ou désactiver les notifications Push sur un iPhone en utilisant les applets de commande Windows PowerShell

Vous pouvez activer ou désactiver les notifications Push pour un iPhone Apple en utilisant l’applet de commande **Set-CsPushNotificationConfiguration**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer les notifications Push pour un iPhone

  - Pour activer les notifications Push pour un iPhone définissez la valeur de la propriété EnableApplePushNotificationService à True ($True). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

## Pour désactiver les notifications Push pour un iPhone

  - Pour désactiver les notifications Push pour un iPhone définissez la valeur de la propriété EnableApplePushNotificationService à False ($False). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## Voir aussi

#### Tâches

[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

