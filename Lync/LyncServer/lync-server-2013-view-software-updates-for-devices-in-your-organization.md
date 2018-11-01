---
title: "Afficher des màj logicielles pour les périphériques dans Lync Server 2013"
TOCtitle: "Afficher des màj logicielles pour les périphériques dans Lync Server 2013"
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182592(v=OCS.15)
ms:contentKeyID: 49298923
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher des mises à jour logicielles pour les périphériques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avec Lync Server 2013, vous utilisez le service web de mise à jour des périphériques pour afficher et gérer les mises à jour logicielles des périphériques de votre entreprise. Ces mises à jour sont disponibles dans des fichiers .cab (cabinet) sur le site web de support Microsoft à l’adresse [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x40c). Lorsque vous avez téléchargé le fichier .cab, exécutez la cmdlet **Import-CSdeviceUpdate** pour importer les règles de mise à jour de périphérique du fichier .cab. Pour plus d’informations sur la cmdlet **Import-CSdeviceUpdate**, voir [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate) dans la documentation Lync Server Management Shell.

> [!TIP]  
> Avant de déployer une nouvelle mise à jour dans votre entreprise, vérifiez qu’elle fonctionne correctement sur un périphérique de test.

## Pour afficher les mises à jour logicielles des périphériques de communications unifiées

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Sur le site web d’aide et de support Microsoft disponible à l’adresse [http://go.microsoft.com/fwlink/?linkid=204091\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=204091%26clcid=0x40c), téléchargez le fichier .cab sur un ordinateur doté de Lync Server 2013 (par exemple, C:\\Updates\\UCUpdates.cab).

3.  Importez les règles de mise à jour de périphérique du fichier C:\\Updates\\UCUpdates.cab en exécutant l’une des cmdlets suivantes :
    
      - Si le fichier .cab se trouve sur le même ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-2), exécutez la cmdlet suivante :
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si le fichier .cab se trouve sur un autre ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-3), exécutez la cmdlet suivante :
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Mise à jour du périphérique**.

6.  Dans la page **Mise à jour du périphérique**, cliquez sur une mise à jour de la liste, puis effectuez l’une des opérations suivantes :
    
      - **Annulez une mise à jour en attente.** Pour empêcher le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Annuler les mises à jour en attente**.
    
      - **Approuvez une mise à jour.** Pour autoriser le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Approuver**.
    
      - **Restaurez une mise à jour.** Pour autoriser le déploiement d’une mise à jour approuvée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Restaurer**.

## Voir aussi

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

