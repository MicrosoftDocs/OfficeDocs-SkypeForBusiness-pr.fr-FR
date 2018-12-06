---
title: "Inst. des fich. Lync Server 2013 princ. et de la base de données RTCLocal"
TOCtitle: "Inst. des fich. Lync Server 2013 princ. et de la base de données RTCLocal"
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204734(v=OCS.15)
ms:contentKeyID: 49296487
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des fichiers Lync Server 2013 principaux et de la base de données RTCLocal

 

_**Dernière rubrique modifiée :** 2012-10-20_

Pour installer les fichiers principaux de Lync Server 2013 sur un ordinateur, procédez de la façon suivante. La base de données RTCLocal est installée automatiquement quand vous installez les fichiers principaux. Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds observateurs. SQL Server Express est installé automatiquement à sa place.

Pour installer les fichiers principaux de Lync Server 2013 et la base de données RTCLocal :

1.  Sur l’ordinateur sur lequel se trouve le nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante puis appuyez sur Entrée, en utilisant le chemin d’accès approprié à vos fichiers d’installation de Lync Server :
    
        D:\Setup.exe /BootstrapLocalMgmt

Afin de vous assurer que les composants principaux de Lync Server ont été bien installés, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**. Dans Lync Server 2013 Management Shell, tapez la commande Windows PowerShell suivante, puis appuyez sur Entrée :

    Get-CsWatcherNodeConfiguration

La première fois que vous exécutez cette commande, elle ne renvoie aucune donnée, car vous n’avez encore configuré aucun nœud observateur. Tant que la commande s’exécute sans renvoyer d’erreur, vous pouvez considérer que l’installation de Lync Server a été correctement effectuée.

Si votre nœud observateur se trouve à l’intérieur de votre réseau de périmètre, exécutez la commande suivante pour vérifier l’installation de Lync Server 2013 :

    Get-CsPinPolicy

Vous recevrez des informations semblables aux suivantes, selon le nombre de stratégies de code confidentiel configurées dans votre organisation :

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si des informations sur vos stratégies de code confidentiel sont affichées, cela signifie que vous avez correctement installé les composants principaux.

