---
title: Activer le contrôle d’admission des appels
TOCTitle: Activer le contrôle d’admission des appels
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398642(v=OCS.15)
ms:contentKeyID: 49297887
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer le contrôle d’admission des appels

 

_**Dernière rubrique modifiée :** 2012-10-19_

Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.

Pour plus d’informations, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## Pour activer le contrôle d’admission des appels à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## Pour activer le contrôle d’admission des appels à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Global**.

4.  Cliquez sur **Global** dans la liste, puis sélectionner **Afficher les détails** dans le menu **Edition**.

5.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.
    
    > [!NOTE]  
    > Si vous souhaitez désactiver le contrôle d’admission des appels à travers votre déploiement, désactivez cette case à cocher.

6.  Cliquez sur **Valider**.

