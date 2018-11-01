---
title: Affichage des informations de la stratégie de code confidentiel
TOCTitle: Affichage des informations de la stratégie de code confidentiel
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49891255
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations de la stratégie de code confidentiel

 

_**Dernière rubrique modifiée :** 2013-02-23_

L’onglet **Stratégie de code confidentiel** vous permet d’afficher l’authentification par code confidentiel des utilisateurs qui se connectent à Lync 2013 avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web. Pour plus d’informations, voir [Modification des paramètres de configuration d’un service web existant](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Suivez ces étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.

## Pour afficher des informations sur une stratégie de code confidentiel dans Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.

## Affichage des stratégies de code confidentiel à l’aide des applets de commande Lync Server PowerShell

Vous pouvez également afficher les stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de commande Get-CsPinPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des stratégies de code confidentiel

  - Pour afficher des informations sur toutes vos stratégies de code confidentiel, tapez la commande suivante dans Lync Server Management Shell et appuyez sur ENTRÉE :
    
        Get-CsPinPolicy
    
    Les informations retournées se présentent ainsi :
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPinPolicy).

## Voir aussi

#### Tâches

[Modification des paramètres de configuration d’un service web existant](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Créer une stratégie de code confidentiel](lync-server-2013-create-a-new-pin-policy.md)

