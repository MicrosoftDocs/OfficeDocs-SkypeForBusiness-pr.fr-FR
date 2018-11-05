---
title: "Lync Server 2013 : Dépl. de pools frontaux couplés pour la réc. d’urgence"
TOCTitle: Déploiement de pools frontaux couplés pour la récupération d’urgence
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204773(v=OCS.15)
ms:contentKeyID: 49296753
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Vous pouvez facilement déployer la topologie de récupération d’urgence des pools de serveurs frontaux par paires à l’aide du Générateur de topologie.

## Pour déployer une paire de pools de serveurs frontaux

1.  S’il s’agit de nouveaux pools qui ne sont pas encore définis, utilisez le Générateur de topologie pour les créer.

2.  Dans le Générateur de topologie, cliquez avec le bouton droit sur l’un des deux pools, puis sur **Modifier les propriétés** .

3.  Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.

4.  Dans la zone située en dessous de **Pool de stockage associé** , sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
    ![Boîte de dialogue Résilience](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "Boîte de dialogue Résilience")  

5.  Sélectionnez **Basculement et restauration automatiques pour Voice** , puis cliquez sur **OK** .
    
    Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance** .

6.  Utilisez le Générateur de topologie pour publier la topologie.

7.  Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.
    
    Cependant, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.

8.  Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.

9.  Dans une invite de commande Lync Server Management Shell, exécutez la commande suivante :
    
        Start-CsWindowsService -Name LYNCBACKUP

10. Forcez la synchronisation des données d’utilisateur et de conférence entre les deux pools, à l’aide des applets de commande suivantes :
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’état de synchronisation dans les deux sens est stable.
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]  
> L’option <strong>Basculement et restauration automatique pour Voice</strong> et les intervalles de temps associés dans le Générateur de topologie ne s’appliquent qu’aux nouvelles fonctionnalités de résistance des communications vocales introduites dans Lync Server 2010. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.
