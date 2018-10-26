---
title: Affichage des informations de code confidentiel de l’utilisateur
TOCTitle: Affichage des informations de code confidentiel de l’utilisateur
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49891362
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations de code confidentiel de l’utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-23_

Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Lync Server 2013 ayant des informations d’identification de services de domaine Active Directory (AD DS) nécessite un code confidentiel. Vous pouvez afficher les informations relatives au code confidentiel d’un utilisateur à partir du Panneau de configuration Lync Server 2013.

> [!NOTE]  
> Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent par exemple si le code confidentiel a été défini ou quand il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier. Si un utilisateur a perdu son code confidentiel, vous pouvez le réinitialiser en suivant les procédures décrites dans <a href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Définition du code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013</a>.

## Pour afficher le code confidentiel d’un utilisateur dans le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.
    
    > [!NOTE]  
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <strong>Action</strong>, puis sur <strong>Déverrouiller le code confidentiel</strong>.

6.  Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.

## Pour afficher les informations relatives au code confidentiel de l’utilisateur à l’aide des applets de commande Lync Server Management Shell

Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations relatives au code confidentiel de l’utilisateur

  - Pour afficher les informations relatives au code confidentiel d’un utilisateur, tapez une commande similaire à ce qui suit dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Les informations retournées se présentent ainsi :
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsConferenceDisclaimer](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferenceDisclaimer).

## Voir aussi

#### Tâches

[Définition du code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Verrouillage ou déverrouillage du code confidentiel d’un utilisateur](lync-server-2013-lock-or-unlock-a-user-pin.md)

