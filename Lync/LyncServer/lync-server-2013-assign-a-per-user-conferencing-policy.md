---
title: Attribution d’une stratégie de conférence par utilisateur
TOCTitle: Attribution d’une stratégie de conférence par utilisateur
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521015(v=OCS.15)
ms:contentKeyID: 49297707
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie de conférence par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie de conférence est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le Panneau de configuration Lync Server.

Le déploiement d’une ou plusieurs stratégies de conférence par utilisateur est facultatif. Vous pouvez également déployer une stratégie de conférence au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite à des utilisateurs, des groupes ou des objets contact. Les droits et autorisations des utilisateurs de conférence sont automatiquement définis sur ceux de la stratégie de conférence globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Lorsque vous aurez créé au moins une stratégie de conférence par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les droits et autorisations que le serveur doit octroyer aux réunions organisées par un utilisateur particulier.

Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, voir [Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Pour plus d’informations sur la création de stratégies de conférence, voir [Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## Pour attribuer une stratégie de conférence par utilisateur

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
    > Si vous voulez que la même stratégie de conférence par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <strong>Actions</strong>, puis sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie de conférence**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]  
    > Du fait qu’il existe plusieurs stratégies configurables dans la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Sélectionnez **\<Automatique\>** pour autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global, ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de conférence par utilisateur que vous avez précédemment définie dans la page **Stratégie de conférence**.
        
        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Attribution d’une stratégie de conférence par utilisateur à l’aide des applets de commande Lync Server PowerShell

Il est également possible d’affecter des stratégies de conférence par utilisateur à l’aide de Lync Server PowerShell et de l’applet de commande Grant-CsConferencingPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affecter à un seul utilisateur une stratégie de conférence par utilisateur

  - La commande suivante affecte la stratégie de conférence par utilisateur RedmondConferencingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## Affecter à plusieurs utilisateurs une stratégie de conférence par utilisateur

  - Cette commande affecte la stratégie de conférence par utilisateur HRConferencingPolicy à tous les utilisateurs qui travaillent pour le service des ressources humaines. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## Annuler l’affectation d’une stratégie de conférence par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de conférence par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy).

## Voir aussi

#### Tâches

[Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  

#### Autres ressources

[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

