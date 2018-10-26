---
title: Affectation d’une stratégie de code confidentiel par utilisateur
TOCTitle: Affectation d’une stratégie de code confidentiel par utilisateur
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182594(v=OCS.15)
ms:contentKeyID: 49299011
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affectation d’une stratégie de code confidentiel par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie de code confidentiel pour les conférences rendez-vous fait partie des paramètres individuels d’un compte d’utilisateur pouvant être configurés dans l’environnement de ligne de commande Panneau de configuration Lync Server 2013.

Le déploiement d’une ou plusieurs stratégies de code confidentiel par utilisateur est facultatif. Vous pouvez également déployer une stratégie de code confidentiel au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les droits et autorisations des utilisateurs concernant l’utilisation des codes confidentiels pour les conférences rendez-vous sont automatiquement définis sur ceux de la stratégie de code confidentiel globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Lorsque vous aurez créé au moins une stratégie de code confidentiel par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les contraintes que le serveur doit appliquer aux codes confidentiels créés et utilisés par un utilisateur particulier.

Pour plus d’informations sur la création de stratégies de code confidentiel par utilisateur pour les conférences rendez-vous, voir [Création ou modification des paramètres de code confidentiel dans Lync Server 2013 pour les conférences rendez-vous pour un site ou un groupe d’utilisateurs](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## Pour attribuer une stratégie de code confidentiel par utilisateur

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
    > Si vous voulez que la même stratégie de code confidentiel par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <strong>Actions</strong>, puis sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie de code confidentiel**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]  
    > Comme vous pouvez configurer plusieurs stratégies à partir de la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est sélectionnée par défaut pour chaque stratégie de la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Autorisez Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle a été définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de code confidentiel par utilisateur que vous avez définie dans la page **Stratégie de code confidentiel**.
        
        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Affectation d’une stratégie de code confidentiel par utilisateur en utilisant les cmdlets de Lync Server Management Shell

Vous pouvez affecter des stratégies de code confidentiel par utilisateur en utilisant l’environnement de ligne de commande Lync Server Management Shell et la cmdlet **Grant-CsPinPolicy**. Vous pouvez exécuter cette cmdlet depuis l’environnement de ligne de commande Lync Server 2013 Management Shell ou depuis une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour affecter une stratégie de code confidentiel par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondPinPolicy à l’utilisateur Ken Myer.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## Pour affecter une stratégie de code confidentiel par utilisateur à plusieurs utilisateurs

  - La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondUsersPinPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## Pour annuler l’affectation d’une stratégie de code confidentiel par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de code confidentiel par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir [Grant-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPinPolicy).

## Voir aussi

#### Tâches

[Créer une stratégie de code confidentiel](lync-server-2013-create-a-new-pin-policy.md)  

#### Autres ressources

[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

