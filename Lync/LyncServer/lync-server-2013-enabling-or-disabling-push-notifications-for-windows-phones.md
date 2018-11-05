---
title: Activation ou désactivation des notifications push pour les Windows Phone
TOCTitle: Activation ou désactivation des notifications push pour les Windows Phone
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49891479
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation des notifications push pour les Windows Phone

 

_**Dernière rubrique modifiée :** 2013-02-23_

Des notifications push, sous forme de badges, icônes ou alertes, peuvent être envoyées à un Windows Phone même lorsque l’application mobile est inactive. Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation de messagerie instantanée nouvelle ou manquée ou un message vocal. Vous pouvez activer ou désactiver les notifications push pour les appareils Windows Phone à l’aide du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour activer les notifications push pour Windows Phone à partir du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications push**, cliquez sur le site à modifier, sur le menu **Edition**, puis sur **Afficher les détails**.

5.  Activez la case à cocher **Activer les notifications push Microsoft**.

6.  Cliquez sur **Valider**.

## Pour désactiver les notifications push pour Windows Phone à partir du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications push**, cliquez sur le site à modifier, sur le menu **Edition**, puis sur **Afficher les détails**.

5.  Désactivez la case à cocher **Activer les notifications push Microsoft**.

6.  Cliquez sur **Valider**.

## Pour activer ou désactiver les notifications push pour Windows Phone à l’aide d’applets de commande Windows PowerShell

Vous pouvez activer ou désactiver les notifications push pour Windows Phone à l’aide de l’applet de commande **Set-CsPushNotificationConfiguration**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer les notifications push pour Windows Phone

  - Pour activer les notifications push pour Windows Phone, affectez la valeur True ($True) à la propriété EnableMicrosoftPushNotificationService. Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

## Pour désactiver les notifications push pour Windows Phone

  - Pour désactiver les notifications push pour Windows Phone, affectez la valeur False ($False) à la propriété EnableMicrosoftPushNotificationService. Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## Voir aussi

#### Tâches

[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

