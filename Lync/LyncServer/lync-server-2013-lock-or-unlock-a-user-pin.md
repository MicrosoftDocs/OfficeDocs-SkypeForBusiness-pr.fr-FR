---
title: Verrouillage ou déverrouillage du code confidentiel d’un utilisateur
TOCTitle: Verrouillage ou déverrouillage du code confidentiel d’un utilisateur
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49891316
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verrouillage ou déverrouillage du code confidentiel d’un utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **Utilisateurs** du Panneau de configuration Lync Server 2013.

## Pour verrouiller le code confidentiel d’un utilisateur dans le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur en employant l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête** et sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (fichier .usf).

5.  (Facultatif) Spécifiez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou sélectionnez-la en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.
    
    6.  Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.

## Pour déverrouiller le code confidentiel d’un utilisateur dans le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur en employant l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête** et sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (fichier .usf).

5.  (Facultatif) Spécifiez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou sélectionnez-la en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.
    
    6.  Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.

## Pour verrouiller et déverrouiller des codes confidentiels d’utilisateurs à l’aide des applets de commande Lync Server Management Shell

Vous pouvez aussi verrouiller et déverrouiller des codes confidentiels d’utilisateurs à l’aide de Windows PowerShell et des applets de commande Lock-CsClientPin et Unlock-CsClientPin. Vous pouvez exécuter ces applets de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour verrouiller le code confidentiel d’un utilisateur

  - Pour verrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Lock-CsClientPin. Par exemple :
    
        Lock-CsClientPin -Identity "Ken Myer"

## Pour déverrouiller le code confidentiel d’un utilisateur

  - Pour déverrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Unlock-CsClientPin. Par exemple :
    
        Unlock-CsClientPin -Identity "Ken Myer"

Pour plus d’informations, voir la rubrique d’aide relative aux applets de commande [Lock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Lock-CsClientPin) et [Unlock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Unlock-CsClientPin).

