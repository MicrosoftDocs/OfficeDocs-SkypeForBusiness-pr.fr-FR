---
title: Créer ou modifier une stratégie de version du client
TOCTitle: Créer ou modifier une stratégie de version du client
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898476(v=OCS.15)
ms:contentKeyID: 53095416
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une stratégie de version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez utiliser des stratégies de version du client pour spécifier les versions des clients pris en charge dans votre environnement. La gestion des versions du client vous permet de réduire les coûts associés à la prise en charge de plusieurs versions du client. Elle permet également d’améliorer l’expérience utilisateur globale, car quand une version antérieure et une version ultérieure de clients interagissent, les fonctionnalités disponibles peuvent être limitées par la version antérieure du client. Vous pouvez créer ou modifier des stratégies de version du client à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour créer ou modifier des stratégies de version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**.
    
    > [!NOTE]  
    > L’onglet <strong>Stratégie de version du client</strong> est sélectionné par défaut.

4.  Dans la page **Stratégie de version du client**, effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie de version du client, cliquez sur **Nouveau**, sélectionnez **Stratégie du site**, **Stratégie du pool** ou **Stratégie de l’utilisateur**, puis cliquez sur **OK**.
    
      - Pour modifier la stratégie globale ou une autre stratégie de version de client existante, sélectionnez la stratégie, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans la page **Modifier la stratégie de version du client**, créez ou modifiez les règles comme décrit dans [Créer ou modifier une nouvelle règle de stratégie de version du client](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

## Création ou modification de stratégies de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez créer des stratégies de version du client à l’aide de l’applet de commande **New-CsClientVersionPolicy**, et les modifier à l’aide de l’applet de commande **Set-CsClientVersionPolicy**. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer une stratégie de version de client au niveau de l’étendue Site

  - La commande suivante crée une stratégie de version du client appliquée au site Redmond. Aucun paramètre supplémentaire n’étant spécifié, la nouvelle stratégie utilise les paramètres par défaut de la version du client.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

## Pour créer une stratégie de version de client au niveau de l’étendue Utilisateur

  - Pour créer une stratégie au niveau de l’étendue Utilisateur, utilisez une commande similaire à celle-ci :
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

Pour plus d’informations, recherchez les rubriques d’aide relatives aux applets de commande [New-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionPolicy) et [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy).

