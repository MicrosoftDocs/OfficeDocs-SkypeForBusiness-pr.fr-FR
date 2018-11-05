---
title: Affichage des informations sur les paramètres de notification push
TOCTitle: Affichage des informations sur les paramètres de notification push
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49891517
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations sur les paramètres de notification push

 

_**Dernière rubrique modifiée :** 2013-02-23_

Des notifications push, sous forme de badges, icônes ou alertes, peuvent être envoyées à un appareil mobile même si l’application mobile est inactive. Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal. Vous pouvez afficher les paramètres de notifications push pour les appareils mobiles en utilisant le Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell.

## Pour afficher les informations de notification Push depuis le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications push**, cliquez sur le site à afficher, sur le menu **Edition**, puis sur **Afficher les détails**.

## Pour afficher les informations de configuration pour les notifications Push à l’aide des applets de commande Windows PowerShell

Vous pouvez aussi afficher les paramètres de configuration des notifications Push à travers Lync Server Management Shell et l’applet de commande **Get-CsPushNotificationConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations de configuration des notifications Push

  - Pour afficher les informations sur tous les paramètres de configuration de vos notifications Push, tapez la commande suivante dans le Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsPushNotificationConfiguration
    
    Les informations retournées se présentent ainsi :
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

Pour plus d’informations, voir la rubrique d’aide de l’applet de commande [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPushNotificationConfiguration).

## Voir aussi

#### Tâches

[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

