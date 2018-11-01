---
title: "Afficher le statut des services s’exécutant sur un ordi. dans Lync Server 2013"
TOCtitle: "Afficher le statut des services s’exécutant sur un ordi. dans Lync Server 2013"
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182606(v=OCS.15)
ms:contentKeyID: 49299355
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher le statut des services s’exécutant sur un ordinateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Panneau de configuration Lync Server 2013 permet de consulter tous les services qui s’exécutent sur un ordinateur donné de votre topologie Lync Server et voir le statut de chaque service.

## Pour consulter le statut des services qui s’exécutent sur un ordinateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**.

4.  Sur la page **Statut**, triez ou recherchez dans la liste, le cas échéant, l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.

5.  Effectuez l’une des opérations suivantes :
    
      - Pour voir le dernier statut des services qui s’exécutent sur l’ordinateur, cliquez sur **Obtenir le statut du service**.
    
      - Pour voir la liste des services spécifiques qui s’exécutent sur l’ordinateur et le statut de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.

## Affichage de l’état des services en utilisant les cmdlets Lync Server Management Shell

Vous pouvez également afficher l’état des services en utilisant Lync Server Management Shell et la cmdlet **Get-CsWindowsService**. Vous pouvez exécuter cette cmdlet depuis Lync Server 2013 Management Shell ou depuis une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher l’état des services

  - Pour afficher l’état des services sur un ordinateur, entrez une commande semblable à la suivante dans Lync Server Management Shell puis appuyez sur Entrée :
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Cette commande renvoie des informations comme celles-ci :
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

Pour plus d’informations, voir [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## Voir aussi

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

