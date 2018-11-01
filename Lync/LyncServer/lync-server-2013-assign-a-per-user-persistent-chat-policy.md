---
title: Attribution d’une stratégie de conversation permanente par utilisateur
TOCTitle: Attribution d’une stratégie de conversation permanente par utilisateur
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49891574
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie de conversation permanente par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

Vous pouvez attribuer une stratégie de conversation persistante par utilisateur dans Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell. Pour plus d’informations sur la création de stratégies utilisateur pour serveur de conversations permanentes, voir [Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md) (contenu éventuellement en anglais).

## Pour attribuer une stratégie de conversation persistante par utilisateur dans Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation à gauche, cliquez sur **Utilisateurs**.

4.  Localisez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la boîte de dialogue **Rechercher des utilisateurs**, tapez le nom d’affichage complet ou la première partie, vos prénom, nom de famille, nom de compte de Gestionnaire des comptes de sécurité, adresse SIP ou URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez une requête enregistrée, cliquez sur l’icône **Ouvrir la requête**, recherchez la requête (fichier .usf) à l’aide de la boîte de dialogue **Ouvrir**, puis cliquez sur **Rechercher**.

5.  (Facultatif) Spécifiez des critères de recherche supplémentaires pour limiter les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en la tapant ou en la sélectionnant dans la liste déroulante en cliquant sur la flèche.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  En fonction de la propriété utilisateur sélectionnée, entrez les critères que vous voulez utiliser pour filtrer les résultats de la recherche en les tapant ou en cliquant sur la flèche de la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à votre requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.

6.  Cliquez sur un utilisateur dans les résultats de la recherche, cliquez sur **Action**, puis sur **Attribuer des stratégies**.
    
    > [!TIP]  
    > Si vous voulez que la même stratégie de conversation persistante s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <strong>Actions</strong> et sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie de conversation persistante**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]  
    > Il existe de nombreuses stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <strong>Attribuer des stratégies</strong> ; l’option <strong>&lt;Conserver tel quel&gt;</strong> est donc sélectionnée par défaut pour chaque stratégie de la boîte de dialogue. Ne modifiez pas ce paramètre pour continuer à utiliser la stratégie attribuée précédemment à l’utilisateur.    
      - Sélectionnez **\<Automatique\>** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de conversation persistante par utilisateur définie précédemment sur la page **Stratégie de conversation persistante**.
        
        > [!TIP]  
        > Pour vous aider à choisir la stratégie que vous voulez attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <strong>Voir</strong> pour afficher les droits et autorisations d’utilisateur définis dans la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Attribution d’une stratégie de conversation persistante par utilisateur à l’aide des cmdlets Lync Server PowerShell

Les stratégies de conversation persistante par utilisateur peuvent également être attribuées à l’aide de Lync Server PowerShell et de l’applet de commande Grant-CsPersistentChatPolicy. Celle-ci peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Attribution d’une stratégie de conversation persistante par utilisateur à un utilisateur unique

  - La commande suivante attribue la stratégie de conversation persistante par utilisateur RedmondPersistentChatPolicy à l’utilisateur Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## Attribution d’une stratégie de conversation persistante par utilisateur à plusieurs utilisateurs

  - Cette commande attribue la stratégie de conversation persistante par utilisateur RedmondUsersPersistentChatPolicy à tous les utilisateurs du service Informatique. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation relative à la cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) (contenu éventuellement en anglais).
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## Annulation de l’attribution d’une stratégie de conversation persistante par utilisateur

  - La commande suivante annule l’attribution de toute stratégie de conversation persistante par utilisateur attribuée précédemment à Ken Myer. Une fois l’attribution annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale ou, si elle existe, sa stratégie de site locale. Une stratégie de site prévaut sur la stratégie globale.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide pour l’applet de commande [Grant-CsPersistentChatPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPersistentChatPolicy) (contenu éventuellement en anglais).

## Voir aussi

#### Concepts

[Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

