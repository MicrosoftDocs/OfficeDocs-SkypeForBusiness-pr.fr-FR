---
title: Attribution d’une stratégie de version de client par utilisateur
TOCTitle: Attribution d’une stratégie de version de client par utilisateur
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182607(v=OCS.15)
ms:contentKeyID: 49299378
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie de version de client par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie de version du client est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le Panneau de configuration Lync Server.

Le déploiement d’une ou plusieurs stratégies de version du client par utilisateur est facultatif. Vous pouvez également ne déployer qu’une stratégie de version du client au niveau global, ou encore déployer des stratégies de version du client au niveau du site ou du pool. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Lorsqu’aucune stratégie n’est attribuée, que ce soit au niveau du site, du pool ou par utilisateur, les clients par défaut qui sont autorisés à s’inscrire auprès de Lync Server 2013 sont ceux qui sont définis dans la stratégie de version du client au niveau global.

Après avoir créé au moins une stratégie de version du client par utilisateur, utilisez les procédures fournies dans cette rubrique pour affecter la stratégie qui précise les versions du client que vous souhaitez autoriser à s’enregistrer avec Lync Server.

Pour plus d’informations sur la création de stratégies de version du client par utilisateur, voir [Spécification des applications clients pouvant être utilisées pour la connexion à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## Pour affecter une stratégie de version du client par utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.

6.  Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.
    
    > [!TIP]  
    > Si vous voulez que la même stratégie de version du client par utilisateur s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <strong>Actions</strong> et sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie de version du client**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]  
    > Comme vous pouvez configurer plusieurs stratégies à partir de la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est sélectionnée par défaut pour chaque stratégie de la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Autorisez Lync Server à choisir automatiquement la stratégie au niveau global ou, si elle a été définie, la stratégie au niveau du site ou du pool.
    
      - Cliquez sur le nom d’une stratégie de version du client par utilisateur que vous avez précédemment définie sur la page **Stratégie de version du client**.
        
        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Pour affecter une stratégie de version du client par utilisateur en utilisant les cmdlets Lync Server Management Shell.

Vous pouvez affecter des stratégies de version du client par utilisateur en utilisant la cmdlet Grant-CsClientVersionPolicy cmdlet. Vous pouvez exécuter cette cmdlet depuis Lync Server 2013 Management Shell ou depuis une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour affecter une stratégie de version du client par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à l’utilisateur Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## Pour affecter une stratégie de version du client par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à tous les utilisateurs actuellement affectés à la stratégie vocale RedmondVoicePolicy. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation pour la cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## Pour annuler l’affectation d’une stratégie de version du client par utilisateur

  - La commande suivante annule l’affectation de toute stratégie de version du client par utilisateur affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale, sa stratégie de site locale (le cas échéant), ou la stratégie d’étendue de service affectée à son serveur d’inscription. Une stratégie d’étendue de service est prioritaire sur les stratégies de site, et une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide sur la cmdlet [Grant-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientVersionPolicy).

## Voir aussi

#### Autres ressources

[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

